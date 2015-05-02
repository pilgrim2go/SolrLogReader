## A high performance Solr log reader / parser.

Early days. Crunches and summarizes Solr log files.  

SolrLogReader [file or folder path] {TextMatchAspect} {TextMatchAspect} {-o outputdir}...  

Example: SolrLogReader /solr/logs  

An optional TextMatchAspect will pull out any logs with matching text, for example: SolrLogReader /solr/logs org.apache.solr.cloud 

If you specify an outputdir, more verbose summaries are dumped to files in that folder as well as an html error chart.  

If a folder is given, logs are parsed in reverse order if they end with digits.  
solr.log.0, solr.log.1, solr.log.2, etc

Logs that look like they come from different servers will be summarized separately.  
solr-host1.log.0, solr-host2.log.1, solr-host1.log.1, etc


### FAQ

Q: Can I just process the Solr logs in a deep directory hierarchy with lots of log files?  
A: SolrLogReader /solr/logs/solr* A filename with a glob pattern will be used to match against file names for all files under the /solr/logs directory hierarchy.  


### Getting Started:

wget https://github.com/markrmiller/SolrLogReader/archive/master.zip  
  
unzip master.zip  
cd SolrLogReader-master  
javac -cp lib/* src/main/java/*.java  
java -cp lib/*:src/main/java SolrLogReader /path/to/logs  