git cherry-pick 使用指南:
web link: https://www.jianshu.com/p/08c3f1804b36

i.e.
git cherry-pick可以选择某一个分支中的一个或几个commit(s)来进行操作。

例如，假设我们有个稳定版本的分支，叫v2.0，另外还有个开发版本的分支v3.0，我们不能直接把两个分支合并，这样会导致稳定版本混乱，但是又想增加一个v3.0中的功能到v2.0中，这里就可以使用cherry-pick了,其实也就是对已经存在的commit 进行再次提交.

 =====> =====> =====> =====> =====> =====>

































