Differences : @SessionScoped vs @Stateful and @ApplicationScoped vs @Singleton [closed]:
web link: https://stackoverflow.com/questions/24105807/differences-sessionscoped-vs-stateful-and-applicationscoped-vs-singleton#:~:text=%40ApplicationScoped%20is%20just%20a%20scope%2C%20while%20%40Singleton%20is,%40Lock%29%20and%20with%20eager%20construction%20behavior%20%28via%20%40Startup%29.

i.e. 
@SessionScoped denotes a scope while @Stateful is in a way what we would now call a stereotype. @Stateful adds a number a services to a bean, among which transactional behavior and passivation.
Central to @Stateful is however its session behavior, which indeed overlaps with the session scope.
The difference is that the session scope is tied to the HTTP session, while @Stateful is an open-ended user managed session, with its lifetime managed by a client that has a reference to the bean proxy.

 ----- ----- -----
There's a somewhat similar story for @ApplicationScoped and @Singleton, although without the legacy (@Singleton is a fairly new thing). 
@ApplicationScoped is just a scope, while @Singleton is a bean type (stereotype if you wish), which doesn't only give you application scoped behavior, but also provides you with transactional behavior again, with automatic locking (which can be tuned via @Lock) and with eager construction behavior (via @Startup).



 =====> =====> =====> =====> =====> 



























