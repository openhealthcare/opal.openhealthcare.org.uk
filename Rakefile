task :setupdocs do
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
end

task :docs do
  sh "git pull origin gh-pages"
  sh "rm -rf _opalsrc"
  sh "rm -rf docs/"
  sh "mkdir docs"
  sh "git clone git@github.com:openhealthcare/opal _opalsrc"
  ["master", "v0.6.0", "v0.7.0"].each do |b|
    puts "Bulding docs for #{b}"
    sh "cd _opalsrc; git checkout #{b};"
    sh "cd _opalsrc/doc; mkdocs build"
    sh "mv _opalsrc/doc/site docs/#{b}"
    sh "cp -r docs/#{b}/img img"
  end
  sh "cp -r docs/master/* docs"

  sh "git add ."
  sh "git commit -a -m 'Rake:: Add newly generated docs to site.'"
  sh "git push origin gh-pages"
end
