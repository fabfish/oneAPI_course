# Report

余致远 SA 22011090

## Part I

1.   clinfo: machine information 

     >   clinfo > clinfo.log

2.   Basic Linux Commands 

3.   Compiler first DPC++ Program - run local by changing device 

     >   qsub -I -l nodes=1:gpu:ppn=2 -d .
     >
     >   dpcpp basic_parafor.cpp –o a.out

     >   ./a.out

     ```shell
     Selected GPU device: Intel(R) UHD Graphics [0x9a60]
     
     Data Result
     0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 
     Task Done!
     ```

4.   pbsnodes, check available nodes 

     ```shell
     qsub: waiting for job 2317202.v-qsvr-1.aidevcloud to start
     qsub: job 2317202.v-qsvr-1.aidevcloud ready
     
     
     ########################################################################
     #      Date:           Sun 11 Jun 2023 07:50:07 AM PDT
     #    Job ID:           2317202.v-qsvr-1.aidevcloud
     #      User:           u194952
     # Resources:           cput=75:00:00,neednodes=1:gpu:ppn=2,nodes=1:gpu:ppn=2,walltime=06:00:00
     ########################################################################
     ```

     

5.   Create a shell file, submit to GPU and check results



## Part II

1.   Review basic_parafor.cpp 

     主要是展示并行程序编写，GPU queue 中每个任务将 `device_mem` 中的元素乘以2。

2.   Change memory type to share 

     将 mem 类型改为 malloc shared，见 basic parafor shared.cpp

3.   Create new file, vector_add.cpp - change code and complete the kernel - using ND_range

     简单编写了一个函数用于示例。

     ```shell
     Problem size: c(1024) = a(1024) + b(1024)
     
     GPU Computation Time = 0.004254 (ms)
     ```

     

## 实验课练习



## 编程作业

