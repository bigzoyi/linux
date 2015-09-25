#概念

##物理cpu
  实际Server中插槽上的CPU个数,物理cpu数量，可以数不重复的 physical id 有几个
  
##逻辑CPU 
 Linux用户对 /proc/cpuinfo 这个文件肯定不陌生. 它是用来存储cpu硬件信息的
              信息内容分别列出了processor 0 – n 的规格。这里需要注意，如果你认为n就是真实的cpu数的话, 就大错特错了
              一般情况，我们认为一颗cpu可以有多核，加上intel的超线程技术(HT), 可以在逻辑上再分一倍数量的cpu core出来
              逻辑CPU数量=物理cpu数量 x cpu cores 这个规格值 x 2(如果支持并开启ht)
              备注一下：Linux下top查看的CPU也是逻辑CPU个数
            
##CPU核数
  一块CPU上面能处理数据的芯片组的数量。
  比如现在的i5 760,是双核心四线程的CPU、而 i5 2250 是四核心四线程的CPU
  一般来说，物理CPU个数×每颗核数就应该等于逻辑CPU的个数，如果不相等的话，则表示服务器的CPU支持超线程技术 
  
#查看CPU信息

##查看物理CPU的个数

###cat /proc/cpuinfo |grep "physical id"|sort |uniq|wc -l 

##查看逻辑CPU的个数
###cat /proc/cpuinfo |grep "processor"|wc -l  

##查看CPU是几核
###cat /proc/cpuinfo |grep "cores"|uniq 
