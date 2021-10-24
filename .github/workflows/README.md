The first process is the establishment environment of ubuntu
  * runs-on: ubuntu-latest
 
  * The second step is to pull  the  "lvthillo/python-flask-docker" app from dockerhub 
  pull docker pull lvthillo/python-flask-docker

  * Run and up the app on port 8080
  docker run --name my-container -d -p 8080:8080 lvthillo/python-flask-docker
        
  * run the commend for geeting thr IP from the image app 
   docker inspect -f '{{range .NetworkS ttings.Networks}}{{.IPAddress}}{{end}}' my-container
           
  * getting the hostname from the runing image
   docker inspect -f '{{ .Config.Hostname }}' my-container
        
        
  next steps is run the Project.yml repo on git Actions and verify that  all the commands running without errors
