# HINs
王总软件学报相关实验


## 预处理

### 利用neo4j构建网络

#### 地点类别
- 食堂C {c1, c2, ... , cn}
- 校车站B {b1, b2, ... , bn}
- 宿舍D {d1, d2, ... , dn}

#### 时间划分
每天分成4个时间段：
- t0: 0~6
- t1: 6~12
- t2: 12~18
- t3: 18~24 

选取一周时间，划分为7x4共28个时间片T {t1, t2, ... , t28}

#### 实体节点：
- 学生U {u1, u2, ... , un} 其中ui <name, stuId>
- 事件E {e1, e2, ... , en} 其中ei <tj, ck/bk/dk>
- 消费金额M {m0, m1, ... , m5}

#### 边：
由学生节点指向事件节点，具有次数属性作为权重
from u
to e
property : times

例如： 
          
ui -------times = 5------> ei

学生ui在这一周中，给时间片tj内在地点ck消费了5次


#### 消费分类:
- 食堂消费：1,2,3,4,6,8,9,10,11,13,14,15
- 面包房：5,16 
- 洗澡: 7,12,17
- 超市: 21
- 校车: 18,19,20
- 
