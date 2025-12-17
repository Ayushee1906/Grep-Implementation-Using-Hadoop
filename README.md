# Hadoop-Log-Analyzer-Using-Grep


## Overview
This project implements a simple **Hadoop Grep (Word Frequency)** program using **Java** on the **Cloudera Hadoop platform**.  
It counts the frequency of a given word from a sample text file using Hadoop MapReduce.

## Files
- **Input file:** `us constitution.txt`
- **Jar file:** `grep.jar`
- **Platform:** Cloudera Hadoop

## Prerequisites
- Java
- Hadoop (Cloudera distribution)
- HDFS configured and running

## Usage
1. Upload the input file to HDFS:
   ```bash
   hdfs dfs -put "us constitution.txt" /input/
