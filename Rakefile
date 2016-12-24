require "bundler/gem_tasks"
require "rake/testtask"
require 'find'

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

task :default => :test

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') { |name| puts name[2..-1] if File.file?(name) }
end

desc 'Display listing of all hidden files'
task :listing do
  Find.find('.') do |name|
    next if name == '.'
    clean_name = name[2..-1]

    puts clean_name if File.file?(clean_name) && !clean_name.start_with?('.')
  end
end
