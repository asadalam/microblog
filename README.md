The flask mega tutorial by Miguel Grinberg. 
None of the code is mine, I only followed the blog to learn about flask. 
I have skipped a few sections which were not of interest to me. 
It also contains a docker file to deploy the whole app with just one command.

For running the docker image, say:

docker run --name alamasad84/microblog -d -p 8000:5000 --rm -e SECRET_KEY=my-secret-key \
    -e MAIL_SERVER=smtp.googlemail.com -e MAIL_PORT=587 -e MAIL_USE_TLS=true \
    -e MAIL_USERNAME=<your-gmail-username> -e MAIL_PASSWORD=<your-gmail-password> \
    --link mysql:dbserver \
    -e DATABASE_URL=mysql+pymysql://microblog:<database-password>@dbserver/microblog \
    --link elasticsearch:elasticsearch \
    -e ELASTICSEARCH_URL=http://elasticsearch:9200 \
    microblog:latest


Remember to allow for 3rd party authentication and access in your google settings


