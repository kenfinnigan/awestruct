FROM jboss/base:latest

VOLUME /opt/jboss/website

# Set the AWESTRUCT_VERSION env variable
ENV AWESTRUCT_VERSION 0.5.5

# Use root user to install software
USER root

# Install necessary packages
yum -y install ruby && yum clean all
gem install bundler
gem install awestruct -v $AWESTRUCT_VERSION

# Switch back to jboss user
USER jboss

# Expose the ports we're interested in
EXPOSE 4242

# Set the default command to run on boot
CMD ["bundle", "exec", "awestruct", "-d"]
