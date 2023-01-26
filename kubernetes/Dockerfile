FROM quay.io/fedora/python-39

ENV PYTHONPATH=.

WORKDIR /app/
COPY requirements.txt /app/
RUN pip install -r /app/requirements.txt
COPY wsgi.py /app/
COPY selinon_api /app/selinon_api/
ENTRYPOINT ["gunicorn", "wsgi:application", "--bind=0.0.0.0:8080", "--access-logfile=-"]
