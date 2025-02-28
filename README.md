# Elasticsearch & Kibana Cheatsheet

## **Elasticsearch Overview**
Elasticsearch is a distributed search and analytics engine used for full-text search, log analysis, and real-time data processing.

---

## **Elasticsearch Setup & Basic Commands**
```sh
elasticsearch --version          # Check Elasticsearch version
systemctl start elasticsearch    # Start Elasticsearch service
systemctl stop elasticsearch     # Stop Elasticsearch service
systemctl restart elasticsearch  # Restart Elasticsearch service
```

### **Check Cluster Health**
```sh
curl -X GET "localhost:9200/_cluster/health?pretty"
```

### **List Available Indices**
```sh
curl -X GET "localhost:9200/_cat/indices?v"
```

### **Create an Index**
```sh
curl -X PUT "localhost:9200/my_index?pretty"
```

### **Index a Document**
```sh
curl -X POST "localhost:9200/my_index/_doc/1" -H "Content-Type: application/json" -d '{"name": "example", "value": 100}'
```

### **Search Documents**
```sh
curl -X GET "localhost:9200/my_index/_search?q=name:example&pretty"
```

### **Delete an Index**
```sh
curl -X DELETE "localhost:9200/my_index?pretty"
```

---

## **Kibana Overview**
Kibana is a visualization and analytics tool for Elasticsearch, used to explore data and create dashboards.

---

## **Kibana Setup & Basic Commands**
```sh
kibana --version                # Check Kibana version
systemctl start kibana          # Start Kibana service
systemctl stop kibana           # Stop Kibana service
systemctl restart kibana        # Restart Kibana service
```

### **Access Kibana UI**
- Default URL: `http://localhost:5601`

### **Adding an Index Pattern**
1. Navigate to **Stack Management > Index Patterns**
2. Click **Create Index Pattern**
3. Enter the index name (`my_index*`)
4. Choose a time field and save

---

## **Kibana Queries (KQL & Lucene)**
```sh
status:200 AND extension:jpg  # Filter HTTP 200 responses with .jpg files
response:>500                 # Filter response codes greater than 500
message:*error*               # Search messages containing 'error'
```

---

## **Creating Visualizations**
1. Navigate to **Visualize > Create Visualization**
2. Select a visualization type (Line, Bar, Pie, etc.)
3. Choose an index pattern and configure the metrics
4. Save and add it to a dashboard

---

## **Setting Up Alerts in Kibana**
1. Navigate to **Alerts & Actions**
2. Click **Create Alert** and choose a condition (e.g., high response times)
3. Set up notification actions (email, Slack, etc.)
4. Save and enable the alert

---

## **Useful Elasticsearch & Kibana Resources**
- [Elasticsearch Docs](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- [Kibana Docs](https://www.elastic.co/guide/en/kibana/current/index.html)
- [Elasticsearch Query DSL](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl.html)

---

This cheatsheet provides a quick reference for Elasticsearch and Kibana commands, queries, and dashboards. Let me know if you need any modifications!

