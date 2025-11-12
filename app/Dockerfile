FROM python:3.12-slim

WORKDIR /app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# boto3 will use IMDSv2 on EC2 for credentials via instance profile
COPY . ./
EXPOSE 8080
CMD ["gunicorn", "-c", "gunicorn.conf.py", "wsgi:app"]