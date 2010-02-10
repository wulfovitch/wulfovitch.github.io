--- 
layout: post
title: "LaTeX Compile Script"
time: '17:19'
---

I am dealing with a lot of LaTeX documents lately. The need to compile every tex document at least two times is really annoying. And if you also have to use bibtex, then it gets real cumbersome to compile all the appropriate files properly. Though I have written this small ruby script, which takes care of all the files and compiles them in the correct order:

{% highlight ruby %}
#!/usr/bin/env ruby
# default values
compileCount = 3
open_latex_document = false

def outputErrorMessage
  puts "Too many parameters..."
  puts "Usage: 'rubylatex.rb anylatexfile.tex [compilecountnumber]'"
  puts "where [compilecountnumber] is a number greater than 0"
end

# check arguments
if ARGV.count == 1
  latexfile = ARGV[0]
elsif ARGV.count == 2 || ARGV.count == 3
  latexfile = ARGV[0]
  compileCount = ARGV[1].to_i
  
  # check if compileCount has a reasonable value
  if compileCount < 1 || compileCount > 5
    outputErrorMessage
    exit
  end
  
  # open the latex document if a third parameter has been detected
  if ARGV.count == 3
    open_latex_document = true
  end
else
  outputErrorMessage
  exit
end

# filename without file type extension
filebasename = File.basename("#{latexfile}", '.tex')

# compile latex file at least one time 
sout = system("pdflatex #{latexfile}")

# create bibtex files
if sout
  sout = system("bibtex "+filebasename)
end

# compile latex files a few times more
if sout && compileCount > 1
  (2..compileCount).each do |i|
    if sout
      sout = system("pdflatex #{latexfile}")
    end
  end
end

# cleanup
puts "#### cleaning up! ####"
system("rm -rf *.log")
system("rm -rf *.aux")
system("rm -rf *.aux.bak")
system("rm -rf *.toc")
system("rm -rf *.out")
system("rm -rf *.idx")
system("rm -rf *.blg")
system("rm -rf *.bbl")
system("rm -rf *.nlo")
system("rm -rf *.lot")
system("rm -rf *.lof")
system("rm -rf *.tcp")
system("rm -rf *.tps")
system("rm -rf *.brs")
system("rm -rf *.brf")

# pdf successfully generated
if sout
  puts "#### done! #{filebasename}.pdf is ready! ####"
  if open_latex_document
    puts "#### opening #{filebasename}.pdf now! ####"
    system("open #{filebasename}.pdf")
  end
else
  # failed pdf generation
  system("rm -rf #{filebasename}.pdf")
  puts "#### failed! no pdf generated!!! ####"
end
{% endhighlight %}

The script is a little bit bloated, but it gets the job done and it even takes care of deleting all the temporary files which are created during the compiling process.