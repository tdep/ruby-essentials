# ruby-essentials
## Basics

### Data Accessing
String iteration :
```Ruby
name = "Bobblu"
name.chars do |c|
  puts c
end
```

Accessing keys in hashes:
```Ruby
user = {name: "t-dog", power: "telepathy"}

(notice: using p will output the data as its datatype vs. puts which will just print 
p user.keys -> [:name, :power]
puts user.keys -> name
                  power
```

To find find out the data type:
```Ruby
user.class
```

### Function Syntax

Function notation in JavaScript:
```JavaScript
const double = (num) => {
  return num * 2
}
```
vs. function notation in Ruby:
```Ruby
def double(num)
  return num * 2
end

### Conditionals

If/Else notation in Javascript:
```JavaScript
if (x > 10) {
  console.log("X is greater than 10")
} else {
  console.log("X is NOT greater than 10")
}
```

vs. If/Else notation in Ruby:
```Ruby
if x > 10
  p "X is greater than 10"
else 
  p "X is NOT greater than 10"
end
```


## Active User

Migration files control the data modeling of tables and how data will be converted 
when moving between the database and the Ruby app.

### creating Migration Files

After `bundle install`, set up a migration table using rake:
`bundle exec rake db:create_migration NAME=create_********s`

### Accessing the rake console:
`rake console`

### Migration Signatures

When you first create a Migration File, you end up with this:
```Ruby
class CreateUsers < ActiveRecord::Migration[7.0]
  def change
  end
end
```

You can then populate it by adding the data to be passed and its type:
```Ruby
class CreateUsers < ActiveRecord::Migration[7.0]
  def change
    create_table :table_name_plural do |t|
      t.ruby_data_type :attribute_name
      t.ruby_data_type :another_attribute_name
    end
  end
end
```

For example:
```Ruby
class CreateUsers < ActiveRecord::Migration[7.0]
  def change
    create_table :trees do |t|
      t.string :tree_name
      t.integer :tree_age
      t.boolean :tree_living
      t.Other :Other_table
    end
  end
end
```

You can check on the status of a migration using the following:
`rake db:migrate:status`

## CRUD and AR

Creating a record:
`user = User.create(key:value, key:value, etc.)`

Getting a record from a database:
`user = User.find(1)` or `User.first/second/third/.../last`

Updating a record:
`user.update(key:value, key:value, etc.)

Delete a record:
`user.destroy`
