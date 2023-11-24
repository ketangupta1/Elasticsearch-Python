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
- Get the doc content:
  
        client.get(index="my_index", id="my_document_id")
- Delete the doc:
  
      client.delete(index="my_index", id="my_document_id")
- Search the doc using query:
  
      resp = client.search(index="my_index", query={"match_all": {}})
      print("Got %d Hits:" % resp['hits']['total']['value'])
      for hit in resp['hits']['hits']:
          print(hit)
- Update the doc:
  
      client.update(index="my_index", id="my_document_id", doc={
          "foo": "bar",
          "new_field": "new value",
      })
- Update the doc:

      doc = {
          'email': 'rajagupta@gmail.com'
      }
      resp = client.update(index="my_index", id="my_document_id", doc=doc)
      print(resp['result'])

