jobs:
  build:
  # it is run on ubuntu #
    runs-on: ubuntu-latest
  # now is get the image from dokerhub#
    steps:
    - name: docker pull
      run: |
        docker pull lvthillo/python-flask-docker
    - name: ## run the cotener nemd "my-container " on port 8080 ##
      run: |
        docker run --name my-container -d -p 8080:8080 lvthillo/python-flask-docker
    - name: ##docker output IP ##
      run: |
        docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container
    - name: ##docker output  hostname##
      run: |
        docker inspect -f '{{ .Config.Hostname }}' my-container
