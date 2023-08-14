# Use centos7
FROM centos:7

# Install packages and updates
RUN yum -y update && \
    yum -y install epel-release && \
    yum -y install rabbitmq-server && \
    yum clean all

# Open ports for RabbitMQ
EXPOSE 5672 15672

# Start RabbitMQ
CMD ["rabbitmq-server"]
