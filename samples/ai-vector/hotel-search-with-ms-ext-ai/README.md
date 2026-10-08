# Oracle AI Vector Hotel Search Sample

This .NET console application demonstrates vector storage and similarity search for hotel data with Oracle AI Database and the [`Oracle.VectorData`](https://www.nuget.org/packages/Oracle.VectorData/) connector.

The demo application reads sample hotel records from `Hotels.json`, generates 1536-dimensional embeddings with OpenAI's `text-embedding-3-small` model, and stores the records in a vector collection.

It then demonstrates four searches:

1. Retrieve hotels by primary key.
2. Filter hotels by a scalar property, such as a rating of 9 or higher.
3. Search hotel names by cosine distance.
4. Search hotel descriptions by Euclidean distance.

During cleanup or upon an exception, the application attempts to delete the collection and the corresponding database table.

## Configure the database connection and embedding model credentials

Edit `AppSettings.json` and set the database connection string and OpenAI credentials:

```json
{
  "Oracle": {
    "ConnectionString": "User Id=<USER>; Password=<PASSWORD>; Data Source=<DATA-SOURCE>;"
  },
  "OpenAI": {
    "Key": "<OPENAI-API-KEY>",
    "Endpoint": "<OPENAI-ENDPOINT>"
  }
}
```

As a reminder, keep real credentials out of source control.
