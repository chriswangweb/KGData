# KGData
 各个行业知识图谱分享，关系抽取，数据清洗，提供 neo4j 批量导入格式

## 使用步骤

### 首先你要自行安装 neo4j

### 由于本方式是覆盖导入，建议创建一个全新的知识图谱库

### 解压后将两个文件放入 import 目录

### 执行导入语句
```
bin/neo4j-admin import --id-type=STRING --multiline-fields=true \
                       --nodes "import/entity10.csv"  \
                       --relationships "import/relationship10.csv" \
```

                       
导入成功显示如下：
```
IMPORT DONE in 3s 337ms. 
Imported:
  100000 nodes
  88362 relationships
  288361 properties
Peak memory usage: 1.03 GB
```

### 启动 neo4j，查看导入的数据

`MATCH (ee:my_entity) WHERE ee.name = "文天祥" RETURN ee;
`
点击展开子节点，返回效果如下
![image](https://github.com/chriswangweb/KGData/blob/master/1578500414912.jpg)
