<h1 style="font-size: 24px;">Stock-Market Kafka Real Time Data Engineering Project </h1>
<h2 style="font-size: 20px;">Introduction</h2>
<p>In this project, I executed an End-To-End Data Engineering Project on Real-Time Stock Market Data using Kafka.</p>

<p> I used various technologies such as Python, Amazon Web Services (AWS), Apache Kafka, Glue, Athena, and SQL in the project.</p>

<h3 style="font-size: 20px;">Architecture</h3>

<img src="Project-Architecture.jpg"/>


<h2>Technologies Used:</h2>
    <ul>
        <li>Programming Language - Python, SQL</li>
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
[indexProcessed.csv](https://github.com/kalid123/real-time-stock-analysis-project/files/14955289/indexProcessed.csv)

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
<img width="1298" alt="Screenshot 2024-04-12 at 2 21 47 AM" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/f6fc23ac-e5f8-40f7-98d6-c9c1ef8a29e5">


<p>Start Kafka-server:</p>
    <li>export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"</li> <p>I ran this command because I provide more memory.</p>
    <li>cd kafka_2.12-3.3.1</li>
    <li>bin/kafka-server-start.sh config/server.properties</li>
    <li>sudo nano config/server.properties</li>
<img width="727" alt="kafka" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/6f4effc2-1386-4132-b3e0-ad359f5dd649">

<p>I directed it towards a private server and modified the server.properties to enable operation on a public IP.</p>
</ul>
<h3>Create the topic:</h3>
<ul>
    <li>cd kafka_2.12-3.7.0</li>
    <li> bin/kafka-topics.sh --create --topic demo_test1 --bootstrap-server 3.86.115.17:9092 --replication-factor 1 --partitions 1
</li>
<h3>Start Producer:</h3>
<li>bin/kafka-console-producer.sh --topic demo_test --bootstrap-server 3.86.115.17:9092
</li>
<h3>Start Consumer:</h3>

<li>bin/kafka-console-consumer.sh --topic demo_test --bootstrap-server 3.86.115.17:9092
</li>
</ul>

<h3>EC2 instance:</h3>
<P> I created an EC2 instace to connect to the terminal.</P>
<img width="1168" alt="EC2 instance" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/d38782da-824d-4edf-b3f2-e5edf2101cbd">

<h3>S3 Bucket</h3>
<P>Created an S3 bucket to store my CSV data file.</P>
<img width="1056" alt="S3 bucket" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/3ccc32c3-54b0-4519-9ad8-f63c5beb3210">

<h3>AWS Glue Crawler and AWS Athena Integration</h3>
<p>First, I initiated a crawler using AWS Glue to catalog the dataset. Subsequently, I established a connection between the dataset and AWS Athena to enable real-time program execution.</p>
<p>
    SELECT *
FROM "stock_market_kafka"."data"
WHERE high > 1990;
</p>
<img width="928" alt="AWS athena" src="https://github.com/kalid123/real-time-stock-analysis-project/assets/104119652/4abf01f8-d67b-4bb5-8841-19ca855d6286">

