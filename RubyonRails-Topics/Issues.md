##Known Issues
There as been many instances where developing or learning Ruby on Rails on a Windows machine is at times, time consuming due to the nature of the trouble-shooting issues that arise. One issue that I think that is consistant is the configuration when you use RailsInstaller. 

#####The best way to fix this error is by the following

"Windows does not include zoneinfo files, so bundle the tzinfo-data gem" within the gemfile

To:
```ruby
   gem 'tzinfo-data', platforms: [:mingw, :mswin]
```
From:
```ruby
 gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw]
```
#####Other Issue

The other issue is when you install RailsInstaller for the first time and create a new rails app and you cannot access the Ruby Gems due to the nature of the SSL Certificate. This configuration will need to be added manually. 

Go into your C: drive access the  ssl_cert folder within the RailsInstaller 

    RailsInstaller/Ruby2.1.0/lib/ruby/rubygems/ssl_cert

Copy the **AddTrustExternalCARoot-2048.pem** from this link, [SSL upgrades on rubygems.org and RubyInstaller versions](https://gist.github.com/luislavena/f064211759ee0f806c88) by going to the section under; **Step 1: Obtain the new trust certificate** and add AddTrustExternalCARoot-2048.pem to the ssl_cert folder. Once that is added you should not have any problems with the Ruby Gems. 
