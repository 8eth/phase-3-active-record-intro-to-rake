namespace :greeting do
  desc 'outputs hello to the terminal'
    task :hello do
      puts "hello from Rake!"
    end

  desc 'outputs hola to the terminal'
    task :hola do
      puts "hola de Rake!"
    end
end

namespace :db do
  #this allows us to run 'rake db:migrate'
  desc 'migrate changes to your database'
  task migrate: :environment do
    Student.create_table
  end

  # this allows us to run 'bundle exec rake db:seed' to seed the table we created above with data from db/seeds.db
  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end

#this prevents an error that happens when running 'rake db:migrate' just with the above code
task :environment do
  require_relative './config/environment'
end

# this allows us to run 'bundle exec rake console' in terminal to start pry session
desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end


