require 'bundler/setup'
Bundler::GemHelper.install_tasks

require 'rake/testtask'
require 'rubocop/rake_task'

Rake::TestTask.new do |t|
  t.libs << 'test'
  t.test_files = FileList['test/**/*_test.rb', 'test/**/test_*.rb']
  t.verbose = true
end

RuboCop::RakeTask.new

task default: [:test, :rubocop]

task :parse do
  require 'timezone/parser'

  Timezone::Parser.new.perform
end
