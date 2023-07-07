# MuscleApp


## Installation


### Using Docker Compose (recommended)

1. Clone the repository:
  ```shell
   git clone https://github.com/Baptiste-Ferrand/MuscleApp-Front.git && cd MuscleApp-Front
   ```

2. Generate JWT Keys:
Generate a key using the following command:
```bash
openssl rand -base64 32
```
Export the key as an environment variable:

3. Export your environment variables:

   ```shell
   export DB_NAME=
   export DB_USER=
   export DB_PASSWORD=
   export DB_HOST=db
   export DB_PORT=3306
   export API_PORT=
   export SECRET_KEY=
   ```
Do not edit DB_HOST and DB_PORT variables. They are set by docker-compose.yml file. \
DB_NAME, DB_USER and DB_PASSWORD are used both by API and DB containers so if you update one of them you don't have any other changes to do. 
 
API_PORT is the port on which the API will be available. So when you will make a request to the API, you will have to use this port on your machine. 


## Build Setup

```bash
docker compose pull && docker compose up
```
