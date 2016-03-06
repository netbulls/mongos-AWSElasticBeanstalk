# mongos-AWSElasticBeanstalk

It's a docker image which allow you run mongos on AWS Elastic Beanstalk. Elastic Beanstalk doesn't support arguments for docker container, docker supports only env variables. So if you want to run mongos on Elastic Beanstalk you can do it executing command:
```
docker run \
  --name mongos \
  -e "CONFIG_SERVERS=cfg/server1:27019,server2:27019,server3:27019" \
  netbulls/mongos-awselasticbeanstalk
```

Example of Dockerrun.aws.json

```
{
	"AWSEBDockerrunVersion": 2,
	"containerDefinitions": [
		{
			"name": "mongos",
			"image": "netbulls/mongos-awselasticbeanstalk",
			"essential": true,
			"memory": 128,
			"environment": [
				{
					"name": "CONFIG_SERVERS",
					"value": "cfg/server1:27019,server2:27019,server3:27019"
				}
			]
		}
	]
}
```
