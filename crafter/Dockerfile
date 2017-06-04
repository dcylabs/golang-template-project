FROM debian:jessie
MAINTAINER Dcylabs <dcylabs@gmail.com>

# Installing all build tools 
RUN apt-get update && apt-get install -y golang ca-certificates

# Setting up environment 
RUN mkdir -p /var/crafter
WORKDIR /var/crafter 
RUN mkdir -p /var/crafter/golang/src
ENV GOPATH '/var/crafter/golang'
ENV CGO_ENABLED 0

CMD set -- $args && export GOOS=${1} && cp -R /var/crafter/src /var/crafter/golang/src/app && go build -o /var/crafter/dist/app -a -installsuffix cgo -tags netgo app 