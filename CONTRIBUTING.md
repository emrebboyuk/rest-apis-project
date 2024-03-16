# CONTRIBUTING

## How to run the Dockerfile locally

```angular2html
docker build -t flask-smorest-api .
docker run -dp 5000:5000 -w /app -v "$(pwd):/app" flask-smorest-api sh -c "flask db upgrade && flask run --host 0.0.0.0"
docker run -w /app rest-apis-flask-smorest-rq sh -c "rq worker -u <insert your Redis url here> emails"
docker run -p 5000:5000 rest-apis-flask-smorest-rq sh -c "flask run --host 0.0.0.0"
```