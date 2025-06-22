# Hadoop 1.x vs 2.x vs 3.x

## Hadoop Version Comparison

| **Feature**                   | **Hadoop 1.x**                                               | **Hadoop 2.x**                                               | **Hadoop 3.x**                                               |
| ----------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Resource Management**       | **MapReduce** **(JobTracker)**<br />Tightly coupled resource and job scheduling | Introduced **YARN** (Yet Another Resource Negotiator)<br>Decouples resource management, supports multi-frameworks (e.g., Spark, Flink) | Enhanced YARN<br>Supports heterogeneous resources (GPU/FPGA) |
| **HDFS High Availability**    | **Single NameNode， Master/Slave topology $\rightarrow$ SPOF**;<br>**No HA support** | **Active/Standby NameNodes** with QJM<br>Metadata synchronization | **Multiple NameNodes** with Raft protocol<br>Improved fault tolerance |
| **Storage Efficiency**        | 3x replication(3副本机制)                                    | 3x replication                                               | **Erasure Coding(纠删码)**<br>Reduces storage overhead to 50% |
| **Single Point of Failure**   | JobTracker + NameNode (SPOF)                                 | NameNode HA eliminates SPOF                                  | Further reduced with multiple NameNodes                      |
| **Scalability**               | ≤ 4,000 nodes                                                | ≤ 10,000 nodes                                               | Supports ultra-large clusters                                |
| **Compute Framework Support** | **Only MapReduce**                                           | **Multiple frameworks** (**Spark**, **Flink**, etc.)         | Enhanced compatibility (e.g., Kubernetes)                    |
| **Java Version**              | Java 6/7                                                     | Java 7/8                                                     | **Java 8+**                                                  |
| **Ecosystem**                 | Limited (MapReduce-centric)                                  | Broad (supports **real-time streaming**, etc.)               | Optimized (**Docker**/**GPU** support)                       |
| **Key Innovations**           | Basic **MapReduce** and **HDFS**                             | **YARN**, **HDFS Federation**                                | **Erasure Coding**, **multi-NameNode**, resource type flexibility |



- **Hadoop 1.x**：以HDFS和MapReduce作为核心组件，奠定了其在大数据领域的基础。
- **Hadoop 2.x**：引入YARN（Yet Another Resource Negotiator），对架构进行重大改进，使得资源管理更加高效。
- **Hadoop 3.x**：在前两个版本的基础上进行了多项改进，包括增加存储效率、提升集群规模、支持云平台和容器化。



## Details

### Hadoio 1.x

#### HDFS

![image-20250313113115783](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20250313113115783.png)



#### MapReduce

![image-20250313113219157](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20250313113219157.png)

#### Master/Slave topology

![image-20250313205742965](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20250313205742965.png)

---



### Hadoop 2.x

#### YARN

![image-20250313205844355](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20250313205844355.png)

![image-20250313205852100](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20250313205852100.png)



### Hadoop 3.x

#### Hadoop Erasure Coding

![image-20250313112952899](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20250313112952899.png)

