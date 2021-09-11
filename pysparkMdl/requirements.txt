<!-- Requirements for running the model in spark environment -->
# Install Pyspark using pip
pip install pyspark

<!-- Installaion required for spark and hadoop setups -->
!apt-get install openjdk-8-jdk-headless -qq > /dev/null

# !wget -q https://archive.apache.org/dist/spark/spark-3.0.0/spark-3.0.0-bin-hadoop3.2.tgz
!wget -q https://archive.apache.org/dist/spark/spark-3.1.2/spark-3.1.2-bin-hadoop3.2.tgz
# unzip the spark file to the current folder
# !tar xf spark-3.0.0-bin-hadoop3.2.tgz
!tar xf spark-3.1.2-bin-hadoop3.2.tgz

# set your spark folder to your system path environment. 
import os
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64"
# os.environ["SPARK_HOME"] = "/content/spark-3.0.0-bin-hadoop3.2"
os.environ["SPARK_HOME"] = "/content/spark-3.1.2-bin-hadoop3.2"

# install findspark using pip
!pip install -q findspark

SPARK_HOME  = '/content/spark-3.1.2-bin-hadoop3.2'
PATH = '%SPARK_HOME%/bin;%SPARK_HOME%/python;%PATH%'
PYTHONPATH = '%SPARK_HOME%\python;%SPARK_HOME%\python\lib\py4j-0.10.9-src.zip:%PYTHONPATH%'

# Check the pyspark version
import pyspark
print(pyspark.__version__)
print(PYTHONPATH)
print(pyspark.conf)