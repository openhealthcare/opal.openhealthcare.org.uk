task :setupdocs do
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
end

task :docs do
  sh "git pull origin gh-pages"
  sh "rm -rf _opalsrc"
  sh "rm -rf docs/"
  sh "mkdir docs"
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
  [
    "master", "v0.6.0", "v0.7.0", "v0.7.1", "v0.7.2",
    "v0.7.3", "v0.7.4", "v0.8.0", "v0.8.1", "v0.8.2",
    "v0.8.2.1", "v0.8.3", "v0.9.0", "v0.10.0", "v0.10.1", "v0.11.0",
    "v0.11.1", "v0.11.2", "v0.12.0", "v0.12.1", "v0.13.0", "v0.13.1",
    "v0.14.0", "v0.14.1", "v0.14.2", "v0.15.0", "v0.16.0", "v0.17.0",
    "v0.17.1", "v0.18.0", "v0.18.1", "v0.18.2", "v0.18.3", "v0.18.4",
    "v0.20.0", "v0.21.0", "v0.22.0", "v0.22.1", "v0.22.2", "v0.23.0",
    "v0.23.1"
  ].each do |b|
    puts "Bulding docs for #{b}"
    sh "cd _opalsrc; git checkout #{b};"
    sh "cd _opalsrc/doc; mkdocs build"
    sh "mv _opalsrc/doc/site docs/#{b}"
    sh "cp -r docs/#{b}/img/* img/"
  end
  sh "cp -r docs/master/* docs"

  sh "git add ."
  sh "git commit -a -m 'Rake:: Add newly generated docs to site.'"
  sh "git push origin gh-pages"
end
