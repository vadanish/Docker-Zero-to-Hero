FROM ubuntu:20.04

# Set the working directory inside the container
WORKDIR /app

# Install required dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip

# Copy requirements.txt and install dependencies
COPY requirements.txt /app/
RUN pip install -r requirements.txt

# Copy the entire 'devops' directory into /app
COPY devops /app/devops

# Set the working directory to the devops folder where manage.py is likely located
WORKDIR /app/devops

# Entry point and default command
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





