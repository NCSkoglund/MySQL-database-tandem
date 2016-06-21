1. Initialize a mySQL server:

    ```
    $ mysql.server start
    Starting mySQL
      SUCCESS!
    ```
1. Start a mySQL server with in the terminal (by default there is no password):

    ```
    $ mysql -u root -p
    ```
2. Create a database called, `tandem`. For more information, visit this [great tutorial](https://www.digitalocean.com/community/tutorials/a-basic-mysql-tutorial):

    ```
    mysql> CREATE DATABASE tandem;
    ```
3. Open up the database:

    ```
    mysql> USE tandem;
    ```
4. Create account and specifiy privileges. Here, we will be creating an `admin` account with a password of your choice, connection from `localhost` and all access to the database, `tandem`. More information about users and privileges can be found [here](http://dev.mysql.com/doc/refman/5.7/en/adding-users.html "mysql Docs") AND [here](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql "Digital Ocean's How-to")

    ```
    mysql> CREATE USER 'tandem'@'localhost' IDENTIFIED BY 'your_password';
    mysql> GRANT ALL PRIVILEGES ON tandem.* TO 'tandem'@'localhost';
    ```
To see privileges on the account you've just created:

    ```
    mysql> SHOW GRANTS FOR 'tandem'@'localhost';
    ```

5. Save your newly created password to your machine's bash profile, to be accessed by config.js:

    ```
    export TANDEM_DB_PW='your_password'
    ```

