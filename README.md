# 🚀 Spark Structured Streaming with JSON → Delta Lake

This project demonstrates how to build a **Spark Structured Streaming pipeline** that:

- Reads JSON data from a landing zone
- Uses two types of triggers:
  - **Trigger Once** → batch-style micro-batch (runs once and stops)
  - **Continuous Trigger (10 seconds)** → continuously checks for new files every 10s
- Writes output in **Delta Lake format**
- Uses a **checkpoint location** for fault tolerance and exactly-once guarantees

---

## 📂 Streaming Overview

```text
Source (JSON files)  --->  Spark Structured Streaming  --->  Delta Lake (sink)
                            (trigger once / continuous)

⚠️ **Archive**
Use below options to archive processed data/files:

 .option("cleanSource","archive") \
 .option("sourceArchiveDir","/Volumes/sparkcatalog/store/raw_volume/js_archive") \


