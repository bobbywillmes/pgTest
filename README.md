# PostGreSQL Simple Setup

Running a simple Rails app using PostgreSQL locally.

1. Create new rails app: rails new awesomeNewApp --database=postgresql
2. Install [pgAdmin for Windows](https://www.postgresql.org/download/windows/)

## In pgAdmin

3. Create db user. Right click Login/Group Roles > Create > Login/Group Role... Fill in Name: pgTest_user, (then on the definition tab) Password: password
4. Create databases. Right click Databases > Create > Database... Database: pgtest_development. Then again for pgtest_test.
5. Add user to databases. In Browser on left, right click on pgTest_development > Properties... On the Default Privileges tab, Add row, then set grantee (pgTest_user) & privileges (All). Then Save. Do same for pgtest_test.

## In Rails app / code editor

6. Configure database.yml: Add the following three lines under development & test: host: 127.0.0.1, username: pgTest_user & password: password
7. Create scaffold to have application / data to work with. Run command: rails g scaffold Recipe title:string instructrions:text
8. Add route for recipes. On config/routes.rb add the following line: resources :recipes
9. Start server by running: rails s
10. Browse to /recipes to View / Add / Delete recipes
