
Notes of Logstash Config
========================

### Migrating Elasticsearch to Another Elasticsearch (sample-01.config)
	input {
  		elasticsearch {
   			hosts => "192.168.56.10:9200"
	 		index => "*" 
 			docinfo => true
  				}
		}

	output {
		elasticsearch { hosts => ["localhost:9200"] 
			index => "%{[@metadata][_index]}"
			document_type => "%{[@metadata][_type]}"
			document_id => "%{[@metadata][_id]}"
				}
		}

### Migrate Data with Range Query
