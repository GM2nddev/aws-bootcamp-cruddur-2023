FROM python:3.10-slim-buster

# Inside Container
# make a new folder inside container
WORKDIR /backend-flask

# Outside Container to Inside Container
# contains library for install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container to Inside Container
# 1st period . everything -/backend-flask (outside container)
# 2nd period . /backend-flask (inside container)
COPY . .

# Set Envirnement Variables (Env Vars)
# Inside Container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]