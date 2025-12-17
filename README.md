# Grep on Hadoop using Cloudera

## Project Overview
This project demonstrates the implementation of a **Grep program using Hadoop MapReduce** to search for a specific keyword or pattern from a large text file stored in **HDFS**.  
The application is developed in **Java** and executed on **Apache Hadoop** running inside the **Cloudera QuickStart VM**.  

The program mimics the traditional Unix `grep` command but leverages Hadoop’s distributed processing capabilities to efficiently process large datasets.

**Sample Input File Name:** `constitunial`

---

## Technology Stack
- **Apache Hadoop**
  - HDFS
  - MapReduce
- **Java**
- **Cloudera QuickStart VM**
- **Eclipse IDE**
- **WinSCP**

---

## Prerequisites

### Java
- JDK 7 or above installed
- `JAVA_HOME` configured properly

### Hadoop (Cloudera QuickStart)
- Cloudera QuickStart VM installed and running
- Hadoop services up and running inside the VM

### Eclipse
- Eclipse IDE for Java Developers
- Used for writing, compiling, and exporting the MapReduce project as a JAR

### WinSCP
- Used to transfer files between the local system and Cloudera VM

---

## Establishing Connection Between Local Host and Cloudera using WinSCP

**Connection Details:**
- **Hostname:** `localhost`
- **Protocol:** SFTP
- **Port:** `22`
- **Username:** `cloudera`
- **Password:** `cloudera`

### Steps to Connect WinSCP to Cloudera VM
1. Open **WinSCP**
2. Select **SFTP** as the protocol
3. Enter the hostname, port, username, and password
4. Click **Login**
5. Once connected, access the Cloudera home directory

**Purpose:**
- Transfer **JAR files** from local system to Cloudera VM
- Download **output files** from Cloudera to local system

---

## Project Structure
<img width="236" height="343" alt="image" src="https://github.com/user-attachments/assets/960764a1-b199-427a-b02b-b445f0b5a96e" />



---

## Java Program Explanation

### Mapper (Grep Logic)
- Reads each line from the input file
- Checks whether the line contains the specified keyword/pattern
- Emits the matched line with a count of `1`

**Input:**  
`<LongWritable, Text>`

**Output:**  
`<Text, IntWritable>`

---

### Reducer
- Aggregates the counts of matched lines
- Outputs the final matched lines and their occurrences

---

### Driver Class
- Configures the MapReduce job
- Sets:
  - Mapper class
  - Reducer class
  - Input and output paths
- Submits the job to Hadoop for execution

---

## Steps to Execute the Project on Cloudera

### 1. Creating Java Project in Eclipse
- Open Eclipse
- Create a new **Java Project**
- Add package and Java classes (Mapper, Reducer, Driver)

### 2. Adding External Hadoop JARs
- Right-click project → **Build Path**
- Add required Hadoop JARs from Cloudera installation

### 3. Exporting the Project as a JAR
- Right-click project → **Export**
- Select **Runnable JAR**
- Export as `GrepHadoop.jar`

### 4. Uploading Sample File to HDFS

hadoop fs -put constitunial /user/cloudera/input/

**### Running Grep MapReduce Job**
hadoop jar GrepHadoop.jar com.hadoop.grep.GrepDriver \
/user/cloudera/input/constitunial /user/cloudera/output


### Output Directory Creation

Hadoop automatically creates the output directory

Ensure the directory does not already exist

###  Output File

part-r-00000

Reading Output
Using hadoop fs -cat
hadoop fs -cat /user/cloudera/output/part-r-00000

Transferring Output from Cloudera to Local System
Using hadoop fs -get
hadoop fs -get /user/cloudera/output/part-r-00000 /home/cloudera/

### Using WinSCP

Navigate to the output file location in Cloudera

Download part-r-00000 to the local machine

### HDFS Commands Used
hadoop fs -ls
hadoop fs -mkdir
hadoop fs -put
hadoop fs -cat
hadoop fs -get
hadoop fs -rm -r

```markdown
---
### Conclusion

This project successfully demonstrates how to implement a **Grep program using Hadoop MapReduce**.

By running the application on **Cloudera QuickStart VM**, it showcases the power of distributed processing for text searching tasks.

The project also provides hands-on experience with **HDFS commands**, **MapReduce programming**, and **file transfer using WinSCP**.
