task :setupdocs do
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
end

task :docs do
  sh "cd _opalsrc; git pull origin master"
  sh "cd _opalsrc/doc; mkdocs clean; mkdocs build"
  sh "rm -rf docs/"
  sh "mv _opalsrc/doc/site docs"
  sh "git add ."
  sh "git commit -a -m 'Rake:: Add newly generated docs to site.'"
  sh "git push origin gh-pages"
end