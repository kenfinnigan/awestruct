FROM ruby:2.1

VOLUME /opt/jboss/website

# Set the AWESTRUCT_VERSION env variable
ENV AWESTRUCT_VERSION 0.5.6.beta8

RUN gem install awestruct -v $AWESTRUCT_VERSION

WORKDIR website

# Expose the ports we're interested in
EXPOSE 4242

# Set the default command to run on boot
CMD ["bundle", "exec", "awestruct", "-d"]
