FROM jboss/base:latest

VOLUME /opt/jboss/website

# Set the AWESTRUCT_VERSION env variable
ENV AWESTRUCT_VERSION 0.5.6.beta8

# Use root user to install software
USER root

# Install necessary packages
RUN yum -y install ruby && yum clean all
RUN gem install bundler
RUN gem install awestruct -v $AWESTRUCT_VERSION

# Switch back to jboss user
USER jboss

# Expose the ports we're interested in
EXPOSE 4242

# Set the default command to run on boot
CMD ["bundle", "exec", "awestruct", "-d"]
