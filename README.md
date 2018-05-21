# Semantic Mapping Service

The TOOP Semantic Mapping Service is a specific instantiation of the TNO Plasido platform for ontology-based integration of linked data sources.

It contains 2 specific containers:
- one for the Apache Jena Fuseki triplestore that contains the TOOP Common Semantic Model and its mappings to national data models, and
- one for the GRLC component that provides a REST-API with various GET operations that are translated to SPARQL queries on the Fuseki triplestore  

### How to start the TOOP Semantic Mapping Service
Execute the following steps:

- Make sure you have Docker, Docker Compose and Git installed.
- Git clone this Semantic Mapping Serivce repository to your computer.
- Open a shell and navigate to your `git clone` of the SMS.
- Copy the .env.default file to a .env file in the root directory of this local repository
- Add a Github API access token to it as indicated in the last lines of the .env.default file,
  which looks like: env_github_access_token=`<hexadecimal Github API token that has to be generated at Github>`
- If you don't have a Github API access token, you can also contact jack.verhoosel@tno.nl to get one

- Execute the following command: `docker-compose build fuseki grlc` and then `docker-compose up -d fuseki grlc`
- The SMS services Fuseki and GRLC will be started automatically, this might take a while (also when the command is already finished, it might still take a while for all the services to be started).
- Now you can access different services of SMS. In the browser open:

	- Apache Jena Fuseki: `http://localhost:3030`.
	- GRLC: `http://localhost:9001`.
	
Note that we assume your docker host is available on `localhost` (which is the case if you are using Docker for Linux or recent Docker for Windows and Mac)
If you want to use a different port number for the GRLC service, you can edit it in the .env file by changing `GRLC_PORT=9001` to `GRLC_PORT=<your-port>`

For any other questions, please contact jack.verhoosel@tno.nl
 