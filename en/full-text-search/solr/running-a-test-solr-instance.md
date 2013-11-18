# Running a test Solr server instance

Download and unpack Solr. In the "example" directory, run:

    java -Djetty.port=8983 -Dsolr.solr.home=/path/to/home -Dsolr.data.dir=/path/to/data -jar start.jar
