# projet2_daar : Indexing CVs using ELK

Project : Indexing CVs in Elasticsearch

UE : DAAR

Group mermbers:
- Wassim AROUI : 
- Nazim BENRABAH : https://github.com/nazim-benrabah

Class : M2 RES ALT/INSTA


----------------------------------------------------------------------------------------------------------
Requirements :

- Install Python
- Preferably install Docker
- pip install django
- pip install elasticsearch
- pip install nltk
- pip install docx2txt
- pip install pdfminer.six
- pip install json or jsonlib

------------------------------------------------------------------------------------------------------------------------ 
Step 1 : Run the ELK stack using docker

Unzip elastic_dar_windows.zip if you are a Windows user otherwise unzip elastic_daar_linux.zip if you a re a Linux or Mac user

Open terminal in /elastic_daar/run_elk_stack  and tap : docker-compose up

this will run Elasticsearch, Kibana, and Logstash in one commande at port 9200, 5601, and 5000 respectively.

Wait a few moment and make sure that elasticsearch and Kibana are ready by opening in browser : localhost:9200  and  localhost:5601

#####################
USERNAME : elastic  #
PASSWORD : changeme #
#####################

-------------------------------------------------------------------------------------------------------------------------
Step 2 Configure logstash in Kibana

Open Kibana --> management --> stack management --> Kibana --> index patterns --> name your pattern : logstash* --> next step --> time filter : I don't wan't to use time filer --> create index pattern --> go to Observability --> logs --> settings --> name your logs --> log indices : logstash* --> Apply --> you can now observe your logs in streams.

these logstash config is saved even if you restart your stack, so you don't need to reconfigure

-------------------------------------------------------------------------------------------------------------------------
Step 3 Run App

Go to elastic_daar/elastic and tap : python ./manage.py runserver

open browser on : localhost:8000

Choose your files and upload (visualise logs on Kibana --> logs --> streams)

-------------------------------------------------------------------------------------------------------------------------

Step 4 do queries on Kibana or Postman :



