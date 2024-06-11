FROM python:3.10-slim-buster

# Working directory within the container
WORKDIR /backend-flask

# Copies the txt file from outside the container to inside the container
# Requirements.txt contains libraries we need to install to run the app
COPY requirements.txt requirements.txt

# Install within the container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside the container -> Inside the container
# . means everything in the current directory
# first period  - /backend-flask (outside container)
# second period - /backend-flask (inside container)
COPY . .

# Set environment variable (Env Vars)
# Inside container and will remain set when container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]