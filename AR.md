# Active Record

- is the M in MVC

- Excellent at abstracting away SQL queries from our applictaion.

- Developed as a part of Rails
  - Purpose: define Database Models
    - to allow the web app to easily work with an SQL database using Classes.

    
- each AR Class is a Model
- corresponds to an existing table in the database
- provides attributes that map to each column/field in the table

- You can CRUD records in that particular table using said Class and
  its instances.
  - ie., a User model will automagically connect to the users table in the 
    database.
    
If there are two fields along witht eh PK, then AR will allow us to get/set
these on a given instance of User.
    
 ```ruby
# Executes the following SELECT and returns an instance attributes for that record:
#   SELECT * FROM users WHERE email = 'bob@loblaw.com' LIMIT 1;
user = User.find_by(email: 'bob@loblaw.com')

# Reads an attribute (like an attr_reader)
user.id # => 5

# These are just like an attr_writers, performing changes in memory (no UPDATE sql)
user.name  = 'Bob'
user.email = 'bob@loblaw.org'

# Executes the following UPDATE statement:
#   UPDATE users SET name = 'Bob', email = 'bob@loblaw.org' WHERE id = 1;
# (Assuming id of record was 1)
user.save
```

- Represents Models and their data
- Represents associations between these models
- represents inherited hierarchies through related models (tables)
- Validate models before they get persisted to the database
- Perform db operations with OOP mehods

## Naming Conventions

[naming_conventions](naming_conventions)

## Schema Conventions

[schema](schema)

## Migrations

[migrations](migrations)
