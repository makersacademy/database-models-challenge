require 'pg'

task :setup do
  connection = PG.connect
  connection.exec('CREATE DATABASE models;')

  connection = PG.connect :dbname => 'models';
  connection.exec('CREATE TABLE books (id SERIAL PRIMARY KEY, title VARCHAR(20), author VARCHAR(20), loaned boolean);')
  connection.exec('CREATE TABLE restaurants (id SERIAL PRIMARY KEY, name VARCHAR(20), location VARCHAR(20));')
  connection.exec('CREATE TABLE clothes (id SERIAL PRIMARY KEY, item VARCHAR(20), size int, colour VARCHAR(20), label VARCHAR(20));')
end

task :seed_db do
  connection = PG.connect :dbname => 'models';
  connection.exec ('TRUNCATE TABLE books;')
  connection.exec ("INSERT INTO books VALUES (1, 'Harry Potter', 'J.K Rowling', False);")
  connection.exec ("INSERT INTO books VALUES (2, 'The Web', 'Tim Berners Lee', True);")
  connection.exec ("INSERT INTO books VALUES (3, 'Not A Real Boy', 'Robert Webb', False);")
  connection.exec ("INSERT INTO books VALUES (4, 'Helloworld!', 'Anon', False);")
  connection.exec ('TRUNCATE TABLE restaurants;')
  connection.exec ("INSERT INTO restaurants VALUES (1, 'McDonalds', 'Roundabout');")
  connection.exec ("INSERT INTO restaurants VALUES (2, 'KFC', 'Street corner');")
  connection.exec ("INSERT INTO restaurants VALUES (3, 'Wagamamas', 'Town');")
  connection.exec ("INSERT INTO restaurants VALUES (4, 'Prezzo', 'Train station');")
  connection.exec ('TRUNCATE TABLE clothes;')
  connection.exec ("INSERT INTO clothes VALUES (1, 'Trousers', 10, 'Red', 'Guess');")
  connection.exec ("INSERT INTO clothes VALUES (2, 'Skirt', 10, 'Blue', 'Calvin Klein');")
end
