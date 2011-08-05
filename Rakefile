# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "bio-core"
  gem.homepage = "http://github.com/helios/bioruby-core"
  gem.license = "MIT"
  gem.summary = %Q{BioRuby core plugins, most and stable plugins. BlastXMLParser, BWA, SamTools }
  gem.description = %Q{Bioruby core plugins}
  gem.email = "ilpuccio.febo@gmail.com"
  gem.authors = ["Raoul J.P. Bonnal"]
  # dependencies defined in Gemfile
  gem.add_runtime_dependency 'bio',["= 1.4.1"]
  gem.add_runtime_dependency 'bio-assembly',["= 0.1.0"]
  gem.add_runtime_dependency 'bio-gff3',["= 0.8.7"]
  gem.add_runtime_dependency 'bio-logger',["= 1.0.0"]
  gem.add_runtime_dependency 'intermine-bio',["= 0.98.1"]
  gem.add_runtime_dependency 'ruby-ensembl-api',["= 1.0.1"]
  gem.add_runtime_dependency 'bio-ucsc-api',["= 0.1.0"]
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

require 'rcov/rcovtask'
Rcov::RcovTask.new do |test|
  test.libs << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
  test.rcov_opts << '--exclude "gems/*"'
end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "bio-core #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
