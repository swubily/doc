1. mvn dependency:tree 查看maven依赖树，排除错误依赖

mvn dependency:tree -s /C/wzc/apache/maven/conf/settings-yi.xml

2. dependencymanagement 定义在parent里面，继承的module 只需要写名字 不用填写版本