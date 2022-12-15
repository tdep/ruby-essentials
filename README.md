# ruby-essentials
## Basics

### Function syntax
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

p user.keys -> [:name, :power]
puts user.keys -> name
                  power
```


