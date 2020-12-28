FROM ubuntu:latest
RUN apt-get update -y
RUN apt-get install -y python3-pip python-dev build-essential
RUN pip3 install --upgrade pip

WORKDIR /monolith-service

COPY service/requirements.txt .
#Install dependencies listed in the requirements.txt file using pip3
RUN pip3 install -r requirements.txt

# Copy python source files and requirements file into container image
COPY service .

# Specify a listening port for the container
EXPOSE 80/TCP
# Run the monolith.py as the final step. We want this container to run as an executable. Looking at ENTRYPOINT and CMD for this?
ENTRYPOINT ["python3"]
CMD ["mythicalMysfitsService.py"]
