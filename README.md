<h1 style="font-size: 24px;"> My Stock-Market Kafka Real Time Data Engineering Project </h1>
<h2 style="font-size: 20px;">Introduction</h2>
<p>In this project, I executed an End-To-End Data Engineering Project on Real-Time Stock Market Data using Kafka.</p>

<p> I used various technologies such as Python, Amazon Web Services (AWS), Apache Kafka, Glue, Athena, and SQL in the project.</p>

<h3 style="font-size: 20px;">Architecture</h3>

<img src="Project-Architecture.jpg"/>


<h2>Technologies Used:</h2>
    <ul>
        <li>Programming Language - Python</li>
        <li>Amazon Web Service (AWS)</li>
     <ol type="1">
        <li>S3 (Simple Storage Service)</li>
        <li>Athena</li>
        <li>Glue Crawler</li>
        <li>Glue Catalog</li>
        <li>EC2</li>
    </ol>
        <li>Apache Kafka</li>
    </ul>

<h2>Dataset Used</h2>
<a href="Downloads/indexProcessed.csv" download>indexProcessed.csv</a>

<h2>Installation/Run</h2>
<ul>
    <li>Pyhton 3.7 +</li>
    <li>wget https://downloads.apache.org/kafka/3.3.1/kafka_2.12-3.7.0.tgz</li>
    <li>tar -xvf kafka_2.12-3.3.1.tgz</li>
    <li>java - sudo yum install -y java-1.8.0-amazon-corretto-devel</li>
    <li>zookeeper kafka</li>
</ul>

<h3>Step-by-step Process:</h3>
<p>Start Zoo-keeper:</p>
<ul>
    <li> bin/zookeeper-server-start.sh config/zookeeper.properties</li>
<img width="1311" alt="Zookeeper" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/6ae375db-7669-4dee-829e-46e4e01c889c">

<p>Start Kafka-server:</p>
    <li>export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"</li> <p>I ran this command because I provide more memory.</p>
    <li>cd kafka_2.12-3.3.1</li>
    <li>bin/kafka-server-start.sh config/server.properties</li>
    <li>sudo nano config/server.properties</li>
<img width="727" alt="kafka" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/6f4effc2-1386-4132-b3e0-ad359f5dd649">

<p>I directed it towards a private server and modified the server.properties to enable operation on a public IP.</p>
</ul>

