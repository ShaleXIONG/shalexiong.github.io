task :default => :build

task :build do
  sh "bundle exec jekyll build"
end

task :deploy => :build do
  sh "gsutil cp -R _site/** gs://www.shalexiong.com "
end
