
![Docker Automated build](https://img.shields.io/docker/automated/carlosfrutos/streamlit-app)
![Docker Pulls](https://img.shields.io/docker/pulls/carlosfrutos/streamlit-app)

# Description
This repository contains a docker image that allows running streamlit web application. It can be used to test the application and/or deploy to a cloud service like Google Cloud, Heroku, Amazon AWS
 
# Fork motivation
I forked to update the Python (version 3.9) and streamlit (version 1.11.0) to avoid several errors I had with forms and imports:

```
AttributeError: module ‘streamlit’ has no attribute ‘form’
```
```
import error cannot import name 'noreturn' streamlit
```

Also all dependency versions are fixed now to avoid future incompatibilities.

The rest of the functionality stays unchanged.

# Run the docker container
Simply enter the following command to run your application
```
docker run -ti --rm carlosfrutos/streamlit-app:latest
```

**Local development**
 - Mount your working folder in the container 
  ```
  docker run -ti --rm -v $(pwd):/app carlosfrutos/streamlit-app
  ```

 - If your main file name is different to  `main.py` (e.g. `app.py`)
 ```
 docker run -ti --rm -v $(pwd):/app carlosfrutos/streamlit-app:latest streamlit run name_main_file.py
 ```

- To access the docker container in the bash mode
```
docker run -ti --rm carlosfrutos/streamlit-app:latest bash
```

# Build docker image
You can build this docker image from a dockerfile using this command
```
docker build -t carlosfrutos/streamlit-app:latest .
```





