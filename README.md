### Testing Virtuoso docker instance for Geolink

#### Acquiring the image from Docker-hub:
```
docker pull tenforce/virtuoso:1.3.1-virtuoso7.2
```


#### Getting started with the image:
```
docker run --name gl-virtuoso \
	-p 8890:8890 -p 1111:1111 \
	-e DBA_PASSWORD=myDbaPassword \
     	-e SPARQL_UPDATE=true \
     	-e DEFAULT_GRAPH=http://www.example.com/my-graph \
     	-v /local/path/to/virtuoso/db:/data \
	-d tenforce/virtuoso:1.3.1-virtuoso7.2`
```
- note: For running the container on Mac, you might have to add this `/local/path/to/virtuoso/db` to the list of mounted directories, because Docker tries to comply with Apple's filesystem sandbox guidelines. 


#### Defaults
| UserName | Default Password |	Usage 									 |
|----------|------------------|--------------------------------------------------------------------------|
| dba      | dba   	      | Default Database Administrator account.					 |
| dav      | dav	      | WebDAV Administrator account.						 |
| vad      | vad   	      | WebDAV account for internal usage in VAD (disabled by default).		 |
| demo     | demo  	      | Default demo user for the demo database. This user is the owner of the Demo catalogue of the demo database. |
| soap     | soap  	      | SQL User for demonstrating SOAP services.				 |
| fori     | fori  	      | SQL user account for 'Forums' tutorial application demonstration in the Demo database. |
