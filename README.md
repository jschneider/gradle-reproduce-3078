# This is what I did to reproduce:

> gradle --version

```
------------------------------------------------------------
Gradle 4.4
------------------------------------------------------------

Build time:   2017-12-06 09:05:06 UTC
Revision:     cf7821a6f79f8e2a598df21780e3ff7ce8db2b82

Groovy:       2.4.12
Ant:          Apache Ant(TM) version 1.9.9 compiled on February 2 2017
JVM:          1.8.0_151 (Oracle Corporation 25.151-b12)
OS:           Linux 4.13.0-19-generic amd64
```


> gradle --stacktrace init

```
> Task :init FAILED
Maven to Gradle conversion is an incubating feature.


FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':init'.
> java.lang.StackOverflowError (no error message)

* Try:
Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Exception is:
org.gradle.api.tasks.TaskExecutionException: Execution failed for task ':init'.
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeActions(ExecuteActionsTaskExecuter.java:100)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.execute(ExecuteActionsTaskExecuter.java:70)
        at org.gradle.api.internal.tasks.execution.OutputDirectoryCreatingTaskExecuter.execute(OutputDirectoryCreatingTaskExecuter.java:51)
        at org.gradle.api.internal.tasks.execution.SkipUpToDateTaskExecuter.execute(SkipUpToDateTaskExecuter.java:62)
        at org.gradle.api.internal.tasks.execution.ResolveTaskOutputCachingStateExecuter.execute(ResolveTaskOutputCachingStateExecuter.java:54)
        at org.gradle.api.internal.tasks.execution.ValidatingTaskExecuter.execute(ValidatingTaskExecuter.java:60)
        at org.gradle.api.internal.tasks.execution.SkipEmptySourceFilesTaskExecuter.execute(SkipEmptySourceFilesTaskExecuter.java:97)
        at org.gradle.api.internal.tasks.execution.CleanupStaleOutputsExecuter.execute(CleanupStaleOutputsExecuter.java:87)
        at org.gradle.api.internal.tasks.execution.ResolveTaskArtifactStateTaskExecuter.execute(ResolveTaskArtifactStateTaskExecuter.java:52)
        at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:52)
        at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:54)
        at org.gradle.api.internal.tasks.execution.ExecuteAtMostOnceTaskExecuter.execute(ExecuteAtMostOnceTaskExecuter.java:43)
        at org.gradle.api.internal.tasks.execution.CatchExceptionTaskExecuter.execute(CatchExceptionTaskExecuter.java:34)
        at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker$1.run(DefaultTaskGraphExecuter.java:248)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:336)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:328)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:199)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:110)
        at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker.execute(DefaultTaskGraphExecuter.java:241)
        at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker.execute(DefaultTaskGraphExecuter.java:230)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker.processTask(DefaultTaskPlanExecutor.java:123)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker.access$200(DefaultTaskPlanExecutor.java:79)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker$1.execute(DefaultTaskPlanExecutor.java:104)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker$1.execute(DefaultTaskPlanExecutor.java:98)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionPlan.execute(DefaultTaskExecutionPlan.java:626)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionPlan.executeWithTask(DefaultTaskExecutionPlan.java:581)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker.run(DefaultTaskPlanExecutor.java:98)
        at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
        at org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
        at org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
Caused by: java.lang.StackOverflowError
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle$_generateFqn_closure17.doCall(Maven2Gradle.groovy:220)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:219)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)
        at org.gradle.buildinit.plugins.internal.maven.Maven2Gradle.generateFqn(Maven2Gradle.groovy:223)


* Get more help at https://help.gradle.org

BUILD FAILED in 0s
2 actionable tasks: 2 executed
```

