# foodie-wellness-analytics-platform

This project explores how dining culture and wellness accessibility intersect to shape lifestyle patterns in LA and SF. Using Yelp reviews, demographic data, and wellness indicators, the project builds a “Food & Wellness Lifestyle Index” at the neighborhood level. Since tourist activity strongly influences dining preferences in both cities, the project incorporates proxies for tourism (proximity to attractions, Airbnb density, and review distribution patterns) to distinguish between tourist-driven and local dining trends. The goal is to understand how wellness-oriented food culture emerges differently in tourist hotspots versus local neighborhoods.

This project integrates diverse, large-scale datasets (Yelp JSON reviews, Census API, OpenAQ API, Google Places API, InsideAirbnb CSVs, and airport passenger data), requiring a robust and scalable data engineering stack. The chosen technologies are designed to handle both the volume (millions of rows) and the variety (JSON, CSV, APIs) of the data sources:

Apache Spark: Selected for distributed processing and its ability to handle multi-million row datasets efficiently. Spark makes it possible to parse nested Yelp JSON, perform large-scale joins with demographic and tourism datasets, and run NLP transformations on review text.

Cloud Object Storage (S3/GCS): Provides a data lake to store raw, semi-structured, and processed data in scalable formats (JSON, CSV, Parquet).

Airflow (or Prefect): Orchestrates ingestion pipelines, ensuring reproducible and automated extraction from APIs and batch jobs.

dbt (Data Build Tool): Enables modular, version-controlled transformations that convert raw Spark outputs into clean fact and dimension tables. dbt also makes the pipeline easy to document and explain to stakeholders.

Data Warehouse (BigQuery/Snowflake/Postgres): Provides a structured, queryable layer optimized for analytics and dashboarding.

BI / Dashboard (Tableau, Metabase, or Looker Studio): Makes insights accessible, visualizing the “Food & Wellness Lifestyle Index” and enabling comparisons between tourist-driven and local dining cultures.

Together, this stack represents a modern data engineering workflow: raw ingestion → scalable processing → curated transformations → analytics-ready datasets. It demonstrates not just technical ability, but also design decisions aligned with real-world industry practices.
