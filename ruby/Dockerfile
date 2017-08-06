### This will be my container for running rails applications ###
### The first application run here will be my bookmarks app  ###

FROM ruby:2.4-alpine

MAINTAINER inovakov@gmail.com

# musl-dev is required for building nokogiri
# g++ is required for therubyracer

RUN apk update && apk upgrade && apk add make && apk add musl-dev && apk add g++ \
    && apk add git && apk add postgresql-dev && apk add nodejs \
    && apk add bash && apk add nano \
    && gem update && gem cleanup

RUN git clone https://github.com/ro-tex/bookmarks.git /home/bookmarks && cd /home/bookmarks && bundle install

# TODO Find out how to automatically start a service with the container startup.
# ENTRYPOINT cd /home/bookmarks && rails s -e=production -d
# CMD ["cd /home/bookmarks && rails s -e=production"]

# build command:    docker build --rm -t inovakov/ruby /vagrant/ruby
# run command:      docker run -it -p 3000:3000 --name bms inovakov/ruby /bin/bash
# semi-auto:        docker run -d -p 3000:3000 --name bms inovakov/ruby /bin/bash -c "cd /home/bookmarks && rails s -e=production"
