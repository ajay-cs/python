## CSV file to mysql database - using python 2.7.5
#### 1) Make sure you have installed Development Tools
![1.png](1.png?raw=true "Title")

#### 2) Check hostname is resolving if not please add the local host entry.
![2.png](2.png?raw=true "Title")

#### 3) Update your system for all fixes
![3.png](3.png?raw=true "Title")

#### 4) Check firewall status
![4.png](4.png?raw=true "Title")

#### 5) Stop the firewall if running
![5.png](5.png?raw=true "Title")

#### 6) Recheck the firewall status
![6.png](6.png?raw=true "Title")

#### 7) Check the selinux status
![7.png](7.png?raw=true "Title")

#### 8) If selinux status is enabled, please set in disabled in file the /etc/selinux/config
![8.png](8.png?raw=true "Title")

#### 9) We are going to install the mysql community version, so please the mysql repo from http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm
![9.png](9.png?raw=true "Title")

#### 10) Install the mysql noarch.rpm, it will add the new repo on your system
![10.png](10.png?raw=true "Title")

#### 11) Update the newly added repo and dependencies
![11.png](11.png?raw=true "Title")

#### 12) Mysql installation
![12.png](12.png?raw=true "Title")

#### 13) Start the mysql server
![13.png](13.png?raw=true "Title")

#### 14) Check the mysql server status
![14.png](14.png?raw=true "Title")

#### 15) Follow the secure installation
![15.png](15.png?raw=true "Title")
![16.png](16.png?raw=true "Title")
![17.png](17.png?raw=true "Title")

#### 16) Check if you can login in mysql server with updated password
![18.png](18.png?raw=true "Title")

#### 17) By default pip not included with python2.7 and CentOS Base repo.
![19.png](19.png?raw=true "Title")

#### 18) Add EPEL repo to get pip, pip help to install python modules.
![20.png](20.png?raw=true "Title")

#### 19) Install the pip package
![21.png](21.png?raw=true "Title")

#### 20) Check Pip is working fine
![22.png](22.png?raw=true "Title")

#### 21) Check pip version 
![23.png](23.png?raw=true "Title")

#### 22) Create a database
![24.png](24.png?raw=true "Title")
![26.png](26.png?raw=true "Title")

#### 23) Create table and make sure you have same number of field as in  CSV.
![27.png](27.png?raw=true "Title")

#### 26) Install the MySQL-Python module
![28.png](28.png?raw=true "Title")

#### 27) Make the CSV file, here we have replaced spaces with comma
![29.png](29.png?raw=true "Title")

#### 28) Write the python script to import the data from csv to mysql - csv_mysql.py
    #!/usr/bin/python
    import MySQLdb
    import csv

    db = MySQLdb.connect(host="pydesk", # The Host
                          user="root", # username
                          passwd="x", # password
                          db="storage") # name of the data base

    cursor = db.cursor()
    Query = """ LOAD DATA LOCAL INFILE 'result.csv' INTO TABLE
    storage FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"' ESCAPED
    BY '"' Lines terminated by '\n' IGNORE 1 LINES """

    cursor.execute(Query)
    db.commit()
    cursor.close()

#### 29) run the python code
![29_.png](29_.png?raw=true "Title")

### 30) login in mysql and check the data. sample data..!!
![30.png](30.png?raw=true "Title")

                                                Thank you..!!
