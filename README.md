Ruby on Rails connecting with MongoDB
---------------------------------------
To run the project:
	
	>bundle install
	>mongod --config c:/mongo/bin/mongodb.config {start the mongodb server}
	>rails s {start rails server}
	
Goto browser & localhost:3000 {Default port is 3000}



-----------------------------------------------------
To create the project yourself
-----------------------------------------------------
1) Create new rails app
	
	>rails new mongo_demo

2) go into the project directory i.e. mongo_demo	
   Edit the Gemfile, add mongo_mapper & bson_ext gem
	
	.. {under gem rails '3.2.2' write}
		gem 'mongo_mapper'
		gem 'bson_ext'
	..
	
	Save the Gemfile & go back to command prompt
	
3) Install the new gems
	
	>bundle install
	
4) Generate a scaffold i.e. MVC for an object, say messages in our case
	
	>rails g scaffold messages message:string --orm mongo_mapper

5) Remove the default index file that rails creates i.e. ..public/index.html {Remove index.html}
   
		Change the default root to your new message view
		i.e. set default path to ..app/views/messages/index.html.erb {.erb cause it has ruby embedded in it :) }
		
		to do that goto ..config/routes.rb
		after resources: 'messages'
		add this line: root to: 'messages#index' {it'll make the index page the root of your application}
		
6) Create a basic mongo confguration file i.e. ..config/mongo.yml
	
		>rails g mongo_mapper:config {this command will create the file}
	
7) Start your mongo server {make sure you start the mongodb server first}
	
		>rails s {start the rails server}
	
8) Your application is ready to run
		ENJOY!!!
