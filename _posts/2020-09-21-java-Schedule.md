Java定时任务Schedule实现的4种方式:
web link: https://blog.csdn.net/paladinzh/article/details/88011279




---
"Schedule" plus "ExecutorPool"
---
i.e.
    public void scheduleUpdateMultipleVerifiers(String trustedCategory){

        try {
            //However, the Executor interface does not strictly require that execution be asynchronous.
            // In the simplest case, an executor can run the submitted task immediately in the caller's thread:
            //instance.executor.execute(() -> { So the function will cause
            //  the Failed to generate updateMultipleVerifiers: classloader:sun.misc.Launcher$AppClassLoader@8efb846
            executor.submit(() -> {
                LOG.info("Entry updateMultipleVerifiers");
                try {
                    LOG.info("After addTrustedCert of {}, updateMultipleVerifiers.", trustedCategory);
                    updateMultipleVerifiers(trustedCategory);
                } catch (NsdsCertException e) {
                    LOG.debug("updateMultipleVerifiers of {} failure.", trustedCategory);
                }catch (Throwable t)
                {
                    LOG.warn("Fail to updateMultipleVerifiers:{}",trustedCategory,t);
                }
                LOG.info("Exit updateMultipleVerifiers");
            });
        }catch (Throwable t)
        {
            LOG.warn("instance.executor.execute fail.",t);
        }
    }






============
ScheduledExecutorService executor = Executors.newScheduledThreadPool(2,new ThreadFactory() {
        private final String parentThreadName=Thread.currentThread().getName();

        private final AtomicInteger count = new AtomicInteger(1);
        @Override
        public Thread newThread(Runnable r) {

            final Thread t = new Thread(r, String.format(parentThreadName+"_ImmJNICertHandler-%d",count.getAndIncrement() ));
            t.setContextClassLoader(mainloader);
            t.setDaemon(true);
            LOG.info("{}  is started. mainloader:{}", t.getName(),mainloader);
            return t;
        }
    });










