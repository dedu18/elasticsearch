# 本地运行编译
./gradlew localDistro

# 新增编译后的模块
cp -b config lib logs modules plugins eshome/

# 启动新增参数
-Des.path.home=/dedu/elasticsearch/eshome
-Des.path.conf=/dedu/elasticsearch/eshome/config
-Djava.security.policy=/dedu/elasticsearch/eshome/config/java.policy
-Dlog4j2.disable.jmx=true
-Xmx1g
-Xms1g

# 修改安全策略
./eshome/config/java.policy
grant {
  permission java.security.AllPermission;
};
