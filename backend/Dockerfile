FROM python:3.10-slim


WORKDIR /app

# Required for New Relic
ENV NEW_RELIC_CONFIG_FILE=newrelic.ini
ENV NEW_RELIC_APP_NAME="LMS System - Backend"
ENV NEW_RELIC_HOST=collector.eu01.nr-data.net

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 4000
# CMD ["python", "app.py"]
# The lab requires running the app through the newrelic-admin wrapper
CMD ["newrelic-admin", "run-program", "python", "app.py"]
