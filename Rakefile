task :setupdocs do
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
end

task :docs do
  sh "git pull origin gh-pages"
  sh "cd _opalsrc; git pull origin master"
  sh "cd _opalsrc/doc; mkdocs build"
  sh "rm -rf docs/"
  sh "mv _opalsrc/doc/site docs"
  sh "cp -r docs/img img"
  sh "git add ."
  sh "git commit -a -m 'Rake:: Add newly generated docs to site.'"
  sh "git push origin gh-pages"
end
