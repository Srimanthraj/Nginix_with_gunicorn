FROM python:3.8-alpine

ENV PYTHONUNBUFFERED 1

# Create and activate the virtual environment
RUN python -m venv /django/myproject
ENV PATH="/django/myproject/bin:$PATH"

WORKDIR /django

# Copy requirements separately to leverage Docker cache
COPY requirements.txt requirements.txt

# Upgrade pip and install requirements
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy the rest of the application code
COPY . .

# Set any additional configuration or startup commands as needed
