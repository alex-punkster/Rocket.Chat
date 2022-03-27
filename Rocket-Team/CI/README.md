#### CI
Build_and_Push.yml - this is a pipeline that build rocket.chat, builds a docker image from it and sends this image to Google Container Registry
docker-compose.yml - example of using a built image to run Rocket.Chat (docker-compose pull image from GCR)