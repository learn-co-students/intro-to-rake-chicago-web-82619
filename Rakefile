desc 'outputs hello to the terminal'
task :hello do
  puts "hello from Rake!"
end

namespace :greeting do
  desc 'says hello'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'says hola'
  task :hola do
    puts "hola de Rake!"
  end
end

namespace :db do
  desc 'migrates changes to database'
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed the table with dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end

  desc 'delete table'
  task :destroy => :environment do
    Student.drop_table
    Student.create_table
  end
end

task :environment do
  require_relative './config/environment.rb'
end

desc 'starts a pry session'
task :console => :environment do
  Pry.start
end