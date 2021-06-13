---
layout: post
title:      "Make Your Own Gem"
date:       2021-06-05 08:26:55 -0400
permalink:  make_your_own_gem
---

Creating and publishing your own gem from Ruby CLI project is very simple. I'll show you to create a simple "Hello_World" gem.
    
I started with creating a Ruby file for my hello gem, and the gemspec file. If you want to publish yours, you'll need a new name for yours.
        
Code for the package is placed within the lib directory. The convention is to have one Ruby file with the same name as your gem, since that gets loaded when require 'hello' is run.
        
The code inside of lib/hello.rb is bare bones. It just makes sure that you can see some output from the gem:

    class Hello
      def self.hi
        puts "Hello world!"
      end
    end
    
The gemspec defines what’s in the gem, who made it, and the version of the gem. It’s also your interface to RubyGems.org. All of the information you see on a gem page (like jekyll’s) comes from the gemspec.

    Gem::Specification.new do |s|
      s.name        = 'hello'
      s.version     = '0.0.0'
      s.summary     = "Hello!"
      s.description = "A simple hello world gem"
      s.authors     = ["Nasrin Rahimi"]
      s.email       = '77.nasrin@gmail.com'
      s.files       = ["lib/hello.rb"]
      s.homepage    =
        'https://rubygems.org/gems/hello'
      s.license       = 'MIT'
    end
    
After we have created a gemspec, we can build a gem from it. Then we can install the generated gem locally to test it out.
        
    % gem build hello.gemspec
    
    Successfully built RubyGem
    Name: hello
    Version: 0.0.0
    File: hello-0.0.0.gem

    % gem install ./hello-0.0.0.gem
    
    Successfully installed hello-0.0.0
    Parsing documentation for hello-0.0.0
    Installing ri documentation for hello-0.0.0
    Done installing documentation for hello after 0 seconds
    1 gem installed
        
The final step is to require the gem and use it:

    % irb
    >> require 'hello'
    => true
    >> Hello.hi
    Hello world!
        
Now we can share hello with the rest of the Ruby community. Publishing your gem out to RubyGems.org only takes one command, provided that you have an account on the site. To setup your computer with your RubyGems account, you can run below command (where qrush should be replaced by your own username):
            
    $ curl -u nasrin https://rubygems.org/api/v1/api_key.yaml >
    ~/.gem/credentials; chmod 0600 ~/.gem/credentials

    Enter host password for user 'nasrin':
            
Once this has been setup, we can push out the gem:

    % gem push hello-0.0.0.gem
    Pushing gem to RubyGems.org...
    Successfully registered gem: hello (0.0.0)
        
Your gem will be available for installation by anyone less than a minute. You can see it on the RubyGems.org site or grab it from any computer with RubyGems installed:

    % gem list -r hello

REMOTE GEMS

    hello (0.0.0)

    % gem install hello

    Successfully installed hello-0.0.0
    1 gem installed
    
Thanks to awesome rubygems guides:
    
    https://guides.rubygems.org/make-your-own-gem/
    
To read more about Gem, please go to the link below:
    
    https://guides.rubygems.org/

Thanks for reading!



