require 'bundler/setup'
require 'bump/tasks'
require 'rubocop/rake_task'

Bundler::GemHelper.install_tasks

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.pattern = './test/**/*_test.rb'
  test.verbose = false
  test.warning = true
end

task default: ["rubocop", "test"]

RuboCop::RakeTask.new

desc 'Run an IRB console with ActiveRecordShards loaded'
task :console do
  require 'irb'
  require 'irb/completion'
  require 'active_record_shards'
  ARGV.clear
  IRB.start
end
