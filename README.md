csup
====

Helper to create/update cscope databases in a optimized way.

When working on big projects (e.g. kernel) a good approach for cscope management is to create two different databases. One for directories that you're not going to change and another one to files that you will work on.

Cscope and vi are prepared to work with more than one database at same time to find symbols. Use their documentation to know how to do such task.

First you need to create the databases:

csup create --exclude DIR1 DIR2... --work DIR3 DIR4...

The files cscope.out.proj and cscope.out.work will be created, they are your databases. The files cscope.files.proj and cscope.files.work will be created also. Do not delete them, they are essential to update the databases.

To update your databases, just type:

csup

Example: Suppose you're working on the bluetooth subsystem in the kernel project:

csup create --exclude Documentation samples scripts tools usr debian --work net/bluetooth include/net/bluetooth
