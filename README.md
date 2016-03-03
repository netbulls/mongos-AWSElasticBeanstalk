# mongos-AWSElasticBeanstalk

It's a docker image which allow you run mongos on AWS Elastic Beanstalk. Elastic Beanstalk doesn't support arguments for docker container, docker supports only env variables. So if you want to run mongos on Elastic Beanstalk you can do it executing command:
```
docker run \
  --name mongos \
  -e "CONFIG_SERVERS=cfg/server1:27071,server2:27071,server2:27071" \
  netbulls/mongos-awselasticbeanstalk
```
