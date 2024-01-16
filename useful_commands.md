 # docker commands
`docker build . -t turbofan1`

`docker build . -t adeb09/turbofan_be`

`docker build . -t adeb09/turbo_dash`

`docker run -it -p 8888:8888 --volume "$HOME/git/turbofan_prognostics":"/home/jovyan/work" turbofan1`

`docker run -it -d -p 8888:8888 --volume "$HOME/git/turbofan_prognostics":"/home/jovyan/work" turbofan1`

`docker run --name turbo_jupyter -d -p 8888:8888 --volume "$HOME/git/turbofan_prognostics":"/home/jovyan/work" turbofan1`

`docker run -it -p 8888:8888 -e JUPYTER_ENABLE_LAB=yes --volume "$HOME/git/turbofan_prognostics":"/home/jovyan/work" turbofan1`

`sudo docker run -it rwe_external_integrations_adeb services/econsent/medrio_consent_handler.py -p 8000:8000 -v /home/adeb@ConcertoHealth.AI/rwe_external_integrations/app:/app --env-file /home/adeb@ConcertoHealth.AI/rwe_external_integrations/.env`

# Streamlit commands
`docker run -it --rm -p 8501:8501 -v "$HOME/git/turbofan-dashboard/turbofan_dashboard":/turbofan_dashboard adeb09/turbo_dash`

**generalized command for streamlit docker image**\
`docker run -it -p 8501:8501 -v ~/workspace/streamlit-scripts:/app CONTAINER_NAME relative/path/to/script`

**run deployment repo**\
`docker run --name turbo_fast -d -p 80:80 --volume "$HOME/git/turbo_fast_app/app":"/app" turbofan_be`\
`docker run -d -p 80:80 --volume "$HOME/git/turbo_fast_app/app":"/app" adeb09/turbofan_be`

**run deployment w/reloading on code changes (only for development)**\
`docker run --name turbo_fast -d -p 80:80 --volume "$HOME/git/turbo_fast_app/app":"/app" turbofan_be /start-reload.sh`\
`docker run --name turbo_fast -p 80:80 --volume "$HOME/git/turbo_fast_app/app":"/app" turbofan_be`

**stop running container**\
`docker stop turbo_fast`

**mount a volume so code changes happen inside container right away**\
`docker run -it -v "$(pwd)/app:/app" turbofan_be bash`

**show all the running containers**\
`docker container ls`

**show all the images on your machine**\
`docker images ls`

**view logs for running container**\
`docker logs CONTAINER`

**removes stopped containers and dangling docker images**\
`docker system prune`

**docker build from a specific dockerfile**\
`docker build . -f Dockerfile.localdev -t rwe_external_integrations_adeb`




# Elastic Beanstalk CLI commands
**do this at the root level of your project repo (creates AWS Beanstalk config directories/files)**\
`eb init`

**create an environment for deployment**\
`eb create`

**SSH into an AWS EC2 instance that is hosting your deployed application for the ENVIRONMENT_NAME**\
`eb ssh ENVIRONMENT_NAME`

**terminate an environment**\
`eb terminate`



# Bash Remote Copy commands
`scp adeb@ConcertoHealth.AI@10.164.1.74:/home/adeb@ConcertoHealth.AI/secret.json ~`\
`scp ~/secret_updated1.json adeb@ConcertoHealth.AI@10.164.1.74:~`

# grep
`grep Whatyou'relookingfor whatfileyouwanttosearchin`

**grep manual in UNIX**\
`man grep`

**case insensitive search**\
`grep -i`

**line number for each hit in the file**\
`grep -n`

**any file in the directory to search**\
`grep *`

**recursively search directories within current directory and search every file there is**\
`grep -r`

**5 lines after**\
`grep -A`

**5 lines before**\
`grep -B`

**5 lines around**\
`grep -C`

**can grep the results of a grep**\
`grep blah blah | grep`

**can store results of a grep into a text file**\
`grep blah blah >> ~/file.txt`
