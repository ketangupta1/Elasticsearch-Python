# Elasticsearch-Python
Run elasticsearch with python

## Python Setup
- First install elasticsearch and kibana on your system.
- Install elasticsearch module using pip3.

      pip3 install elasticsearch
- Connect to elasticsearch cluster.

      from elasticsearch import Elasticsearch

      ELASTIC_PASSWORD = "<password>"
      # Create the client instance
      client = Elasticsearch(
          "https://localhost:9200",
          ca_certs="/path/to/http_ca.crt",
          basic_auth=("elastic", ELASTIC_PASSWORD)
      )

      # Successful response!
      client.info()
- 
