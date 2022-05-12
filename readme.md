ansible-playbook deploy_kafka.yml -i hosts




sed -i 's/hk.archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list
sed -i 's/security.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list


kafka server 

```conf


default.replication.factor=3 # 默认数据同步给3个节点
min.insync.replicas = 2 # 至少同步两个节点
delete.topic.enable=true # 禁止删除topic
message.max.bytes=5242880 # 5MB
max.request.size=5242880 # 5MB
replica.fetch.max.bytes=5242880 # 5MB
auto.create.topics.enable=false # 禁止自动创建topic
unclean.leader.election.enable = false # 防止数据丢失
log.segment.ms = 7776000000 # 3个月
retention.ms = 7776000000 # 3个月
log.retention.bytes = -1 # 这是默认值 表示broker允许存储任意容量的数据
retention.bytes = -1
auto.leader.rebalance.enable = false # 禁止定期rebalance

```