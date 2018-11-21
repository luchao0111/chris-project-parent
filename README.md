### chris-project-parent  分3个工程
 ##### 1. 基础Common依赖工程  
  > 提供基础类,如异常类等
  > chris-cache-plugin 和 chris-retry-plugin都依赖于这个工程  
  
 ##### 2. redis依赖以及幂等扩展工程  
  > 提供实现分布式锁的redis操作类  
  > 提供幂等注解及其实现可以通过注解简单实现基于Redis缓存的幂等处理  
 ##### 3.消息级延迟补偿  
 > 基于RabbitMQ的rabbitmq_delayed_message_exchange插件的消息级延迟消息实现  
 > 　　使用场景为:  
 >　　　　　当请求/处理一些弱一致性的操作失败,可以将其放入队列中,过一段时间再消费这条消息(过期后进入消费队列)
 >　　　　　消费时以post请求的方式请求本系统的某个补偿接口


