[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/6x3xYnv0)
# COMP4651 Assignment-1: EC2 Measurement (2 questions, 4 marks)

### Deadline: 23:59, Mar 2, Saturday

---

### Name: CHAN, Chun Hin
### Student Id: 20853893
### Email: chchanec@connect.ust.hk

---

## Question 1: Measure the EC2 CPU and Memory performance

1. (1 mark) Report the name of measurement tool used in your measurements (you are free to choose *any* open source measurement software as long as it can measure CPU and memory performance). Please describe your configuration of the measurement tool, and explain why you set such a value for each parameter. Explain what the values obtained from measurement results represent (e.g., the value of your measurement result can be the execution time for a scientific computing task, a score given by the measurement tools or something else).

    > Your answer goes here.

**Answer:**

> * _Report the name of measurement tool used in your measurements:_
> 
> I use _**SysBench**_ as the measurement tool to measure CPU and memory performance.
>
> ---
> ---
> * _Please describe your configuration of the measurement tool, and explain why you set such a value for each parameter:_
> 
> For testing the CPU, the configuration I have used is:
> 
> `sysbench --test=cpu --threads=4 --cpu-max-prime=20000 run`
> 
> I set the total number of worker threads to create as 4, because I would like to test the CPU performance on multi-thread processing when there are only a few threads.
> 
> I set the maximum prime number limit as 20000, because I would like to test the CPU performance on verifying the prime numbers between 2 and the square root of 20000 using standard division technique. This can test the CPU stress on handling mathematical calculation problems.
>
> ---
> * _Explain what the values obtained from measurement results represent:_
> 
> The results I got from the CPU test are number of threads, prime number limits, CPU speed, general statistics, latency and threads fairness.
> 
> For the **number of threads**, this represents the total number of worker threads to be created, which is 4 as set by me.
> 
> For the **prime number limits**, this represents the upper limit of the prime number. This value is set to 20000 by me since I would like to test the CPU performance on verifying the prime numbers between 2 and the square root of 20000 using standard division technique.
> 
> For **CPU speed**, this represents how many events can the CPU can handle in each second on average.
> 
> For **general statistics**, it represents the total time to complete the CPU test and the total number of events being handled in this CPU test.
> 
> For **latency**, this represents the minimum, the average, the maximum, the 95th percentile and the sum of the latency in milliseconds respectively when the CPU test is run.
> 
> For **threads fairness**, this represents the average and the standard deviation of the number of events handled by each thread, and includes the average and the standard deviation of the execution time of each thread during the CPU test.
>
> ---
> ---
> * _Please describe your configuration of the measurement tool, and explain why you set such a value for each parameter:_
> 
> For testing the memory, the configuration I have used are:
> 
> `sysbench --test=memory --memory-block-size=2K --memory-scope=global --memory-total-size=100G --memory-oper=read run`
> 
> `sysbench --test=memory --memory-block-size=2K --memory-scope=global --memory-total-size=100G --memory-oper=write run`
> 
> I set the memory block size for read/write as 2KiB, because I would like to test read/write memory performance when the memory block size for read/write is small to allow more memory block being utilized.
> 
> I set the memory scope as global, because I would like to test the memory performance when the working thread is using a globally allocated memory block.
> 
> I set the total memory size as 100GiB, because I would like to test the memory read/write performance when it needs to read/write a large amount of data from/to the memory.
> 
> I set the memory operation as read first, and then follow by write. Because I would like to perform one memory read test and one memory write test respectively.
>
> ---
> * _Explain what the values obtained from measurement results represent:_
> 
> For both memory read and memory write test, the results I got from the memory tests are number of threads, block size, total size, operation, scope, total operations, number of operation per second, total data transferred, data transferred per second, general statistics, latency, threads fairness.
> 
> For the **number of threads**, this represents the number of working threads used in the memory read/write test.
> 
> For the **block size**, this represents the memory block size for read/write in the memory read/write test.
> 
> For the **total size**, this represents the total memory data size need to be transferred during the memory read/write test.
> 
> For the **operation**, it represents the operation mode during the memory test; if you are performing memory read test, it will show “read”; if you are performing memory write test, it will show “write”.
> 
> For the **scope**, this represents whether the working thread is using a globally allocated memory block or a locally allocated memory block in the memory read/write test. If it is using a globally allocated memory block, it will show “global”; if it is using a locally allocated memory block, it will show “local”.
> 
> For the **total operations**, this represents the total number of operations completed during the memory read/write test.
> 
> For the **number of operations per second**, this represents the number of operations completed each second on average during the memory read/write test.
> 
> For the **total data transferred**, this represents the total data size being read/write in the memory read/write test.
> 
> For the **data transferred per second**, this represents the data size being read/write each second in the memory read/write test.
> 
> For **general statistics**, it represents the total time to complete the memory read/write test and the total number of events being handled in this memory read/write test.
> 
> For the **latency**, this represents the minimum, the average, the maximum, the 95th percentile and the sum of the latency in milliseconds respectively when the memory read/write test is run.
> 
> For **threads fairness**, this represents the average and the standard deviation of the number of events handled by each thread, and includes the average and the standard deviation of the execution time of each thread during the memory read/write test.


2. (1 mark) Run your measurement tool on general purpose `t2.small` (1 vCPU, 2 GiB Memory), `m5.large` (2 vCPU, 8 GiB Memory), and `c5d.large` (2 vCPU, 4 GiB Memory) Linux instances, respectively, and find the performance differences among these instances. Launch all the instances in the **US East (N. Virginia)** region. Does the performance of EC2 instances increase commensurate with the increase of the number of vCPUs and memory resource?

    In order to answer this question, you need to complete the following table by filling out blanks with the measurement results corresponding to each instance type.

    | Size        | CPU performance | Memory performance |
    | ----------- | --------------- | ------------------ |
    | `t2.small` |                 |                    |
    | `m5.large`  |                 |                    |
    | `c5d.large` |                 |                    |

**Answer:**

|     Size    |                                                                                                                                                                                                                                                      CPU performance                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            Memory performance                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|:-----------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  `t2.small` | Number of threads: 4<br><br>Prime numbers limit: 20000<br><br>CPU speed: 336.12 events per second<br><br>General statistics:<br>- total time: 10.0036s<br>- total number of events: 3363<br><br>Latency (in milliseconds):<br>- minimum: 2.95<br>- average: 11.89<br>- maximum: 24.44<br>- 95th percentile: 15.00<br>- sum: 39969.64<br><br>Threads fairness:<br>- events (average): 840.7500<br>- events (standard deviation): 0.43<br>- execution time (average): 9.9924<br>- execution time (standard deviation): 0.01 | -> READ test<br><br>Number of threads: 1<br><br>block size: 2KiB<br>total size: 102400MiB<br>operation: read<br>scope: global<br><br>Total operations: 5145608<br>Number of operations per second: 514446.91<br><br>Total data size transferred: 10050.02MiB<br>Amount of data size transferred per second: 1004.78 MiB/s<br><br>General statistics:<br>- total time: 10.0001s<br>- total number of events: 5145608<br><br>Latency (in milliseconds):<br>- minimum: 0.00<br>- average: 0.00<br>- maximum: 4.07<br>- 95th percentile: 0.00<br>- sum: 3426.58<br><br>Threads fairness:<br>- events (average): 5145608.0000<br>- events (standard deviation): 0.00<br>- execution time (average): 3.4266<br>- execution time (standard deviation): 0.00<br><br>---<br><br>-> WRITE test<br><br>Number of threads: 1<br><br>block size: 2KiB<br>total size: 102400MiB<br>operation: write<br>scope: global<br><br>Total operations: 4969288<br>Number of operations per second: 496819.14<br><br>Total data size transferred: 9705.64 MiB<br>Amount of data size transferred per second: 970.35 MiB/s<br><br>General statistics:<br>- total time: 10.0001s<br>- total number of events: 4969288<br><br>Latency (in milliseconds):<br>- minimum: 0.00<br>- average: 0.00<br>- maximum: 0.15<br>- 95th percentile: 0.00<br>- sum: 3688.19<br><br>Threads fairness:<br>- events (average): 4969288.0000<br>- events (standard deviation): 0.00<br>- execution time (average): 3.6882<br>- execution time (standard deviation): 0.00            |
|  `m5.large` | Number of threads: 4<br><br>Prime numbers limit: 20000<br><br>CPU speed: 647.19 events per second<br><br>General statistics:<br>- total time: 10.0049s<br>- total number of events: 6476<br><br>Latency (in milliseconds):<br>- minimum: 3.06<br>- average: 6.18<br>- maximum: 19.41<br>- 95th percentile: 11.04<br>- sum: 39992.78<br><br>Threads fairness:<br>- events (average): 1619.0000<br>- events (standard deviation): 0.71<br>- execution time (average): 9.9982<br>- execution time (standard deviation): 0.00 | -> READ test<br><br>Number of threads: 1<br><br>block size: 2KiB<br>total size: 102400MiB<br>operation: read<br>scope: global<br><br>Total operations: 52428800<br>Number of operations per second: 5857904.16<br><br>Total data size transferred: 102400.00 MiB<br>Amount of data size transferred per second: 11441.22 MiB/s<br><br>General statistics:<br>- total time: 8.9484s<br>- total number of events: 52428800<br><br>Latency (in milliseconds):<br>- minimum: 0.00<br>- average: 0.00<br>- maximum: 0.06<br>- 95th percentile: 0.00<br>- sum: 3698.89<br><br>Threads fairness:<br>- events (average): 52428800<br>- events (standard deviation): 0.00<br>- execution time (average): 3.6989<br>- execution time (standard deviation): 0.00<br><br>---<br><br>-> WRITE test<br><br>Number of threads: 1<br><br>block size: 2KiB<br>total size: 102400MiB<br>operation: write<br>scope: global<br><br>Total operations: 41970099<br>Number of operations per second: 4196287.26<br><br>Total data size transferred: 81972.85 MiB<br>Amount of data size transferred per second: 8195.87 MiB/s<br><br>General statistics:<br>- total time: 10.0001s<br>- total number of events: 41970099<br><br>Latency (in milliseconds):<br>- minimum: 0.00<br>- average: 0.00<br>- maximum: 0.05<br>- 95th percentile: 0.00<br>- sum: 5780.69<br><br>Threads fairness:<br>- events (average): 41970099.0000<br>- events (standard deviation): 0.00<br>- execution time (average): 5.7807<br>- execution time (standard deviation): 0.00     |
| `c5d.large` | Number of threads: 4<br><br>Prime numbers limit: 20000<br><br>CPU speed: 754.88 events per second<br><br>General statistics:<br>- total time: 10.0018s<br>- total number of events: 7551<br><br>Latency (in milliseconds):<br>- minimum: 2.63<br>- average: 5.29<br>- maximum: 14.67<br>- 95th percentile: 10.65<br>- sum: 39969.19<br><br>Threads fairness:<br>- events (average): 1887.7500<br>- events (standard deviation): 0.83<br>- execution time (average): 9.9923<br>- execution time (standard deviation): 0.01 | -> READ test<br><br>Number of threads: 1<br><br>block size: 2KiB<br>total size: 102400MiB<br>operation: read<br>scope: global<br><br>Total operations: 52428800<br>Number of operations per second: 6821010.80<br><br>Total data size transferred: 102400.00 MiB<br>Amount of data size transferred per second: 13322.29 MiB/s<br><br>General statistics:<br>- total time: 7.6849s<br>- total number of events: 52428800<br><br>Latency (in milliseconds):<br>- minimum: 0.00<br>- average: 0.00<br>- maximum: 0.05<br>- 95th percentile: 0.00<br>- sum: 3179.09<br><br>Threads fairness:<br>- events (average): 52428800.0000<br>- events (standard deviation): 0.00<br>- execution time (average): 3.1791<br>- execution time (standard deviation): 0.00<br><br>---<br><br>-> WRITE test<br><br>Number of threads: 1<br><br>block size: 2KiB<br>total size:102400MiB<br>operation: write<br>scope: global<br><br>Total operations: 48784780<br>Number of operations per second: 4877744.32<br><br>Total data size transferred: 95282.77 MiB<br>Amount of data size transferred per second: 9526.84 MiB/s<br><br>General statistics:<br>- total time: 10.0001s<br>- total number of events: 48784780<br><br>Latency (in milliseconds):<br>- minimum: 0.00<br>- average: 0.00<br>- maximum: 0.06<br>- 95th percentile: 0.00<br>- sum: 5778.22<br><br>Threads fairness:<br>- events (average): 48784780.0000<br>- events (standard deviation): 0.00<br>- execution time (average): 5.7782<br>- execution time (standard deviation): 0.00 |

    > Region: US East (N. Virginia). Use `Ubuntu Server 22.04 LTS (HVM)` as AMI.

## Question 2: Measure the EC2 Network performance

1. (1 mark) The metrics of network performance include **TCP bandwidth** and **round-trip time (RTT)**. Within the same region, what network performance is experienced between instances of the same type and different types? In order to answer this question, you need to complete the following table.

    | Type                      | TCP b/w (Mbps) | RTT (ms) |
    | ------------------------- | -------------- | -------- |
    | `t2.small` - `t2.small`   |                |          |
    | `m5.large` - `m5.large`   |                |          |
    | `c5d.large` - `c5d.large` |                |          |
    | `t2.small` - `c5d.large`  |                |          |
    | `m5.large` - `c5d.large`  |                |          |
    | `m5.large` - `t2.small`   |                |          |

**Answer:**

|            Type           | TCP b/w (Mbps) | RTT (ms)                                                                    |
|:-------------------------:|----------------|-----------------------------------------------------------------------------|
|  `t2.small` - `t2.small`  | 1030           | minimum: 0.445<br>average: 0.635<br>maximum: 1.433<br>mean deviation: 0.288 |
|  `m5.large` - `m5.large`  | 4960           | minimum: 0.262<br>average: 0.289<br>maximum: 0.359<br>mean deviation: 0.027 |
| `c5d.large` - `c5d.large` | 4970           | minimum: 0.219<br>average: 0.235<br>maximum: 0.248<br>mean deviation: 0.006 |
|  `t2.small` - `c5d.large` | 1030           | minimum: 0.373<br>average: 0.417<br>maximum: 0.463<br>mean deviation: 0.028 |
|  `m5.large` - `c5d.large` | 4960           | minimum: 0.256<br>average: 0.265<br>maximum: 0.289<br>mean deviation: 0.009 |
|  `m5.large` - `t2.small`  | 1030           | minimum: 0.338<br>average: 0.515<br>maximum: 1.263<br>mean deviation: 0.291 |

    > Region: US East (N. Virginia). Use `Ubuntu Server 22.04 LTS (HVM)` as AMI.

3. (1 mark) What about the network performance for instances deployed in different regions? In order to answer this question, you need to complete the following table.

    | Connection                | TCP b/w (Mbps) | RTT (ms) |
    | ------------------------- | -------------- | -------- |
    | N. Virginia - Oregon      |                |          |
    | N. Virginia - N. Virginia |                |          |
    | Oregon - Oregon           |                |          |

**Answer:**

|         Connection        | TCP b/w (Mbps) | RTT (ms)                                                                       |
|:-------------------------:|----------------|--------------------------------------------------------------------------------|
|    N. Virginia - Oregon   | 26.8           | minimum: 59.767<br>average: 59.797<br>maximum: 59.864<br>mean deviation: 0.030 |
| N. Virginia - N. Virginia | 4960           | minimum: 0.171<br>average: 0.182<br>maximum: 0.197<br>mean deviation: 0.007    |
|      Oregon - Oregon      | 4970           | minimum: 0.129<br>average: 0.140<br>maximum: 0.147<br>mean deviation: 0.006    |
 
    > Region: US East (N. Virginia), US West (Oregon). Use `Ubuntu Server 22.04 LTS (HVM)` as AMI. All instances are `c5d.large`.
