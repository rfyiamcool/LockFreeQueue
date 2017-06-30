# LockFreeQueue

## 介绍
使用Python构建无锁队列, 支持多生产者和多消费者. 使用gcc __sync_* 保证原子计数，Python元祖模拟类ringbuffer结构.

生产者在入库时会对比消费者的index. 如果数据差距过大, 会选择暂停Push数据.

当消费者拿到空值时, 选择性的自旋该ringbuffer槽位.
