FROM ubuntu:16.04

RUN apt-get update && apt-get install -y apt-utils firefox libglu1

# Called on first run of docker
ADD start.sh /start.sh
RUN chmod 0755 /start.sh


CMD ["/start.sh"]
