# RCON-web  

RCON-web is a Ruby gem for managing Pavlov Shack servers via RCON in a Rails application.  

## Installation  

Add this gem to your Gemfile:  
```ruby
gem 'rcon-web', git: 'https://github.com/horse1jj/rcon-web.git'

```ruby

Then install it:

```ruby

bundle install

```ruby

# Usage

1. Initialize the RCON Client

```ruby
require "rcon-web"
```ruby

client = RconWeb::Client.new("127.0.0.1", 1234, "yourpassword")

```ruby

2. Authenticate
client.authenticate

3. Send RCON Commands

```ruby
puts client.send_command("Serverinfo")
```ruby

4. Close the Connection
client.close
Rails Integration

Create an initializer in config/initializers/rcon_web.rb:

```ruby
RCON_CLIENT = RconWeb::Client.new(ENV["RCON_IP"], ENV["RCON_PORT"], ENV["RCON_PASSWORD"])
```ruby

Now you can use 
```ruby

RCON_CLIENT.send_command("YourCommand") anywhere in your app.

```ruby
