# docker-nginx-uwsgi-flask README
ML enpoint deployment using `Docker` <img src="https://upload.wikimedia.org/wikipedia/en/thumb/f/f4/Docker_logo.svg/120px-Docker_logo.svg.png" alt="Docker" height="5%" width="5%">. `Flask` [<img src= "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Flask_logo.svg/120px-Flask_logo.svg.png" alt="Flasklogo" height="5%" width="5%" title="Flask">](https://github.com/pallets/flask) as API server, `NGINX` [<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Nginx_logo.svg/120px-Nginx_logo.svg.png" alt="NGINX" height="5%" width="5%">](https://hg.nginx.org/nginx) and `uWSGI` [<img src="https://www.fullstackpython.com/img/logos/uwsgi.png" alt="uWSGI" height="5%" width="5%">](https://github.com/unbit/uwsgi) for request management.
ML details is [available at](https://github.com/tamjid-ahsan/capstone_customer_churn).

___ 
### useful commands

```bash
docker-compose build # build containers
docker-compose up -d # run containers in detached mode 
docker-compose up --build # rebuild 
docker-compose images # all images built
docker-compose ps # show running processes

# Stop services only
docker-compose stop

# Stop and remove containers, networks..
docker-compose down 

# Down and remove volumes
docker-compose down --volumes 

# Down and remove images
docker-compose down --rmi <all|local> 

sudo ss -tulpn | grep LISTEN # list all used ports and process associated
sudo killall apache2 # kill a process if it using a port
```
- peek into images | containers
    - [dive](https://github.com/wagoodman/dive)

## References
- [command](https://www.cyberciti.biz/faq/unix-linux-check-if-port-is-in-use-command/)

___
contact: <a href="mailto:tamz888@yahoo.com">tamz888@yahoo.com</a> [<img src="./flask/app/data/TAlogo1.png" alt="TA" height="3%" width="3%">](http://linkedin.com/in/tamjidahsan/)
___

## TODO:
- create a new image from multiple dockerfile and docker-compose to a single image {check if is it is possible?}
- deep dive into docker and docker-compose
- secure connection: SSL, 443 in nginx
- add architechture diagram

___
**test this server** ausing this curl command after using docker for deployment.
```bash
curl --location --request POST 'http://localhost:5000/predict' --header 'Content-Type: application/json' --data-raw '{"Customer_Age": 45, "Gender": "M", "Dependent_count": 3, "Education_Level": "High School", "Marital_Status": "Married", "Income_Category": "60K_to_80K", "Card_Category": "Blue", "Months_on_book": 39, "Total_Relationship_Count": 5, "Months_Inactive_12_mon": 1, "Contacts_Count_12_mon": 3, "Credit_Limit": 12691.0, "Total_Revolving_Bal": 777, "Avg_Open_To_Buy": 11914.0, "Total_Amt_Chng_Q4_Q1": 1.335, "Total_Trans_Amt": 1144, "Total_Trans_Ct": 42, "Total_Ct_Chng_Q4_Q1": 1.625, "Avg_Utilization_Ratio": 0.061}'
```

```bash
curl --location --request POST 'http://localhost/predict' --header 'Content-Type: application/json' --data-raw '{"Customer_Age": 45, "Gender": "M", "Dependent_count": 3, "Education_Level": "High School", "Marital_Status": "Married", "Income_Category": "60K_to_80K", "Card_Category": "Blue", "Months_on_book": 39, "Total_Relationship_Count": 5, "Months_Inactive_12_mon": 1, "Contacts_Count_12_mon": 3, "Credit_Limit": 12691.0, "Total_Revolving_Bal": 777, "Avg_Open_To_Buy": 11914.0, "Total_Amt_Chng_Q4_Q1": 1.335, "Total_Trans_Amt": 1144, "Total_Trans_Ct": 42, "Total_Ct_Chng_Q4_Q1": 1.625, "Avg_Utilization_Ratio": 0.061}'
```
