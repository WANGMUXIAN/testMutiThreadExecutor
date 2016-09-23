# testMutiThreadExecutor
关于线程池的东西，在ZK的实战中用的比较多
1 master选举中用到了ScheduleExecutorService，ScheduleExecutorService ses = Executors.newScheduleThreadPool(); ses.schedule();
2 分布式队列用到了ScheduleExecutorService，用到了CountDownLatch
3 命名服务中用到了ExecutorService,ExecutorService es = Executors.newThreadPool(); es.execute();
ScheduleExecutorService延迟线程用到了schedule方法
ExecutorService调度线程用到了execute方法

多个线程之前协作可以使用CountDownLatch，初始化CountDownLatch类时，会有一个数字，当一个线程调用latch.await时，该线程会阻塞执行，当调用latch.countDown，会减一，直到减为零后，才继续执行。

调度线程时也可以视同Timer类，调度线程的接口需要使用继承自TimerTask()的类，监控项目中用到了
