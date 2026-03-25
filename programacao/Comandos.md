## Mongodb

---

### Backup collection

```bash
mongodump --uri="mongodb://<USER>:<PASSWORD>@<HOST>:<PORT>/<TARGET_DB>?authSource=<AUTH_DB>" --collection=COLLECTION --out=/OUTPUT/FILE/PATH
```

### Delete collection

```bash
mongosh "mongodb://<USER>:<PASSWORD>@<HOST>:<PORT>/<TARGET_DB>?authSource=<AUTH_DB>" --eval 'db.<COLLECTION>.deleteMany({})'
```

## Solr

### Get indexed count

```bash
curl "http://<USER>:<PASSWORD>@<HOST>:<PORT>/solr/<CORE>/select?q=*:*&rows=0"
```

### Backup core

```bash
curl "http://<USER>:<PASSWORD>@<HOST>:<PORT>/solr/<CORE>/replication?command=backup&location=/BACKUP/PATH/RELATIVE/TO/SOLR_HOME"
```

### Delete all indexed from core

```bash
curl "http://<USER>:<PASSWORD>@<HOST>:<PORT>/solr/<CORE>/update?commit=true" -H "Content-Type: text/xml" --data-binary "<delete><query>*:*</query></delete>"
```