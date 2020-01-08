# KGData
 各个行业知识图谱分享，关系抽取，数据清洗，提供 neo4j 批量导入格式

由于本方式是覆盖导入，建议创建一个全新的知识图谱库

将两个文件放入 import 目录

执行导入语句
bin/neo4j-admin import --id-type=STRING --multiline-fields=true \
                       --nodes "import/entity10.csv"  \
                       --relationships "import/relationship10.csv" \
                       
导入成功显示如下：
IMPORT DONE in 3s 337ms. 
Imported:
  100000 nodes
  88362 relationships
  288361 properties
Peak memory usage: 1.03 GB