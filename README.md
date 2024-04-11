# zengjiandong.cn

[TOC]

## 20240411
——痛失转运良机，从此需要更加努力了

天时地利人不和，遇见贵人，但奈何自己还没准备好，悲痛！

从今以后，从零开始，点点滴滴、积极向上、勇敢坚强！

## 20230415
——Oracle相关操作

时隔多年，重拾Oracle相关知识

### 查看数据库字符集
```shell
select * from v$nls_parameters where parameter = 'NLS_CHARACTERSET';
```

### 用户修改密码、解锁

```sql
-- 管理员登录
sqlplus / as sysdba
-- 解锁用户
ALTER USER 用户名 ACCOUNT UNLOCK;
-- 修改密码
ALTER USER scott identified by "tiger";
-- 设置用户密码无限次尝试登录
ALTER PROFILE DEFAULT LIMIT FAILED_LOGIN_ATTEMPTS UNLIMITED;
-- 设置用户密码不过期
ALTER PROFILE DEFAULT LIMIT PASSWORD_LIFE_TIME UNLIMITED;
```

### 表空间与用户创建
```sql
CREATE TEMPORARY TABLESPACE NB_TEMP 
		TEMPFILE 'e:\OracleData\NB_TEMP.DBF' 
		SIZE 32M 
		AUTOEXTEND ON 
		NEXT 32M MAXSIZE UNLIMITED 
		EXTENT MANAGEMENT LOCAL;
		 
CREATE TABLESPACE NB_DATA
         LOGGING
         DATAFILE 'e:\OracleData\NB_DATA.DBF'
         SIZE 32M
         AUTOEXTEND ON
         NEXT 32M MAXSIZE UNLIMITED
         EXTENT MANAGEMENT LOCAL;
		 
CREATE USER nb IDENTIFIED BY nb
         ACCOUNT UNLOCK
         DEFAULT TABLESPACE NB_DATA
         TEMPORARY TABLESPACE NB_TEMP;
		 
GRANT CONNECT,RESOURCE TO nb;  --表示把 connect,resource 权限授予 nb 用户
GRANT DBA TO nb;  --表示把 dba 权限授予给 nb 用户

-- 用户会话编码
select userenv('language') from dual;
```
### tnsnames.ora
tnsnames.ora 为 Oracle客户端连接数据库所需配置文件
```
连接描述符名 =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = 服务器地址)(PORT = 服务器端口号))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = 数据库服务名)
    )
  )
```
## 20230331
——感恩公司

### 离职
近两日，听闻公司裁了不少了员工，基本是入职1、2年的，当然还可以选择去北京那边的项目。要么去北京，要么拿赔偿。我就在想我为啥。。？我也是入职才不到2年，平时表现也很一般，目前也没什么需求分给我，真是感激公司的“不杀”之恩。想想这两年，在公司成长了不少，学习到了不少专业素养，特别是我的总监上司，虽不是科班出身，但所涉及的知识面相当广泛且专业，并且在平时工作中看得出都是亲自实践过的，思维缜密做事严谨，平时又很放松待人很好，这良好的专业素养及亲和力，是其他技术总监所不具备的，从他身上学到不少。。公司领导真都是很好的人，挺照顾我的，小伙伴们也很有趣，马上要离开公司的话，真是有太多不舍了，只希望公司能挺过当前难处，今后肯定会越来越好。作为乙方公司，我们公司显然比其他公司专业多了，不管是管理上，还是技术上。可这几年经济大环境不行，甲方领导开始搞事，把整个乙方生态搞的稀烂，别的公司早就裁员，我们公司硬是在发完年终奖后才开始动刀，领导层也是尽了最大努力了。要离开这个可爱的家庭真是挺不舍的。。我姐说笑，要我在定了 Offer 之后让公司把我裁了，我真是笑不出来。写到这里，心里不是滋味，眼睛都要湿润了。

## 20230324
——不打无准备的仗

### 面试
近来面试有 2、3 场，不管是电话还是现场面试，都表现得一踏糊涂，现在看来我都不知道自己从何而来的勇气，投的这些高级岗位简历。总体表现上来看：

1. 完全没什么准备（自我介绍、项目介绍） 
2. 技术基础较薄弱（人家基本都会问原理，技术架构） 
3. 简历写得也很差（介绍不充分，不能自洽）

经过市场的洗礼，我这 8 年的工作经验，水份真是很大，在目前的行情上，想要找到一份满意的工作确实是比较困难了。自己回想了想，前些年确实是浪费了不少时光，只有在最近 2 年才专注在技术上，目前这结果是情理之中，接下来不想再面了，想着仔细梳理一下技术栈。不管是工作还有没有，已做好了最坏心理打算，干好剩余的工作，抓紧时间学习，保持乐观，自己好好活着！

凭借自己对技术还有兴趣，对搞好技术有信心，我相信目前这状况只是暂时的！

### 改造措施 ###
_**在人文上**_

1. 按时休息好，尽可能不要浪费时间，明确时间的价值，做好时间规划。
2. 安排时间适度锻炼。
3. 向优秀的人看齐，保持谦虚谨慎。
4. 整理自己的仪容外貌，保持好的心态，积极乐观与人交流，积极参加各类社交活动。
5. 做事积极主动。

_**在技术上**_

方法论：
明确目标、做好规划、立即行动

重点：
1. 行动
2. 以程序员思维思考问题。遇到问题时，能不能用程序解决问题？技术框架原理是什么？可不可以用其他程序处理？

### 碎言碎语
接下来，打算长期写日志，将学习、工作、面试记录到这里，作为总结的地方。

打算上传本文到 Github ，发现 push 时报权限相关错误：

```shell
git -c core.quotepath=false -c log.showSignature=false push --progress --porcelain origin refs/heads/main:main
remote: Permission to zengjiandong-cn/zengjiandong-cn.github.io.git denied to 39haohezi.
fatal: unable to access 'https://github.com/zengjiandong-cn/zengjiandong-cn.github.io.git/': The requested URL returned error: 403
```

原因是我本地的公钥是绑定到了另一个 Github 上，一通搜索搞定：[四步实现在一台电脑上使用多个github账号](https://www.shuzhiduo.com/A/Ae5RR6Gm5Q/)
