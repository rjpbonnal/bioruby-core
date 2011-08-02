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
  gem.add_runtime_dependency 'bio'
  gem.add_runtime_dependency 'bio-bwa'
  gem.add_runtime_dependency 'bio-samtools'
  gem.add_runtime_dependency 'bio-blastxmlparser'
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
