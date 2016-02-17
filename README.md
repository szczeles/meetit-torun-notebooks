# meetit-torun-notebooks
Notebooks presented on  Meet IT Toruń

## Local spark & notebook installation tutorial (tested on Ubuntu 14.04.3 LTS)

1. Download and extract [spark](http://www.apache.org/dyn/closer.lua/spark/spark-1.6.0/spark-1.6.0-bin-without-hadoop.tgz )
1. Download and extract [hadoop](http://www.apache.org/dyn/closer.cgi/hadoop/common/hadoop-2.6.4/hadoop-2.6.4.tar.gz) 
1. Create spark's conf/spark-env.sh with the following content:

        #!/usr/bin/env bash
        export JAVA_HOME=PATH_TO_JAVA_HOME_DIRECTORY
        export SPARK_DIST_CLASSPATH=$(PATH_TO_EXTRACTED_HADOOP/bin/hadoop classpath)

1. Install jupyter using pip: `sudo pip3 install nose "ipython[notebook]"`

Now you can run notebook with pyspark kernel using:

    PYSPARK_PYTHON=python3 PYSPARK_DRIVER_PYTHON=ipython3 PYSPARK_DRIVER_PYTHON_OPTS="notebook" PATH_TO_EXTRACTED_SPARK/bin/pyspark --master local[*]
