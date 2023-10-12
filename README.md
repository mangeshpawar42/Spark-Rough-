# Spark-Rough-


     at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 32 more

Driver stacktrace:
        at org.apache.spark.scheduler.DAGScheduler.failJobAndIndependentStages(DAGScheduler.scala:2844)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$abortStage$2(DAGScheduler.scala:2780)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$abortStage$2$adapted(DAGScheduler.scala:2779)
        at scala.collection.mutable.ResizableArray.foreach(ResizableArray.scala:62)
        at scala.collection.mutable.ResizableArray.foreach$(ResizableArray.scala:55)
        at scala.collection.mutable.ArrayBuffer.foreach(ArrayBuffer.scala:49)
        at org.apache.spark.scheduler.DAGScheduler.abortStage(DAGScheduler.scala:2779)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$handleTaskSetFailed$1(DAGScheduler.scala:1242)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$handleTaskSetFailed$1$adapted(DAGScheduler.scala:1242)
        at scala.Option.foreach(Option.scala:407)
        at org.apache.spark.scheduler.DAGScheduler.handleTaskSetFailed(DAGScheduler.scala:1242)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.doOnReceive(DAGScheduler.scala:3048)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:2982)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:2971)
        at org.apache.spark.util.EventLoop$$anon$1.run(EventLoop.scala:49)
        at org.apache.spark.scheduler.DAGScheduler.runJob(DAGScheduler.scala:984)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2398)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2419)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2438)
        at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:530)
        at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:483)
        at org.apache.spark.sql.execution.CollectLimitExec.executeCollect(limit.scala:61)
        at org.apache.spark.sql.execution.adaptive.AdaptiveSparkPlanExec.$anonfun$executeCollect$1(AdaptiveSparkPlanExec.scala:374)
        at org.apache.spark.sql.execution.adaptive.AdaptiveSparkPlanExec.withFinalPlanUpdate(AdaptiveSparkPlanExec.scala:402)
        at org.apache.spark.sql.execution.adaptive.AdaptiveSparkPlanExec.executeCollect(AdaptiveSparkPlanExec.scala:374)
        at org.apache.spark.sql.Dataset.collectFromPlan(Dataset.scala:4344)
        at org.apache.spark.sql.Dataset.$anonfun$head$1(Dataset.scala:3326)
        at org.apache.spark.sql.Dataset.$anonfun$withAction$2(Dataset.scala:4334)
        at org.apache.spark.sql.execution.QueryExecution$.withInternalError(QueryExecution.scala:546)
        at org.apache.spark.sql.Dataset.$anonfun$withAction$1(Dataset.scala:4332)
        at org.apache.spark.sql.execution.SQLExecution$.$anonfun$withNewExecutionId$6(SQLExecution.scala:125)
        at org.apache.spark.sql.execution.SQLExecution$.withSQLConfPropagated(SQLExecution.scala:201)
        at org.apache.spark.sql.execution.SQLExecution$.$anonfun$withNewExecutionId$1(SQLExecution.scala:108)
        at org.apache.spark.sql.SparkSession.withActive(SparkSession.scala:900)
        at org.apache.spark.sql.execution.SQLExecution$.withNewExecutionId(SQLExecution.scala:66)
        at org.apache.spark.sql.Dataset.withAction(Dataset.scala:4332)
        at org.apache.spark.sql.Dataset.head(Dataset.scala:3326)
        at org.apache.spark.sql.Dataset.take(Dataset.scala:3549)
        at org.apache.spark.sql.Dataset.getRows(Dataset.scala:280)
        at org.apache.spark.sql.Dataset.showString(Dataset.scala:315)
        at jdk.internal.reflect.GeneratedMethodAccessor62.invoke(Unknown Source)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:52)
        at java.base/java.lang.reflect.Method.invoke(Method.java:580)
        at py4j.reflection.MethodInvoker.invoke(MethodInvoker.java:244)
        at py4j.reflection.ReflectionEngine.invoke(ReflectionEngine.java:374)
        at py4j.Gateway.invoke(Gateway.java:282)
        at py4j.commands.AbstractCommand.invokeMethod(AbstractCommand.java:132)
        at py4j.commands.CallCommand.execute(CallCommand.java:79)
        at py4j.ClientServerConnection.waitForCommands(ClientServerConnection.java:182)
        at py4j.ClientServerConnection.run(ClientServerConnection.java:106)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.api.python.PythonRDD.compute(PythonRDD.scala:67)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        ... 1 more
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 32 more

>>> def uppercase(in_str):
...     out_str = in_str.upper()
...     return out_str
... print(uppercase('hello'))
  File "<stdin>", line 4
    print(uppercase('hello'))
    ^^^^^
SyntaxError: invalid syntax
>>>
>>> def uppercase(in_str):   r()
... 
  File "<stdin>", line 2

    ^
IndentationError: expected an indented block after function definition on line 1
>>>
>>> def uppercase(in_str):
...     out_str = in_str.upper()
...     return out_str
... 
>>> print(uppercase('hello'))
HELLO
>>> uppercaseudf = udf(lambda x : uppercase(x), StringType())
>>> empDF.select(col('Employee_id'),col('last_name'),uppercaseudf(col('firstname'))).show() 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\sql\dataframe.py", line 3223, in select
    jdf = self._jdf.select(self._jcols(*cols))
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\lib\py4j-0.10.9.7-src.zip\py4j\java_gateway.py", line 1322, in __call__
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\errors\exceptions\captured.py", line 185, in deco
    raise converted from None
pyspark.errors.exceptions.captured.AnalysisException: [UNRESOLVED_COLUMN.WITH_SUGGESTION] A column or function parameter with name `firstnameolved. Did you mean one of the following? [`EMAIL`, `JOB_ID`, `SALARY`, `HIRE_DATE`, `LAST_NAME`].;
'Project [Employee_id#303, last_name#305, unresolvedalias(<lambda>('firstname)#3707, Some(org.apache.spark.sql.Column$$Lambda/0x0000024f019f8+- Relation [EMPLOYEE_ID#303,FIRST_NAME#304,LAST_NAME#305,EMAIL#306,PHONE_NUMBER#307,HIRE_DATE#308,JOB_ID#309,SALARY#310,COMMISSION_PCT#311,MEPARTMENT_ID#313] csv

>>> empDF.select(col('Employee_id'),col('first__name'),uppercaseudf(col('first_name'))).show()     
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\sql\dataframe.py", line 3223, in select
    jdf = self._jdf.select(self._jcols(*cols))
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\lib\py4j-0.10.9.7-src.zip\py4j\java_gateway.py", line 1322, in __call__
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\errors\exceptions\captured.py", line 185, in deco
    raise converted from None
pyspark.errors.exceptions.captured.AnalysisException: [UNRESOLVED_COLUMN.WITH_SUGGESTION] A column or function parameter with name `first__naesolved. Did you mean one of the following? [`HIRE_DATE`, `JOB_ID`, `LAST_NAME`, `EMAIL`, `FIRST_NAME`].;
'Project [Employee_id#303, 'first__name, <lambda>(first_name#304)#3708 AS <lambda>(first_name)#3709]
+- Relation [EMPLOYEE_ID#303,FIRST_NAME#304,LAST_NAME#305,EMAIL#306,PHONE_NUMBER#307,HIRE_DATE#308,JOB_ID#309,SALARY#310,COMMISSION_PCT#311,MEPARTMENT_ID#313] csv

>>> empDF.select(col('EMPLOYEE_ID'),col('FIRST_NAME'),uppercaseudf(col('FIRST_NAME'))).show()   
Python was not found; run without arguments to install from the Microsoft Store, or disable this shortcut from Settings > Manage App Executio
23/10/12 17:17:20 ERROR Executor: Exception in task 0.0 in stage 154.0 (TID 127)
org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more
23/10/12 17:17:20 WARN TaskSetManager: Lost task 0.0 in stage 154.0 (TID 127) (DESKTOP-UU0L0RE executor driver): org.apache.spark.SparkExceptker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more

23/10/12 17:17:20 ERROR TaskSetManager: Task 0 in stage 154.0 failed 1 times; aborting job
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\sql\dataframe.py", line 959, in show
    print(self._jdf.showString(n, 20, vertical))
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\lib\py4j-0.10.9.7-src.zip\py4j\java_gateway.py", line 1322, in __call__
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\errors\exceptions\captured.py", line 179, in deco
    return f(*a, **kw)
           ^^^^^^^^^^^
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\lib\py4j-0.10.9.7-src.zip\py4j\protocol.py", line 326, in get_return_value
py4j.protocol.Py4JJavaError: An error occurred while calling o767.showString.
: org.apache.spark.SparkException: Job aborted due to stage failure: Task 0 in stage 154.0 failed 1 times, most recent failure: Lost task 0.0 (TID 127) (DESKTOP-UU0L0RE executor driver): org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more

Driver stacktrace:
        at org.apache.spark.scheduler.DAGScheduler.failJobAndIndependentStages(DAGScheduler.scala:2844)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$abortStage$2(DAGScheduler.scala:2780)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$abortStage$2$adapted(DAGScheduler.scala:2779)
        at scala.collection.mutable.ResizableArray.foreach(ResizableArray.scala:62)
        at scala.collection.mutable.ResizableArray.foreach$(ResizableArray.scala:55)
        at scala.collection.mutable.ArrayBuffer.foreach(ArrayBuffer.scala:49)
        at org.apache.spark.scheduler.DAGScheduler.abortStage(DAGScheduler.scala:2779)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$handleTaskSetFailed$1(DAGScheduler.scala:1242)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$handleTaskSetFailed$1$adapted(DAGScheduler.scala:1242)
        at scala.Option.foreach(Option.scala:407)
        at org.apache.spark.scheduler.DAGScheduler.handleTaskSetFailed(DAGScheduler.scala:1242)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.doOnReceive(DAGScheduler.scala:3048)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:2982)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:2971)
        at org.apache.spark.util.EventLoop$$anon$1.run(EventLoop.scala:49)
        at org.apache.spark.scheduler.DAGScheduler.runJob(DAGScheduler.scala:984)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2398)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2419)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2438)
        at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:530)
        at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:483)
        at org.apache.spark.sql.execution.CollectLimitExec.executeCollect(limit.scala:61)
        at org.apache.spark.sql.Dataset.collectFromPlan(Dataset.scala:4344)
        at org.apache.spark.sql.Dataset.$anonfun$head$1(Dataset.scala:3326)
        at org.apache.spark.sql.Dataset.$anonfun$withAction$2(Dataset.scala:4334)
        at org.apache.spark.sql.execution.QueryExecution$.withInternalError(QueryExecution.scala:546)
        at org.apache.spark.sql.Dataset.$anonfun$withAction$1(Dataset.scala:4332)
        at org.apache.spark.sql.execution.SQLExecution$.$anonfun$withNewExecutionId$6(SQLExecution.scala:125)
        at org.apache.spark.sql.execution.SQLExecution$.withSQLConfPropagated(SQLExecution.scala:201)
        at org.apache.spark.sql.execution.SQLExecution$.$anonfun$withNewExecutionId$1(SQLExecution.scala:108)
        at org.apache.spark.sql.SparkSession.withActive(SparkSession.scala:900)
        at org.apache.spark.sql.execution.SQLExecution$.withNewExecutionId(SQLExecution.scala:66)
        at org.apache.spark.sql.Dataset.withAction(Dataset.scala:4332)
        at org.apache.spark.sql.Dataset.head(Dataset.scala:3326)
        at org.apache.spark.sql.Dataset.take(Dataset.scala:3549)
        at org.apache.spark.sql.Dataset.getRows(Dataset.scala:280)
        at org.apache.spark.sql.Dataset.showString(Dataset.scala:315)
        at jdk.internal.reflect.GeneratedMethodAccessor62.invoke(Unknown Source)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:52)
        at java.base/java.lang.reflect.Method.invoke(Method.java:580)
        at py4j.reflection.MethodInvoker.invoke(MethodInvoker.java:244)
        at py4j.reflection.ReflectionEngine.invoke(ReflectionEngine.java:374)
        at py4j.Gateway.invoke(Gateway.java:282)
        at py4j.commands.AbstractCommand.invokeMethod(AbstractCommand.java:132)
        at py4j.commands.CallCommand.execute(CallCommand.java:79)
        at py4j.ClientServerConnection.waitForCommands(ClientServerConnection.java:182)
        at py4j.ClientServerConnection.run(ClientServerConnection.java:106)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        ... 1 more
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more

>>> empDF.show()
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+
|EMPLOYEE_ID|FIRST_NAME|LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|    JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+
|        198|    Donald| OConnell|DOCONNEL|650.507.9833|21-JUN-07|  SH_CLERK|  2600|            - |       124|           50|
|        199|   Douglas|    Grant|  DGRANT|650.507.9844|13-JAN-08|  SH_CLERK|  2600|            - |       124|           50|
|        200|  Jennifer|   Whalen| JWHALEN|515.123.4444|17-SEP-03|   AD_ASST|  4400|            - |       101|           10|
|        201|   Michael|Hartstein|MHARTSTE|515.123.5555|17-FEB-04|    MK_MAN| 13000|            - |       100|           20|
|        202|       Pat|      Fay|    PFAY|603.123.6666|17-AUG-05|    MK_REP|  6000|            - |       201|           20|
|        203|     Susan|   Mavris| SMAVRIS|515.123.7777|07-JUN-02|    HR_REP|  6500|            - |       101|           40|
|        204|   Hermann|     Baer|   HBAER|515.123.8888|07-JUN-02|    PR_REP| 10000|            - |       101|           70|
|        205|   Shelley|  Higgins|SHIGGINS|515.123.8080|07-JUN-02|    AC_MGR| 12008|            - |       101|          110|
|        206|   William|    Gietz|  WGIETZ|515.123.8181|07-JUN-02|AC_ACCOUNT|  8300|            - |       205|          110|
|        100|    Steven|     King|   SKING|515.123.4567|17-JUN-03|   AD_PRES| 24000|            - |        - |           90|
|        101|     Neena|  Kochhar|NKOCHHAR|515.123.4568|21-SEP-05|     AD_VP| 17000|            - |       100|           90|
|        102|       Lex|  De Haan| LDEHAAN|515.123.4569|13-JAN-01|     AD_VP| 17000|            - |       100|           90|
|        103| Alexander|   Hunold| AHUNOLD|590.423.4567|03-JAN-06|   IT_PROG|  9000|            - |       102|           60|
|        104|     Bruce|    Ernst|  BERNST|590.423.4568|21-MAY-07|   IT_PROG|  6000|            - |       103|           60|
|        105|     David|   Austin| DAUSTIN|590.423.4569|25-JUN-05|   IT_PROG|  4800|            - |       103|           60|
|        106|     Valli|Pataballa|VPATABAL|590.423.4560|05-FEB-06|   IT_PROG|  4800|            - |       103|           60|
|        107|     Diana|  Lorentz|DLORENTZ|590.423.5567|07-FEB-07|   IT_PROG|  4200|            - |       103|           60|
|        108|     Nancy|Greenberg|NGREENBE|515.124.4569|17-AUG-02|    FI_MGR| 12008|            - |       101|          100|
|        109|    Daniel|   Faviet| DFAVIET|515.124.4169|16-AUG-02|FI_ACCOUNT|  9000|            - |       108|          100|
|        110|      John|     Chen|   JCHEN|515.124.4269|28-SEP-05|FI_ACCOUNT|  8200|            - |       108|          100|
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+
only showing top 20 rows

>>> @udf(returnType = StringType())
... def uppercase(in_str):   r()                                                               
... 
  File "<stdin>", line 3

    ^
IndentationError: expected an indented block after function definition on line 2
>>> @udf(returnType = StringType())                                                            
... def uppercase(in_str):
...     out_str = in_str.upper()                                                               
...     return out_str        ()
... 
>>> empDF.select(uppercase(col('FIRST_NAME')).show()
... )
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'Column' object is not callable
>>> empDF.select(col('FIRST_NAME'),uppercase(col('FIRST_NAME')).show() 
... )
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'Column' object is not callable
>>> empDF.select(col('FIRST_NAME'),uppercase(col('FIRST_NAME'))).show() 
Python was not found; run without arguments to install from the Microsoft Store, or disable this shortcut from Settings > Manage App Executio
23/10/12 17:20:38 ERROR Executor: Exception in task 0.0 in stage 156.0 (TID 129)
org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more
23/10/12 17:20:38 WARN TaskSetManager: Lost task 0.0 in stage 156.0 (TID 129) (DESKTOP-UU0L0RE executor driver): org.apache.spark.SparkExceptker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more

23/10/12 17:20:38 ERROR TaskSetManager: Task 0 in stage 156.0 failed 1 times; aborting job
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\sql\dataframe.py", line 959, in show
    print(self._jdf.showString(n, 20, vertical))
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\lib\py4j-0.10.9.7-src.zip\py4j\java_gateway.py", line 1322, in __call__
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\errors\exceptions\captured.py", line 179, in deco
    return f(*a, **kw)
           ^^^^^^^^^^^
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\lib\py4j-0.10.9.7-src.zip\py4j\protocol.py", line 326, in get_return_value
py4j.protocol.Py4JJavaError: An error occurred while calling o800.showString.
: org.apache.spark.SparkException: Job aborted due to stage failure: Task 0 in stage 156.0 failed 1 times, most recent failure: Lost task 0.0 (TID 129) (DESKTOP-UU0L0RE executor driver): org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more

Driver stacktrace:
        at org.apache.spark.scheduler.DAGScheduler.failJobAndIndependentStages(DAGScheduler.scala:2844)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$abortStage$2(DAGScheduler.scala:2780)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$abortStage$2$adapted(DAGScheduler.scala:2779)
        at scala.collection.mutable.ResizableArray.foreach(ResizableArray.scala:62)
        at scala.collection.mutable.ResizableArray.foreach$(ResizableArray.scala:55)
        at scala.collection.mutable.ArrayBuffer.foreach(ArrayBuffer.scala:49)
        at org.apache.spark.scheduler.DAGScheduler.abortStage(DAGScheduler.scala:2779)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$handleTaskSetFailed$1(DAGScheduler.scala:1242)
        at org.apache.spark.scheduler.DAGScheduler.$anonfun$handleTaskSetFailed$1$adapted(DAGScheduler.scala:1242)
        at scala.Option.foreach(Option.scala:407)
        at org.apache.spark.scheduler.DAGScheduler.handleTaskSetFailed(DAGScheduler.scala:1242)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.doOnReceive(DAGScheduler.scala:3048)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:2982)
        at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:2971)
        at org.apache.spark.util.EventLoop$$anon$1.run(EventLoop.scala:49)
        at org.apache.spark.scheduler.DAGScheduler.runJob(DAGScheduler.scala:984)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2398)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2419)
        at org.apache.spark.SparkContext.runJob(SparkContext.scala:2438)
        at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:530)
        at org.apache.spark.sql.execution.SparkPlan.executeTake(SparkPlan.scala:483)
        at org.apache.spark.sql.execution.CollectLimitExec.executeCollect(limit.scala:61)
        at org.apache.spark.sql.Dataset.collectFromPlan(Dataset.scala:4344)
        at org.apache.spark.sql.Dataset.$anonfun$head$1(Dataset.scala:3326)
        at org.apache.spark.sql.Dataset.$anonfun$withAction$2(Dataset.scala:4334)
        at org.apache.spark.sql.execution.QueryExecution$.withInternalError(QueryExecution.scala:546)
        at org.apache.spark.sql.Dataset.$anonfun$withAction$1(Dataset.scala:4332)
        at org.apache.spark.sql.execution.SQLExecution$.$anonfun$withNewExecutionId$6(SQLExecution.scala:125)
        at org.apache.spark.sql.execution.SQLExecution$.withSQLConfPropagated(SQLExecution.scala:201)
        at org.apache.spark.sql.execution.SQLExecution$.$anonfun$withNewExecutionId$1(SQLExecution.scala:108)
        at org.apache.spark.sql.SparkSession.withActive(SparkSession.scala:900)
        at org.apache.spark.sql.execution.SQLExecution$.withNewExecutionId(SQLExecution.scala:66)
        at org.apache.spark.sql.Dataset.withAction(Dataset.scala:4332)
        at org.apache.spark.sql.Dataset.head(Dataset.scala:3326)
        at org.apache.spark.sql.Dataset.take(Dataset.scala:3549)
        at org.apache.spark.sql.Dataset.getRows(Dataset.scala:280)
        at org.apache.spark.sql.Dataset.showString(Dataset.scala:315)
        at jdk.internal.reflect.GeneratedMethodAccessor62.invoke(Unknown Source)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:52)
        at java.base/java.lang.reflect.Method.invoke(Method.java:580)
        at py4j.reflection.MethodInvoker.invoke(MethodInvoker.java:244)
        at py4j.reflection.ReflectionEngine.invoke(ReflectionEngine.java:374)
        at py4j.Gateway.invoke(Gateway.java:282)
        at py4j.commands.AbstractCommand.invokeMethod(AbstractCommand.java:132)
        at py4j.commands.CallCommand.execute(CallCommand.java:79)
        at py4j.ClientServerConnection.waitForCommands(ClientServerConnection.java:182)
        at py4j.ClientServerConnection.run(ClientServerConnection.java:106)
        at java.base/java.lang.Thread.run(Thread.java:1583)
Caused by: org.apache.spark.SparkException: Python worker failed to connect back.
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:203)
        at org.apache.spark.api.python.PythonWorkerFactory.create(PythonWorkerFactory.scala:109)
        at org.apache.spark.SparkEnv.createPythonWorker(SparkEnv.scala:124)
        at org.apache.spark.api.python.BasePythonRunner.compute(PythonRunner.scala:174)
        at org.apache.spark.sql.execution.python.BatchEvalPythonExec.evaluate(BatchEvalPythonExec.scala:54)
        at org.apache.spark.sql.execution.python.EvalPythonExec.$anonfun$doExecute$2(EvalPythonExec.scala:131)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2(RDD.scala:855)
        at org.apache.spark.rdd.RDD.$anonfun$mapPartitions$2$adapted(RDD.scala:855)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.rdd.MapPartitionsRDD.compute(MapPartitionsRDD.scala:52)
        at org.apache.spark.rdd.RDD.computeOrReadCheckpoint(RDD.scala:364)
        at org.apache.spark.rdd.RDD.iterator(RDD.scala:328)
        at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:93)
        at org.apache.spark.TaskContext.runTaskWithListeners(TaskContext.scala:161)
        at org.apache.spark.scheduler.Task.run(Task.scala:141)
        at org.apache.spark.executor.Executor$TaskRunner.$anonfun$run$4(Executor.scala:620)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally(SparkErrorUtils.scala:64)
        at org.apache.spark.util.SparkErrorUtils.tryWithSafeFinally$(SparkErrorUtils.scala:61)
        at org.apache.spark.util.Utils$.tryWithSafeFinally(Utils.scala:94)
        at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:623)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
        ... 1 more
Caused by: java.net.SocketTimeoutException: Accept timed out
        at java.base/sun.nio.ch.NioSocketImpl.timedAccept(NioSocketImpl.java:701)
        at java.base/sun.nio.ch.NioSocketImpl.accept(NioSocketImpl.java:745)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:698)
        at java.base/java.net.ServerSocket.platformImplAccept(ServerSocket.java:663)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:639)
        at java.base/java.net.ServerSocket.implAccept(ServerSocket.java:585)
        at java.base/java.net.ServerSocket.accept(ServerSocket.java:543)
        at org.apache.spark.api.python.PythonWorkerFactory.createSimpleWorker(PythonWorkerFactory.scala:190)
        ... 27 more

>>> empDF.show()
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+
|EMPLOYEE_ID|FIRST_NAME|LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|    JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+
|        198|    Donald| OConnell|DOCONNEL|650.507.9833|21-JUN-07|  SH_CLERK|  2600|            - |       124|           50|
|        199|   Douglas|    Grant|  DGRANT|650.507.9844|13-JAN-08|  SH_CLERK|  2600|            - |       124|           50|
|        200|  Jennifer|   Whalen| JWHALEN|515.123.4444|17-SEP-03|   AD_ASST|  4400|            - |       101|           10|
|        201|   Michael|Hartstein|MHARTSTE|515.123.5555|17-FEB-04|    MK_MAN| 13000|            - |       100|           20|
|        202|       Pat|      Fay|    PFAY|603.123.6666|17-AUG-05|    MK_REP|  6000|            - |       201|           20|
|        203|     Susan|   Mavris| SMAVRIS|515.123.7777|07-JUN-02|    HR_REP|  6500|            - |       101|           40|
|        204|   Hermann|     Baer|   HBAER|515.123.8888|07-JUN-02|    PR_REP| 10000|            - |       101|           70|
|        205|   Shelley|  Higgins|SHIGGINS|515.123.8080|07-JUN-02|    AC_MGR| 12008|            - |       101|          110|
|        206|   William|    Gietz|  WGIETZ|515.123.8181|07-JUN-02|AC_ACCOUNT|  8300|            - |       205|          110|
|        100|    Steven|     King|   SKING|515.123.4567|17-JUN-03|   AD_PRES| 24000|            - |        - |           90|
|        101|     Neena|  Kochhar|NKOCHHAR|515.123.4568|21-SEP-05|     AD_VP| 17000|            - |       100|           90|
|        102|       Lex|  De Haan| LDEHAAN|515.123.4569|13-JAN-01|     AD_VP| 17000|            - |       100|           90|
|        103| Alexander|   Hunold| AHUNOLD|590.423.4567|03-JAN-06|   IT_PROG|  9000|            - |       102|           60|
|        104|     Bruce|    Ernst|  BERNST|590.423.4568|21-MAY-07|   IT_PROG|  6000|            - |       103|           60|
|        105|     David|   Austin| DAUSTIN|590.423.4569|25-JUN-05|   IT_PROG|  4800|            - |       103|           60|
|        106|     Valli|Pataballa|VPATABAL|590.423.4560|05-FEB-06|   IT_PROG|  4800|            - |       103|           60|
|        107|     Diana|  Lorentz|DLORENTZ|590.423.5567|07-FEB-07|   IT_PROG|  4200|            - |       103|           60|
|        108|     Nancy|Greenberg|NGREENBE|515.124.4569|17-AUG-02|    FI_MGR| 12008|            - |       101|          100|
|        109|    Daniel|   Faviet| DFAVIET|515.124.4169|16-AUG-02|FI_ACCOUNT|  9000|            - |       108|          100|
|        110|      John|     Chen|   JCHEN|515.124.4269|28-SEP-05|FI_ACCOUNT|  8200|            - |       108|          100|
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+
only showing top 20 rows

>>> deptdf.show()
+-------------+--------------------+----------+-----------+
|DEPARTMENT_ID|     DEPARTMENT_NAME|MANAGER_ID|LOCATION_ID|
+-------------+--------------------+----------+-----------+
|           10|      Administration|       200|       1700|
|           20|           Marketing|       201|       1800|
|           30|          Purchasing|       114|       1700|
|           40|     Human Resources|       203|       2400|
|           50|            Shipping|       121|       1500|
|           60|                  IT|       103|       1400|
|           70|    Public Relations|       204|       2700|
|           80|               Sales|       145|       2500|
|           90|           Executive|       100|       1700|
|          100|             Finance|       108|       1700|
|          110|          Accounting|       205|       1700|
|          120|            Treasury|        - |       1700|
|          130|       Corporate Tax|        - |       1700|
|          140|  Control And Credit|        - |       1700|
|          150|Shareholder Services|        - |       1700|
|          160|            Benefits|        - |       1700|
|          170|       Manufacturing|        - |       1700|
|          180|        Construction|        - |       1700|
|          190|         Contracting|        - |       1700|
|          200|          Operations|        - |       1700|
+-------------+--------------------+----------+-----------+
only showing top 20 rows

>>> from pyspark.sql.window import Window
>>> windowspec = Window.partitionBy("DEPARTMENT_ID').orderBY('Salary')
  File "<stdin>", line 1
    windowspec = Window.partitionBy("DEPARTMENT_ID').orderBY('Salary')
                                    ^
SyntaxError: unterminated string literal (detected at line 1)
>>> windowspec = Window.partitionBy("DEPARTMENT_ID").orderBY('Salary') 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'WindowSpec' object has no attribute 'orderBY'. Did you mean: 'orderBy'?
>>> windowspec = Window.partitionBy("DEPARTMENT_ID").orderBy('Salary') 
>>> empDF.withColumn("salary_rank",rank() over(windowSpec)).show()
  File "<stdin>", line 1
    empDF.withColumn("salary_rank",rank() over(windowSpec)).show()
                                   ^^^^^^^^^^^^^^^^^^^^^^^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
>>> empDF.withColumn("salary_rank",rank().over(windowSpec)).show() 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'windowSpec' is not defined. Did you mean: 'windowspec'?
>>> empDF.withColumn("salary_rank",rank().over(windowspec)).show()  
+-----------+----------+-----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----------+
|EMPLOYEE_ID|FIRST_NAME|  LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|  JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|salary_rank|
+-----------+----------+-----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----------+
|        200|  Jennifer|     Whalen| JWHALEN|515.123.4444|17-SEP-03| AD_ASST|  4400|            - |       101|           10|          1|
|        202|       Pat|        Fay|    PFAY|603.123.6666|17-AUG-05|  MK_REP|  6000|            - |       201|           20|          1|
|        201|   Michael|  Hartstein|MHARTSTE|515.123.5555|17-FEB-04|  MK_MAN| 13000|            - |       100|           20|          2|
|        119|     Karen| Colmenares|KCOLMENA|515.127.4566|10-AUG-07|PU_CLERK|  2500|            - |       114|           30|          1|
|        118|       Guy|     Himuro| GHIMURO|515.127.4565|15-NOV-06|PU_CLERK|  2600|            - |       114|           30|          2|
|        117|     Sigal|     Tobias| STOBIAS|515.127.4564|24-JUL-05|PU_CLERK|  2800|            - |       114|           30|          3|
|        116|    Shelli|      Baida|  SBAIDA|515.127.4563|24-DEC-05|PU_CLERK|  2900|            - |       114|           30|          4|
|        115| Alexander|       Khoo|   AKHOO|515.127.4562|18-MAY-03|PU_CLERK|  3100|            - |       114|           30|          5|
|        114|       Den|   Raphaely|DRAPHEAL|515.127.4561|07-DEC-02|  PU_MAN| 11000|            - |       100|           30|          6|
|        203|     Susan|     Mavris| SMAVRIS|515.123.7777|07-JUN-02|  HR_REP|  6500|            - |       101|           40|          1|
|        132|        TJ|      Olson| TJOLSON|650.124.8234|10-APR-07|ST_CLERK|  2100|            - |       121|           50|          1|
|        128|    Steven|     Markle| SMARKLE|650.124.1434|08-MAR-08|ST_CLERK|  2200|            - |       120|           50|          2|
|        136|     Hazel| Philtanker|HPHILTAN|650.127.1634|06-FEB-08|ST_CLERK|  2200|            - |       122|           50|          2|
|        127|     James|     Landry| JLANDRY|650.124.1334|14-JAN-07|ST_CLERK|  2400|            - |       120|           50|          4|
|        135|        Ki|        Gee|    KGEE|650.127.1734|12-DEC-07|ST_CLERK|  2400|            - |       122|           50|          4|
|        131|     James|     Marlow| JAMRLOW|650.124.7234|16-FEB-05|ST_CLERK|  2500|            - |       121|           50|          6|
|        140|    Joshua|      Patel|  JPATEL|650.121.1834|06-APR-06|ST_CLERK|  2500|            - |       123|           50|          6|
|        198|    Donald|   OConnell|DOCONNEL|650.507.9833|21-JUN-07|SH_CLERK|  2600|            - |       124|           50|          8|
|        199|   Douglas|      Grant|  DGRANT|650.507.9844|13-JAN-08|SH_CLERK|  2600|            - |       124|           50|          8|
|        126|     Irene|Mikkilineni|IMIKKILI|650.124.1224|28-SEP-06|ST_CLERK|  2700|            - |       120|           50|         10|
+-----------+----------+-----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----------+
only showing top 20 rows

>>> windowspec = Window.partitionBy("DEPARTMENT_ID").orderBy(col('Salary').desc()).show()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'WindowSpec' object has no attribute 'show'
>>> windowspec = Window.partitionBy("DEPARTMENT_ID").orderBy(col('Salary').desc())       
>>> empDF.withColumn('salary_row', row_number().over(windowspec)).show()
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+----------+
|EMPLOYEE_ID|FIRST_NAME| LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|  JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|salary_row|
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+----------+
|        200|  Jennifer|    Whalen| JWHALEN|515.123.4444|17-SEP-03| AD_ASST|  4400|            - |       101|           10|         1|
|        201|   Michael| Hartstein|MHARTSTE|515.123.5555|17-FEB-04|  MK_MAN| 13000|            - |       100|           20|         1|
|        202|       Pat|       Fay|    PFAY|603.123.6666|17-AUG-05|  MK_REP|  6000|            - |       201|           20|         2|
|        114|       Den|  Raphaely|DRAPHEAL|515.127.4561|07-DEC-02|  PU_MAN| 11000|            - |       100|           30|         1|
|        115| Alexander|      Khoo|   AKHOO|515.127.4562|18-MAY-03|PU_CLERK|  3100|            - |       114|           30|         2|
|        116|    Shelli|     Baida|  SBAIDA|515.127.4563|24-DEC-05|PU_CLERK|  2900|            - |       114|           30|         3|
|        117|     Sigal|    Tobias| STOBIAS|515.127.4564|24-JUL-05|PU_CLERK|  2800|            - |       114|           30|         4|
|        118|       Guy|    Himuro| GHIMURO|515.127.4565|15-NOV-06|PU_CLERK|  2600|            - |       114|           30|         5|
|        119|     Karen|Colmenares|KCOLMENA|515.127.4566|10-AUG-07|PU_CLERK|  2500|            - |       114|           30|         6|
|        203|     Susan|    Mavris| SMAVRIS|515.123.7777|07-JUN-02|  HR_REP|  6500|            - |       101|           40|         1|
|        121|      Adam|     Fripp|  AFRIPP|650.123.2234|10-APR-05|  ST_MAN|  8200|            - |       100|           50|         1|
|        120|   Matthew|     Weiss|  MWEISS|650.123.1234|18-JUL-04|  ST_MAN|  8000|            - |       100|           50|         2|
|        122|     Payam|  Kaufling|PKAUFLIN|650.123.3234|01-MAY-03|  ST_MAN|  7900|            - |       100|           50|         3|
|        123|    Shanta|   Vollman|SVOLLMAN|650.123.4234|10-OCT-05|  ST_MAN|  6500|            - |       100|           50|         4|
|        124|     Kevin|   Mourgos|KMOURGOS|650.123.5234|16-NOV-07|  ST_MAN|  5800|            - |       100|           50|         5|
|        137|    Renske|    Ladwig| RLADWIG|650.121.1234|14-JUL-03|ST_CLERK|  3600|            - |       123|           50|         6|
|        129|     Laura|    Bissot| LBISSOT|650.124.5234|20-AUG-05|ST_CLERK|  3300|            - |       121|           50|         7|
|        133|     Jason|    Mallin| JMALLIN|650.127.1934|14-JUN-04|ST_CLERK|  3300|            - |       122|           50|         8|
|        125|     Julia|     Nayer|  JNAYER|650.124.1214|16-JUL-05|ST_CLERK|  3200|            - |       120|           50|         9|
|        138|   Stephen|    Stiles| SSTILES|650.121.2034|26-OCT-05|ST_CLERK|  3200|            - |       123|           50|        10|
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+----------+
only showing top 20 rows

>>> empDF.withColumn('salary_dense_rank', dense_rank().over(windowspec)).show() 
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----------------+
|EMPLOYEE_ID|FIRST_NAME| LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|  JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|salary_dense_rank|
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----------------+
|        200|  Jennifer|    Whalen| JWHALEN|515.123.4444|17-SEP-03| AD_ASST|  4400|            - |       101|           10|                1|
|        201|   Michael| Hartstein|MHARTSTE|515.123.5555|17-FEB-04|  MK_MAN| 13000|            - |       100|           20|                1|
|        202|       Pat|       Fay|    PFAY|603.123.6666|17-AUG-05|  MK_REP|  6000|            - |       201|           20|                2|
|        114|       Den|  Raphaely|DRAPHEAL|515.127.4561|07-DEC-02|  PU_MAN| 11000|            - |       100|           30|                1|
|        115| Alexander|      Khoo|   AKHOO|515.127.4562|18-MAY-03|PU_CLERK|  3100|            - |       114|           30|                2|
|        116|    Shelli|     Baida|  SBAIDA|515.127.4563|24-DEC-05|PU_CLERK|  2900|            - |       114|           30|                3|
|        117|     Sigal|    Tobias| STOBIAS|515.127.4564|24-JUL-05|PU_CLERK|  2800|            - |       114|           30|                4|
|        118|       Guy|    Himuro| GHIMURO|515.127.4565|15-NOV-06|PU_CLERK|  2600|            - |       114|           30|                5|
|        119|     Karen|Colmenares|KCOLMENA|515.127.4566|10-AUG-07|PU_CLERK|  2500|            - |       114|           30|                6|
|        203|     Susan|    Mavris| SMAVRIS|515.123.7777|07-JUN-02|  HR_REP|  6500|            - |       101|           40|                1|
|        121|      Adam|     Fripp|  AFRIPP|650.123.2234|10-APR-05|  ST_MAN|  8200|            - |       100|           50|                1|
|        120|   Matthew|     Weiss|  MWEISS|650.123.1234|18-JUL-04|  ST_MAN|  8000|            - |       100|           50|                2|
|        122|     Payam|  Kaufling|PKAUFLIN|650.123.3234|01-MAY-03|  ST_MAN|  7900|            - |       100|           50|                3|
|        123|    Shanta|   Vollman|SVOLLMAN|650.123.4234|10-OCT-05|  ST_MAN|  6500|            - |       100|           50|                4|
|        124|     Kevin|   Mourgos|KMOURGOS|650.123.5234|16-NOV-07|  ST_MAN|  5800|            - |       100|           50|                5|
|        137|    Renske|    Ladwig| RLADWIG|650.121.1234|14-JUL-03|ST_CLERK|  3600|            - |       123|           50|                6|
|        129|     Laura|    Bissot| LBISSOT|650.124.5234|20-AUG-05|ST_CLERK|  3300|            - |       121|           50|                7|
|        133|     Jason|    Mallin| JMALLIN|650.127.1934|14-JUN-04|ST_CLERK|  3300|            - |       122|           50|                7|
|        125|     Julia|     Nayer|  JNAYER|650.124.1214|16-JUL-05|ST_CLERK|  3200|            - |       120|           50|                8|
|        138|   Stephen|    Stiles| SSTILES|650.121.2034|26-OCT-05|ST_CLERK|  3200|            - |       123|           50|                8|
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----------------+
only showing top 20 rows

>>> empDF.withColumn('Sum', sum(salary).over(windowspec)).show()                
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'salary' is not defined
>>> empDF.withColumn('Sum', sum('salary').over(windowspec)).show() 
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----+
|EMPLOYEE_ID|FIRST_NAME| LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|  JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|  Sum|
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----+
|        200|  Jennifer|    Whalen| JWHALEN|515.123.4444|17-SEP-03| AD_ASST|  4400|            - |       101|           10| 4400|
|        201|   Michael| Hartstein|MHARTSTE|515.123.5555|17-FEB-04|  MK_MAN| 13000|            - |       100|           20|13000|
|        202|       Pat|       Fay|    PFAY|603.123.6666|17-AUG-05|  MK_REP|  6000|            - |       201|           20|19000|
|        114|       Den|  Raphaely|DRAPHEAL|515.127.4561|07-DEC-02|  PU_MAN| 11000|            - |       100|           30|11000|
|        115| Alexander|      Khoo|   AKHOO|515.127.4562|18-MAY-03|PU_CLERK|  3100|            - |       114|           30|14100|
|        116|    Shelli|     Baida|  SBAIDA|515.127.4563|24-DEC-05|PU_CLERK|  2900|            - |       114|           30|17000|
|        117|     Sigal|    Tobias| STOBIAS|515.127.4564|24-JUL-05|PU_CLERK|  2800|            - |       114|           30|19800|
|        118|       Guy|    Himuro| GHIMURO|515.127.4565|15-NOV-06|PU_CLERK|  2600|            - |       114|           30|22400|
|        119|     Karen|Colmenares|KCOLMENA|515.127.4566|10-AUG-07|PU_CLERK|  2500|            - |       114|           30|24900|
|        203|     Susan|    Mavris| SMAVRIS|515.123.7777|07-JUN-02|  HR_REP|  6500|            - |       101|           40| 6500|
|        121|      Adam|     Fripp|  AFRIPP|650.123.2234|10-APR-05|  ST_MAN|  8200|            - |       100|           50| 8200|
|        120|   Matthew|     Weiss|  MWEISS|650.123.1234|18-JUL-04|  ST_MAN|  8000|            - |       100|           50|16200|
|        122|     Payam|  Kaufling|PKAUFLIN|650.123.3234|01-MAY-03|  ST_MAN|  7900|            - |       100|           50|24100|
|        123|    Shanta|   Vollman|SVOLLMAN|650.123.4234|10-OCT-05|  ST_MAN|  6500|            - |       100|           50|30600|
|        124|     Kevin|   Mourgos|KMOURGOS|650.123.5234|16-NOV-07|  ST_MAN|  5800|            - |       100|           50|36400|
|        137|    Renske|    Ladwig| RLADWIG|650.121.1234|14-JUL-03|ST_CLERK|  3600|            - |       123|           50|40000|
|        129|     Laura|    Bissot| LBISSOT|650.124.5234|20-AUG-05|ST_CLERK|  3300|            - |       121|           50|46600|
|        133|     Jason|    Mallin| JMALLIN|650.127.1934|14-JUN-04|ST_CLERK|  3300|            - |       122|           50|46600|
|        125|     Julia|     Nayer|  JNAYER|650.124.1214|16-JUL-05|ST_CLERK|  3200|            - |       120|           50|53000|
|        138|   Stephen|    Stiles| SSTILES|650.121.2034|26-OCT-05|ST_CLERK|  3200|            - |       123|           50|53000|
+-----------+----------+----------+--------+------------+---------+--------+------+--------------+----------+-------------+-----+
only showing top 20 rows

>>> from pyspark.sql.functions import *
>>> spark.conf.set("spark.sql.autoBroadcastJoinThreshold',10248428234)
  File "<stdin>", line 1
    spark.conf.set("spark.sql.autoBroadcastJoinThreshold',10248428234)
                   ^
SyntaxError: unterminated string literal (detected at line 1)
>>> spark.conf.set("spark.sql.autoBroadcastJoinThreshold",10248428234) 
>>> empDF.join(broadcast(deptdf),empDF.DEPARTMENT_ID==deptdf.DEPARTMENT_ID,'inner').show()
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+-------------+------------+-----------+
|EMPLOYEE_ID|FIRST_NAME|LAST_NAME|   EMAIL|PHONE_NUMBER|HIRE_DATE|    JOB_ID|SALARY|COMMISSION_PCT|MANAGER_ID|DEPARTMENT_ID|DEPARTMENT_ID| DEANAGER_ID|LOCATION_ID|
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+-------------+------------+-----------+
|        198|    Donald| OConnell|DOCONNEL|650.507.9833|21-JUN-07|  SH_CLERK|  2600|            - |       124|           50|           50|   
      121|       1500|
|        199|   Douglas|    Grant|  DGRANT|650.507.9844|13-JAN-08|  SH_CLERK|  2600|            - |       124|           50|           50|   
      121|       1500|
|        200|  Jennifer|   Whalen| JWHALEN|515.123.4444|17-SEP-03|   AD_ASST|  4400|            - |       101|           10|           10|  A
      200|       1700|
|        201|   Michael|Hartstein|MHARTSTE|515.123.5555|17-FEB-04|    MK_MAN| 13000|            - |       100|           20|           20|   
      201|       1800|
|        202|       Pat|      Fay|    PFAY|603.123.6666|17-AUG-05|    MK_REP|  6000|            - |       201|           20|           20|   
      201|       1800|
|        203|     Susan|   Mavris| SMAVRIS|515.123.7777|07-JUN-02|    HR_REP|  6500|            - |       101|           40|           40| Hu
      203|       2400|
|        204|   Hermann|     Baer|   HBAER|515.123.8888|07-JUN-02|    PR_REP| 10000|            - |       101|           70|           70|Pub
      204|       2700|
|        205|   Shelley|  Higgins|SHIGGINS|515.123.8080|07-JUN-02|    AC_MGR| 12008|            - |       101|          110|          110|   
      205|       1700|
|        206|   William|    Gietz|  WGIETZ|515.123.8181|07-JUN-02|AC_ACCOUNT|  8300|            - |       205|          110|          110|   
      205|       1700|
|        100|    Steven|     King|   SKING|515.123.4567|17-JUN-03|   AD_PRES| 24000|            - |        - |           90|           90|   
      100|       1700|
|        101|     Neena|  Kochhar|NKOCHHAR|515.123.4568|21-SEP-05|     AD_VP| 17000|            - |       100|           90|           90|   
      100|       1700|
|        102|       Lex|  De Haan| LDEHAAN|515.123.4569|13-JAN-01|     AD_VP| 17000|            - |       100|           90|           90|   
      100|       1700|
|        103| Alexander|   Hunold| AHUNOLD|590.423.4567|03-JAN-06|   IT_PROG|  9000|            - |       102|           60|           60|   
      103|       1400|
|        104|     Bruce|    Ernst|  BERNST|590.423.4568|21-MAY-07|   IT_PROG|  6000|            - |       103|           60|           60|   
      103|       1400|
|        105|     David|   Austin| DAUSTIN|590.423.4569|25-JUN-05|   IT_PROG|  4800|            - |       103|           60|           60|   
      103|       1400|
|        106|     Valli|Pataballa|VPATABAL|590.423.4560|05-FEB-06|   IT_PROG|  4800|            - |       103|           60|           60|   
      103|       1400|
|        107|     Diana|  Lorentz|DLORENTZ|590.423.5567|07-FEB-07|   IT_PROG|  4200|            - |       103|           60|           60|   
      103|       1400|
|        108|     Nancy|Greenberg|NGREENBE|515.124.4569|17-AUG-02|    FI_MGR| 12008|            - |       101|          100|          100|   
      108|       1700|
|        109|    Daniel|   Faviet| DFAVIET|515.124.4169|16-AUG-02|FI_ACCOUNT|  9000|            - |       108|          100|          100|   
      108|       1700|
|        110|      John|     Chen|   JCHEN|515.124.4269|28-SEP-05|FI_ACCOUNT|  8200|            - |       108|          100|          100|   
      108|       1700|
+-----------+----------+---------+--------+------------+---------+----------+------+--------------+----------+-------------+-------------+------------+-----------+
only showing top 20 rows

>>>  resultDf.write.mode("overwrite").option("header",True).save("/output/result")
  File "<stdin>", line 1
    resultDf.write.mode("overwrite").option("header",True).save("/output/result")
IndentationError: unexpected indent
>>> resultDf.write.mode("overwrite").option("header",True).save("/output/result")  
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'resultDf' is not defined
>>> empDF.getNumPartitions()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "C:\spark\spark-3.5.0-bin-hadoop3\python\pyspark\sql\dataframe.py", line 3123, in __getattr__
    raise AttributeError(
AttributeError: 'DataFrame' object has no attribute 'getNumPartitions'
>>> empDF.rdd.getNumPartitions() 
1
>>> newEmp = empDF.repartition(10)
>>> newEmp.rdd.getNumPartitions()
10
>>> emp1 = newEmp.repartition(5) 
>>> emp1.rdd.getNumPartitions()
5
>>> emp2 = empDF.coalesce(3)
>>> emp2.rdd.getNumPartitions()
1
>>> emp2 = emp1.coalesce(3)     
>>> emp2.rdd.getNumPartitions()
3
>>> emp3 = emp1.coalesce(5)
>>> emp3.rdd.getNumPartitions()
5
>>> emp3 = emp2.coalesce(5)     
>>> emp3.rdd.getNumPartitions()
5
>>> empDF.rdd.getNumPartitions()
1
>>> empDF.coalesce(5)
DataFrame[EMPLOYEE_ID: int, FIRST_NAME: string, LAST_NAME: string, EMAIL: string, PHONE_NUMBER: string, HIRE_DATE: string, JOB_ID: string, SAISSION_PCT: string, MANAGER_ID: string, DEPARTMENT_ID: int]
>>> empnew = empDF.coalesce(5) 
>>> empnew.rdd.getNumPartitions()
1
>>> jsonDF = spark.read.json(r'C:\Users\Rohan\Downloads\Spark-main\Spark-main\jsonexample.json')
>>> jsonDF.show()
+------------+----+-----+-------+
|      Array1|Num1|Text1|  Text2|
+------------+----+-----+-------+
|   [7, 8, 9]| 5.0|Hello|GoodBye|
|[70, 88, 91]| 6.5| This|   That|
|   [1, 2, 3]| 2.0|  Yes|     No|
+------------+----+-----+-------+

>>> jsonDF.printSchema()
root
 |-- Array1: array (nullable = true)
 |    |-- element: long (containsNull = true)
 |-- Num1: double (nullable = true)
 |-- Text1: string (nullable = true)
 |-- Text2: string (nullable = true)

>>> jsonDF.select(jsonDF.Text1,jsonDF.Array1).show()
+-----+------------+
|Text1|      Array1|
+-----+------------+
|Hello|   [7, 8, 9]|
| This|[70, 88, 91]|
|  Yes|   [1, 2, 3]|
+-----+------------+

>>> jsonDF.select(jsonDF.Text1,jsonDF.Array1[1]).show()
+-----+---------+
|Text1|Array1[1]|
+-----+---------+
|Hello|        8|
| This|       88|
|  Yes|        2|
+-----+---------+

>>> jsonDF.select(jsonDF.Text1,explode(jsonDF.Array1)).show()
+-----+---+
|Text1|col|
+-----+---+
|Hello|  7|
|Hello|  8|
|Hello|  9|
| This| 70|
| This| 88|
| This| 91|
|  Yes|  1|
|  Yes|  2|
|  Yes|  3|
+-----+---+

>>> from pyspark.sql import *
>>>   
