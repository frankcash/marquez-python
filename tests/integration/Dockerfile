FROM python:3.6

RUN apt-get update && apt-get install -yq --no-install-recommends \
    iptables
RUN pip install pytest requests
COPY . /marquez-python

RUN cd marquez-python && \
    python setup.py sdist && pip install .

COPY ./tests/integration/integration_test.py .
CMD python -m pytest -s -v ./integration_test.py
    