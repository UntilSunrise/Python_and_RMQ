# Up RabbitMQ
## Steps
* First what do you need install docker, if you don't have - follow [this link](https://docs.docker.com/engine/install/centos/)  
* Second: the following create a [dockerfile](https://github.com/UntilSunrise/Python_and_RMQ/blob/master/docker/Dockerfile) and run the build with this command:
  ```
  docker build -t rabbitmq-container .
  ```
  After you need to run broker:
  ```
  docker run -d --name rabbitmq-instance -p 5672:5672 -p 15672:15672 rabbitmq-container
  ```
  Now, you can check it:
  ```
  docker ps -a
  ```
  And get a results:
  ```
  [root@localhost rabbitmqpy]# docker ps -a
  CONTAINER ID   IMAGE                COMMAND             CREATED          STATUS          PORTS                                                                                      NAMES
  d7051c741464   rabbitmq-container   "rabbitmq-server"   28 seconds ago   Up 27 seconds   0.0.0.0:5672->5672/tcp, :::5672->5672/tcp, 0.0.0.0:15672->15672/tcp, :::15672->15672/tcp   rabbitmq-instance
  ```
* Third: you need create two files: [send.py](https://github.com/UntilSunrise/Python_and_RMQ/blob/master/docker/python_files/send.py) [receive.py]() and run it:
  This shows the output of all commands individually with subsequent file changes:
  ```
  [root@localhost rabbitmqpy]# python3 send.py
  [x] Sent 'Hello World!'

  [root@localhost rabbitmqpy]# python3 receive.py
  [*] Waiting for messages. To exit press CTRL+C
  [x] Received b'Hello World!'
  [x] Received b'Hello World!'
  ^CInterrupted
  ```
