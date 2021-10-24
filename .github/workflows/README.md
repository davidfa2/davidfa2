The first process is the establishment environment of ubuntu
jobs:
 build:
 runs-on: ubuntu-latest
 
  The second step is to pull  the pull "lvthillo/python-flask-docker" from dockerhub 
name: docker pull
   run 
        docker run --name my-container -d -p 8080:8080 lvthillo/python-flask-docker
    
  Run and up the app on port 8080
 name: docker run
   run
        docker run --name my-container -d -p 8080:8080 lvthillo/python-flask-docker
        
   run the commend for geeting thr IP from the image app
           name: docker output IP  
   run 
            docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container
            
   getting the hostname from the runing image 
   
   run 
        docker inspect -f '{{ .Config.Hostname }}' my-container
        
        next steps is run the Project.yml repo on git Actions and verify that  all the commands running without errors
