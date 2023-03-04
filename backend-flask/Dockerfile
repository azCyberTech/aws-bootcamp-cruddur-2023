#FROM python:3.10-slim-buster
# Updated to python:3.11.2-slim-buster because 3.10 game me error "/bin/sh: 1: [: missing ] docker"
FROM python:3.11.2-slim-buster
# Inside Container
# Make a new foler "backend-flask" inside container
WORKDIR /backend-flask

# Copy requirements.txt file from outside Container to inside Container
# The txt file contains the libraries required to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Copy everything from outsdie the Container to inside the Container
# Period (.) means everything in the current directory
# First (.) indicates everying inside /backedn-flask (outside of container)
# Second (.) indicates everying inside /backedn-flask (inside of container)
COPY . .

# Set Environment Variables (Env Vars)
# Inside container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]