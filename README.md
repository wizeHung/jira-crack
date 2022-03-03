# jira-crack
## tested on Version (8.19 , V8.21 , V8.22) bare or via docker image


#### check out the bottom, you can crack Jira Until year 2089 :D  <br />
install and start postgresql with these commands. 
```
 sudo apt-get update
 sudo apt-get install postgresql postgresql-contrib -y
 sudo update-rc.d postgresql enable
 sudo service postgresql start
 ```
 

after that switch to postgre user to make some changes to the database

``` sudo su - postgres
 psql
 postgres=# CREATE USER jiradbadmin WITH PASSWORD 'password';
 postgres=# CREATE DATABASE jiradb WITH ENCODING 'UNICODE' LC_COLLATE 'C' LC_CTYPE 'C' TEMPLATE template0;
 postgres=# GRANT ALL PRIVILEGES ON DATABASE jiradb TO jiradbadmin;
 \q
 logout
```

download jira software version 8.19.1 from this link and install it

```
wget https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-8.19.1-x64.bin
chmod a+x atlassian-jira-software-x.x.x-x64.bin
sudo ./atlassian-jira-software-x.x.x-x64.bin
```
it will ask you some questions, use ENTER to accept all but on the 8th question use n so jira doest run after installation
```
Installation of JIRA Software x.x.x is complete
Start JIRA Software 8.19.1 now?
Yes [y, Enter], No [n]
n
```
now we need to download a file and replace it inside jira config directory.
```
rm -f /opt/atlassian/jira/atlassian-jira/WEB-INF/lib/atlassian-extras-3.4.6.jar
cd /opt/atlassian/jira/atlassian-jira/WEB-INF/lib/
wget https://omwtfyb.ir/atlassian-extras-3.4.6.jar
```
restart jira 
```
. /opt/atlassian/jira/bin/start-jira.sh
. /opt/atlassian/jira/bin/stop-jira.sh
. /opt/atlassian/jira/bin/start-jira.sh
```

now go to yourip:8080 and you should see jira starting up.if it's not showing you anything just give it a few moments.
it takes some time for jira to start up.
proceed with the configuration and use the same values you used for postgre.
  when you see the license page use this code, wait a few minutes(it usually takes 2.3 minutes at this page).
  ```
AAAB6w0ODAoPeJyFU9Fu2jAUfc9XRNrLpikoTqG0lSwthHRjTYAldNL2ZtILuAtOdm1D+fuFQNS0dbNHn3Puvce+xx9ukduzTNmeZ5P+DRnckEt7kqQL23M9YgUITPFCjJkCekQc4jqeZwWFUCxTU7YFKnVZFqi+IFOFZKKXFduGD2PGc6NghmsmuKyb06RFpIA7wMmYJv5ilvpTx70m3rXresPB0ErDqRGfa8w2TMJrm1O9XQLOVvcSUNK+az1yZD0zWmLxoDPVOx4cWazUniG81VY3EgoEExmETyXHQzPTc9x+ZcqKeAZCvkOOQWbIy/rW36tBdnoeZIc7luv6OeyPVRWzA6jm4KeTuVQxrE50xXIJXX5fCtcIIDZFWQL2qnXwHVCF+tzgDWDu2Ja1+9X2SuSy3cIImvsapUJvkyKHoNBCUYd01b+Wnt99cSihjmUwi+MwCSZ+9MJ2h6we9j/ebKajqsnDA6+3Hk4XYTJPJmlosmVQtV29R3eaMhTlJ+Znlekj4zUmq28XTcbGn6eXz8mt9/Uc2Nb+jsk9BbcD/AOHZjK5dN2he3VxQRpP35jc0DjYB7eh9jPMhlL+vgvjwfxX/7BZDEZ9nZO9v0lG0f5v8lU8zpP7z3B1lwcxWcY/9mIUrSm1/gFvD663MC0CFQCG4BagN5AjwL2FjzdS/eyykN/ubwIUf5IhyjHiWlvd1S5IIUjh9Rye7H0=X02nb
  ```
  voala! jira's been activated for 5 months. after that you can just repeat these steps for another 5 months <br />
  i've tried contacting them to fix this but hasn't got a response yet  (: <br />
  if your still not able to crack jira with this code. it may have been banned by jira's Team. instead you can use this repo [atlassian-agent](https://gitee.com/pengzhile/atlassian-agent)  (all credits to him) and use atlassian-agent to generate a new license Code which will activate Jira until 2089.
thanks to Mr. Saeid Hosseini  for finding this repo.
