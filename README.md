# Introduction #
The original creator of IKAnalyzer is [Liang-Yi Lin ](linliangyi2007@gmail.com) . The project home is [http://code.google.com/p/ik-analyzer/](http://code.google.com/p/ik-analyzer/) .

# Feature #
 - based on IK Analyer 2012-FF Hotfix 1 
 - added support for Lucene 6.0.0 API

#Installation #

 - JDK8 

>  mvn clean install

copy ik-analyzer-solr6-6.x.jar to server/solr-webapp/webapp/WEB-INF/lib

# Configuration #
    <fieldType name="text_ik" class="solr.TextField">   
      <analyzer type="index">
        <tokenizer class="org.wltea.analyzer.lucene.IKTokenizerFactory" useSmart="false" />
      </analyzer>
      <analyzer type="query">
        <tokenizer class="org.wltea.analyzer.lucene.IKTokenizerFactory" useSmart="true" />
      </analyzer>
    </fieldType>

or
    
    <fieldType name="text_ik" class="solr.TextField">   
      <analyzer type="index" useSmart="false" class="org.wltea.analyzer.lucene.IKAnalyzer"/>   
      <analyzer type="query" useSmart="true" class="org.wltea.analyzer.lucene.IKAnalyzer"/>   
    </fieldType>

# Compilation Error #
1. Question: The following error happened while running "mvn clean install"

> [ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.3:compile (default-compile) on project ik-analyzer-solr6: Fatal error compiling: invalid target release: 1.8 -> [Help 1]

Answer: Please check your JAVA_HOME setting. If JAVA_HOME setting exists, it may not be JAVA8.  


# Resources #
1. [Solr6配置中文分词库 IKAnalyzer](http://blog.csdn.net/jiangchao858/article/details/53178557)
    