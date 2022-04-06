# Rails

- is a server language
 
## Q&A

can you suggest setting up a linter for Ruby - intellisense - prettier ?

## MVC

model view controller

- different functionality based on where the files are located
- separation of concerns by folders ie., views in the views folder and 
controllers in the controller folder

---

install Rails
- it is like installing a react app
`rails new [name]`

what is gems
- it is like npms modules from `npm init`

`Gemfile` is like package.json
rake file is like the scropts portion of the npm package.json

always run to start - like `npm start`
`bundle exec rails`
or
`bin/rails`

connect a database - lookup

generate the model - prepends with a time stamp
`bundle exec rails generate model [name]`
- then look in the `migrate` folder

So generating a model creates a table?
- yes, refer to the migration file in the lesson for an example

You can build your db with rails and not even write one piece of SQL

- there is a `bundle install faker` look it up first - and also turn off your app then
install

- you will run a migration many time
`/bin/rails db:migrate`

- the schema is auto generated
- you have to generate the locations: which are basically cells in the db.
  - location of the data

`bin/rails db:seed`



`bin/rails c`
command line for the server development environment - use to interact 
with the database, SQL's, 

use the CLI for generating, etc.

The `seeds.rb` is where you populate the db. you have the correct column name
and the tables are built in the migrate folder.. These are generated from 
the CLI.

_You have to seed in the right order, if there are relationships between the 
tables_


