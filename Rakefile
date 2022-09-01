require "rake/testtask"
require "find"
require "bundler/gem_tasks"

desc 'Say hello'
task :hello do 
  puts "Hello there. This is the 'hello' task."
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'Run tests'
task :default => :test

desc 'list of files except those that sart with (.)'
task :list_files do 
  list_of_files = []
  Find.find(".") do |name|
    next if name.include?('/.')
    list_of_files << name if File.file?(name)
  end
  puts list_of_files
end

