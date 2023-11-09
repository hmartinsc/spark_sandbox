# docker build -t spark_sandbox .
# docker run --name spark_container -d spark_sandbox
# docker run --name spark_container -d -v $(pwd)/code:/app/code spark_sandbox
# docker exec -it spark_container /bin/bash

FROM openjdk:8-jre-slim-buster

# Install Python 3.7
RUN apt-get update && apt-get install -y python3.7 python3-pip

# Install Pyspark
RUN pip3 install pyspark==3.1.2

# Set environment variables
ENV PYSPARK_PYTHON=python3.7
ENV PYSPARK_DRIVER_PYTHON=python3.7

# Copy your code to the container
COPY . /app

# Set the working directory
WORKDIR /app

CMD ["bash", "-c", "tail -f /dev/null"]
