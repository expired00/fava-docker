# Dockerized Beancount & Fava
https://hub.docker.com/r/kaze00/fava
 - Based on python:3.10-slim
 - Nginx reverse proxy with Basic Authentication

 ## Docker Settings

 - Exposed Port
    - 80
- Required Variables
    - BEANCOUNT_FILE = Location of your .beancount ledger
    - BASIC_USERNAME = http basic authentication username
    - BASIC_PASSWORD = http basic authentication password

## Example

```
docker run -d -p 80:80 \
 --name fava \
 --restart=always \
 -v /path/to/ledger:/beancount \
 -e BEANCOUNT_FILE=/beancount/file.beancount \
 -e BASIC_USERNAME=Joe -e BASIC_PASSWORD=SuperStrongPassword1 \
 kaze001/fava:latest
 ```
