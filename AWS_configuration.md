# AWS Configuration

To ensure scalable data processing and cloud-based application development, we used **Amazon Web Services (AWS)** as the platform for building and running our project: **Local Weather Trends Dashboard**. The configuration was completed using student accounts provided via the **AWS Academy** program, which have limited permissions but were fully sufficient for the scope of our project.

The main goal of using AWS was to efficiently process large datasets using **Apache Spark**, store them in the cloud with **Amazon S3**, and perform interactive analysis through **EMR Studio Workspace**. Below is a detailed description of the configuration process, including visual confirmation for each step.

## 1. Creation of an EMR Cluster

We configured and launched an **Amazon EMR** (Elastic MapReduce) cluster designed for distributed big data processing using Apache Spark. The cluster was successfully created and ready for use.

![EMR Cluster Successfully Created](./images/cluster_created.jpg)

## 2. Setup of EMR Studio Workspaces

To enable interactive data exploration and coding, we set up **EMR Studio**, a Jupyter-based development environment. EMR Studio allows direct connection to the Spark cluster and integration with the S3 bucket.

As part of the setup, two separate workspaces were created:

- `Studio_1_workspace_1` – the main workspace used for running notebooks and Spark integration  
- `ims` – an additional workspace used for testing or auxiliary development

The EMR Studio environment was successfully initialized, and both workspaces were visible and functioning properly.

![SageMaker Studio Workspaces Running](./images/workspaces_studio1.jpg)

## 3. Initial Cluster Connection without Code

Before deploying any code, we verified the connection between our development environment and the Spark cluster. This ensured that job submission and remote execution would work later on.

![Empty Spark Cluster Connected to AWS](./images/cluster_connected.png)

## 4. Uploading Data to S3 Bucket

The weather datasets in CSV format were uploaded to a dedicated **Amazon S3 bucket**. S3 served as the primary storage for both input files and (optionally) output data, enabling efficient distributed access by Spark jobs.

![Files Uploaded to S3 Bucket](./images/bucket_files.png)

## 5. Running Jupyter Notebook with Spark Jobs

With the infrastructure ready, we ran Python scripts (data loading, cleaning, aggregation, visualization) from a notebook connected to the EMR cluster. All code cells executed successfully.

![Notebook Running with Code on AWS](./images/notebokAWS.png)

## 6. Visualization Output on AWS

The final results — such as heatmaps — were generated inside the notebook and correctly displayed using built-in plotting libraries.

![Heatmap Results Displayed](./images/heatmapAWS.png)
