
'''change permission'''


sudo chmod -R 777  <mkdir><fileName>




'''notesDockerTutorial'''


$Docker images
$Docker ps



docker-compose.yml
  - blue print  | instructions on the docker build up


'''skeleton of <docker-compose.yml>'''

$image -> must be the same as the image
$volume -> to be store // mkdir file must be created
$net -> will be binded
$permssion must be changed to $PWD

version: '3'
services:
  jenkins:
    container_name: jenkins
    image: jenkins
    ports:
      - "8080:8080"
    volumes:
      - $PWD/jenkins_home:/var/jenkins_home
    networks:
      - net
networks:
  net:



'''overwrite the permissions'''
$Excecute .yml without chmod 777
''' will container the pasw'''
$docker logs -f jenkins
'''to stop'''
$docker-compose stop
''' to restart'''
$docker-compose restart jenkins
'''do delete the image but not the VOLUME'''
$docker-compose down
'''create the service'''
docker-compose up -d
''' docker runs on localhost:8080'''
$http://localhost:8080/




''look up inside the docker container'''
docker exec -ti jenkins bash
