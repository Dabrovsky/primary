#!/usr/bin/env rake
begin
  require 'bundler/setup'
rescue LoadError
  puts 'You must `gem install bundler` and `bundle install` to run rake tasks'
end
begin
  require 'rdoc/task'
rescue LoadError
  require 'rdoc/rdoc'
  require 'rake/rdoctask'
  RDoc::Task = Rake::RDocTask
end

RDoc::Task.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'Primary'
  rdoc.options << '--line-numbers'
  rdoc.rdoc_files.include('README.rdoc')
  rdoc.rdoc_files.include('lib/**/*.rb')
end


require 'rspec/core/rake_task'

desc 'Default: Run all specs for a specific rails version.'
task :default => :spec

desc "Run all specs for a specific rails version"
RSpec::Core::RakeTask.new(:spec) do |t|
  t.pattern = '**/*_spec.rb'
end



Bundler::GemHelper.install_tasks

