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
