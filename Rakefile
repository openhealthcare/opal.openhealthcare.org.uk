task :setupdocs do
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
end

task :docs do
  sh "cd _opalsrc; git pull origin master"
  sh "cd _opalsrc/doc; mkdocs build"
  sh "mv _opalsrc/doc/site docs"
end
