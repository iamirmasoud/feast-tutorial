# Feast Tutorial

Feast is an open-source feature store that provides a centralized repository for managing and serving machine learning features. It aims to solve the challenges associated with feature management in machine learning pipelines.

A feature store is a dedicated data store designed to store, organize, and serve machine learning features. Features are the inputs to machine learning models and can include raw data, derived features, or preprocessed data. In a feature store, features are typically associated with entities (e.g., users, products, devices) and timestamps, allowing you to retrieve historical and real-time feature values.

Feast allows you to define, store, and serve features in a scalable and efficient manner. Here are some key features and capabilities of Feast:

Feature definition: You can define features using a declarative syntax, specifying their name, data type, and other metadata. This provides a centralized and standardized way to define features across different teams and projects.

Data ingestion: Feast supports batch and streaming ingestion of feature data. You can push historical data in batches or continuously stream new data into the feature store. Feast integrates with various data sources and processing frameworks to facilitate data ingestion.

Feature serving: Feast provides a serving layer that allows you to retrieve feature values for a given entity and timestamp. It supports both batch and online serving modes, enabling efficient feature retrieval during model training and real-time inference.

Data versioning and lineage: Feast tracks the versioning and lineage of feature data, allowing you to understand how features were computed and trace back to the original data sources. This helps ensure reproducibility and transparency in your machine learning workflows.

Feature discovery and retrieval: Feast provides APIs and tooling to discover available features, retrieve feature values, and join features from multiple sources. This simplifies the process of accessing and combining features in your machine learning pipelines.

Integration with ML frameworks: Feast integrates with popular machine learning frameworks and platforms, such as TensorFlow and Kubeflow, making it easier to incorporate feature management into your existing ML infrastructure.

You can find the theoretical concepts in the feast website itself. Link Here I want to explain the practical implementation aspect of feast. For the same I have created a video explaining each of the below steps used in feast online and offline feature serving to models.

1. Prepare data set and store in parquet format
2. Create an `event_timestamp column` to the data
3. Create a unique ID and add as a column to the data
4. `feast init` and create feature repo structure (to be modified later)
5. create `feature_definition.py` file inside feature repo and define data source and feature views
6. `feast apply` to register and deploy features to offline store
7. Load historical features using `get_historical_features` from offline feature store
8. Train the model using offline features
9. Use `feast materialize-incremental` to load features to online store
10. Get online features using `get_online_features`
11. Inference using the data from online feature store


References:
https://kedion.medium.com/creating-a-feature-store-with-feast-part-1-37c380223e2f#:~:text=With%20feast%20materialize%2Dincremental%20%2C%20the,of%20the%20most%20recent%20materialization.

https://docs.feast.dev/
