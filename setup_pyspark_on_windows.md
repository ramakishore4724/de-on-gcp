## Step 1
# Download and Setup Python 3.10.5 for Windows
Check setup env.md file for detailed steps

## Step 2
# Download and Setup Java 8 for Windows
https://www.oracle.com/java/technologies/downloads/#java8-windows

## Step 3
# Add Java path into Env Variables
C > Program Files > Java > jdk-1.8
Copy above path and create a new variable JAVA_HOME and paste it

In path variable add a new line
%JAVA_HOME%\bin

To validate, open a new cmd prompt and type:
java -version
javac -version

## Step 4
# Download Apache Spark and Extract it
https://archive.apache.org/dist/spark/spark-3.2.0/spark-3.2.0-bin-hadoop2.7.tgz

Copy the path of base folder of Spark and create a new variable SPARK_HOME and paste it
In path variable add a new line
%SPARK_HOME%\bin

## Step 5
# Setup winutils to integrate HDFS APIs with Windows
Why to install winutils?
In the process of building data processing applications using Spark, we need to read data from files
Spark uses HDFS API to read files from several file systems like HDFS, s3, local etc
For HDFS APIs to work on Windows, we need to have WinUtils

https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe

Once exe file is donwloaded, create a folder structure like C/hadoop/bin and paste exe file inside this folder
Copy the path of base folder of hadoop and create a new variable HADOOP_HOME and paste it
In path variable add a new line
%HADOOP_HOME%\bin

## Step 6
# Add a new env variable
name:PYSPARK_PYTHON
value:python

## Step 7
# Install an extension
Spark & Hive Tools -- by Microsoft

## Step 8
# Integrate VS Code with pyspark packages
File > Preferences > Settings > launch > edit in settings.json
Create a new file launch.json and paste below content inside it
{
    "version": "0.0.1",
    "configurations": [
        {
            "type": "python",
            "name": "Launch Python File",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "env": {
                "PYTHONPATH": "C:/SPARK/spark-3.2.0-bin-hadoop2.7/python;C:/SPARK/spark-3.2.0-bin-hadoop2.7/python/pyspark;C:/SPARK/spark-3.2.0-bin-hadoop2.7/python/lib/py4j-0.10.9.2-src.zip;C:/SPARK/spark-3.2.0-bin-hadoop2.7/python/lib/pyspark.zip"
            }
        },
    ]
}

## Step 9
# Integrate VS Code with pyspark packages using Jupyter Notebooks
Make sure to Activate venv then - 
Cell 1:
!pip install findspark

Cell 2:
import findspark
findspark.init()