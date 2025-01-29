FROM python:3.9-slim

# Set up working directory
WORKDIR /app

# Install necessary packages
RUN apt-get update && apt-get install -y build-essential > /dev/null 2>&1

# Copy project files
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Run Django migrations
RUN python manage.py migrate

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
