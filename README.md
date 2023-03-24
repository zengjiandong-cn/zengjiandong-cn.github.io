# zengjiandong.cn

[TOC]

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
