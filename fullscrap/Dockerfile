FROM tboquet/quickscrap

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get install -y postgresql postgresql-contrib libpq-dev build-essential \
    libssl-dev libffi-dev

RUN pip install psycopg2

CMD ["/bin/bash"]
