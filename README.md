# Apache-Spark-INFER-DotNet
Spark .NET on MacOS

## Download .NET 6.0 

.NET is a free, cross-platform, open-source developer platform for building many different types of applications.
https://dotnet.microsoft.com/en-us/download

## Download Java

Java SE Development Kit 8u311
https://www.oracle.com/java/technologies/downloads/#java8

# PySpark on macOS: installation and use

## Install dependencies:

### install dependencies is with homebrew (in my opinion the best package manager for MacOS).
To install homebrew, you only need to copy this in your terminal:

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

### install java
brew install java 
brew info java

### install apache-spark
brew install apache-spark
brew info apache-spark

### check your system with
brew doctor
if you have: “Your system is ready to brew.” you can go to the next step. If you have any message you can follow the instructions given by the console.

### Installing pySpark
you already have python 3 installed on your computer. If not installed already, you can do so with homebrew
brew install python3

### install the python Spark API pySpark:
pip3 install pyspark

### define several environment variables and declare paths so that the Spark driver is accessible through pySpark.
First of all we need to declare which java version to use. I have two versions on my system. You can do so by opening the .bashrc file with nano:

nano .bashrc

### declare java version  with the following environment variable:
export JAVA_HOME=/Library/java/JavaVirtualMachines/adoptopenjdk-8.jdk/contents/Home/


### declare java runtime environment:
export JRE_HOME=/Library/java/JavaVirtualMachines/openjdk-13.jdk/contents/Home/jre/

### declare two variables for Spark:
export SPARK_HOME=/usr/local/Cellar/apache-spark/3.2.0/libexec
export PATH=/usr/local/Cellar/apache-spark/3.2.0/bin:$PATH

export PYSPARK_PYTHON=/usr/local/bin/python3
export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS='notebook'

### RUN PYSPARK IN JUPYTER
pyspark
