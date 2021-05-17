FROM airbyte/integration-base-python:0.1.7

# Bash is installed for more convenient debugging.
RUN apt-get update && apt-get install -y bash && rm -rf /var/lib/apt/lists/*

ENV CODE_PATH="source_airtable"
ENV AIRBYTE_IMPL_MODULE="source_airtable"
ENV AIRBYTE_IMPL_PATH="SourceAirtable"

WORKDIR /airbyte/integration_code
COPY $CODE_PATH ./$CODE_PATH
COPY setup.py ./
RUN pip install .

LABEL io.airbyte.version=0.1.0
LABEL io.airbyte.name=airbyte/source-airtable
