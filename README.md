# 13-e-commerce

## Description
This is a back-end application for e-commerce businesses to house their inventory data. The data sync is done thru the sequelize npm package and the database is written in SQL using PostgreSQL. As this is a back-end application, users must link it to some sort of front-end to make it easier for end users to view the database. Insomnia is an optional install along with this app because it provides an easy way to check api routes and data. 

The hope is that this will allow any business to house their inventory data in a database which will keep that data organized and safe from threat. With cyberattacks getting much more prevalent, and SQL injection attacks at the top of that threat list, it is very important to house your data securely.

## Usage
Users must first install PostgreSQL and all it's dependencies before using this application. Be sure to make a note of your login credentials as they are required for this app. After ensuring you have installed PostgreSQL, it is recommended that the user creates a `.env` file in the root folder and house their sensitive PostgreSQL login information there. This can be done by adding login credentials below and copy & pasting this into the `.env`:

`DB_NAME='ecommerce_db'
DB_USER='postgres'
DB_PASSWORD='YOUR_PASSWORD_HERE'`

For the first-time use of this application, users must set up their schema.sql. This can be done by navigating to the integrated terminal in your code editor (making sure to target the root folder) and typing in the following:

`psql -U postgres`

Here you will be prompted to input your PostgreSQL password. Then type the following:

`\i db/schema.sql`

This will initialize the ecommerce_db (users may opt to change the name of their database to whatever they would like by replacing DB_NAME in the .env and in the schema.sql files). Users can exit the PostgreSQL input by typing `\q` which will return them to the integrated terminal. The next step is optional. Users can populate their database with seed data by typing the following into the integrated terminal:

`npm run seed`

Else, the user must begin inputting their own data into the database, either thru Insomnia or thru some other front-end. Once the database has been initialized, the user can check the api routes thru Insomnia by creating a new collection and then creating a new http request. All CRUD operations are included in this application, so users can READ all data, READ data by ID, CREATE new data, UPDATE data by ID and DELETE data by ID for each of the data tables (categories, products, tags).
