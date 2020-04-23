# KGData
 各个行业知识图谱分享，关系抽取，数据清洗，提供 neo4j 批量导入格式
 
 __Menu__

| Topic                                    | Description                              | status                                  |
| :--------------------------------------- | :--------------------------------------- | --------------------------------------- |
| <a href="#百科数据">百科通用数据</a> | 百科通用数据 | 已完成，部分公开 |
| <a href="#医疗数据">医疗数据</a> | 疾病，症状，科室，用药等 | 已完成 |
| <a href="#垃圾分类">垃圾分类</a> | 上海垃圾分类数据 | 已完成，完全公开 |
| <a href="#汽车配件-车灯">汽车配件-车灯</a> | 各种型号各种年份汽车对应的各类车灯，安装方式 | 已完成 |
| <a href="#新冠疫情">新冠疫情</a> | 新冠疫情公开的行为轨迹，可供做知识推理【公益免费】 | V1.0完成 |
| <a href="#保险产品">保险产品</a> | 保险产品知识图谱，全网最全，种类超2.7w | 完成 |

# 《百科数据》

中文知识图谱，4000w实体，一亿关系，这是我精心整理、清洗、去重后的数据，数据格式已经处理，可用 neo4j-admin 直接导入，所有数据来源都是公开的百科或新闻数据。

由于 github文件大小限制，以下给出了部分数据，并附上了使用步骤，适合研究生交作业用，接受定制服务

## 使用步骤

### 1.首先你要自行安装 neo4j  下载地址：https://neo4j.com/download/

### 2.由于本方式是覆盖导入，建议创建一个全新的知识图谱库

### 3.解压后将两个文件放入 import 目录

### 4.执行导入语句
```
bin/neo4j-admin import --id-type=STRING --multiline-fields=true \
                       --nodes "import/entity10.csv"  \
                       --relationships "import/relationship10.csv" \
```

tips：
#### 1.windows下请去掉命令中的换行符
#### 2.windows下如果提示路径不对，可以将文件路径替换为完整路径                       
导入成功显示如下：

```
IMPORT DONE in 3s 337ms. 
Imported:
  100000 nodes
  88362 relationships
  288361 properties
Peak memory usage: 1.03 GB
```

### 5.启动 neo4j，查看导入的数据

`MATCH (ee:my_entity) WHERE ee.name = "文天祥" RETURN ee;
`
点击展开子节点，返回效果如下

![image](https://github.com/chriswangweb/KGData/blob/master/img/1578500414912.jpg)


# 《医疗数据》

### 1.创建一个新的图谱(注意不要启动)

### 2.下载数据

例如：链接:https://pan.baidu.com/s/1kMynr6lu13wyqTag7xUlpQ

### 3.将数据解压到 data/databases 下
### 4.启动服务
### 5.查看效果
![image](https://github.com/chriswangweb/KGData/blob/master/img/6.gif)

# 《垃圾分类》

### 1.使用方式同医疗数据

### 2.数据地址：https://github.com/chriswangweb/KGData/blob/master/%E5%9E%83%E5%9C%BE%E5%88%86%E7%B1%BB/graph.db.zip

### 3.效果
![image](https://github.com/chriswangweb/KGData/blob/master/img/7.gif)

# 新冠疫情

### 全网首份包含患者出行轨迹的知识图谱，换了超过 10 个数据源，目前的数据源算是最好的，但是还是包含较多的脏数据，后续会整理个精准度更高的版本

### 整理步骤如下：

| Topic                                    | Description                              |
| :--------------------------------------- | :--------------------------------------- |
| 病人基本信息 | ok |
| 关联病人 | - |
| 发病 | - |
| 确诊 | ok |
| 离鄂 | - |
| 出行信息 | ok |
| 活动 | ok |


### 1.使用方式同医疗数据

### 2.数据地址：https://github.com/chriswangweb/KGData/blob/master/ncov/graph.db.zip

网络不好的可以使用网盘地址
链接:https://pan.baidu.com/s/12-fLMV4jEc7BRXj4dUKQGg  密码:b08l

### 3.效果
![image](https://github.com/chriswangweb/KGData/blob/master/img/8.gif)

# 汽车车灯
## 哪个男人会不爱车

### 1.使用方式同医疗数据
### 2.数据地址
### 3.效果
![image](https://github.com/chriswangweb/KGData/blob/master/img/9.gif)

# 保险产品
## 全网最全，种类超2.7w
- 公司名称
- 产品名称
- 产品类别
- 设计类型
- 产品特殊属性
- 承保方式
- 保险期间类型
- 产品交费方式
- 产品条款文字编码
- 产品销售状态
- 停止销售日期

### 1.使用方式同医疗数据
### 2.数据地址：闲鱼搜索鱼塘：知识图谱
### 3.效果
![image](https://github.com/chriswangweb/KGData/blob/master/img/10.gif)

# 联系作者

#### 公众号：作者微信：AI-decoder,作者邮箱联系方式：chris.wang.web@gmail.com

捐赠作者（捐赠将用来购买服务器，OSS，更快的处理速度，更多的数据，更快的下载速度）

![image](https://github.com/chriswangweb/KGData/blob/master/img/WX2.png)