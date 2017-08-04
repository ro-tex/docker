### This will be my container for running rails applications ###
### The first application run here will be my bookmarks app  ###

FROM ruby:2.4-alpine

MAINTAINER inovakov@gmail.com

RUN apk update && apk upgrade && apk add bash && apk add make && apk add musl-dev && apk add gcc

RUN gem update && gem cleanup
