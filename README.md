# Courum
**Courum = course + forum**  
**提供给UCSD学生的课程论坛**  
[See a demo here](https://courum.com)  
[See demo video here](https://drive.google.com/file/d/1c-hDJCm-pV59btyacVQU4DJ9Vg4Q4znE/view?usp=sharing)  
[设计图](https://www.figma.com/file/kp3zYrUAjvElynw2ldiqle/Courum-Wireframes?node-id=0%3A1)  
![Courum_Logo](https://i.loli.net/2020/11/20/AWUP9JgGhwxyKte.png)
![courum_main.png](https://i.loli.net/2021/03/22/bkAKgwcsp5jRMeo.png)
![courum_course.png](https://i.loli.net/2021/03/22/nzUtQwvZdEjymL4.png)
![courum_sign_in.png](https://i.loli.net/2021/03/22/75ZCbetcsNzpqfS.png)

## 目录
- [成员](#项目组成员)
- [技术栈/框架](#技术栈/框架)
- [基本功能](#基本功能)
- [核心技术/难点](#核心技术/难点)
- [不足/反思](#不足/反思)
    - [技术](#技术)
    - [开发流程](#开发流程)
    - [UI设计](#UI设计)
    - [产品设计](#产品设计)
    - [商业发展](#商业发展)
- [优点](#优点)
- [未来发展](#未来发展)
- [联系方式](#联系方式)


## 项目组成员
- Samantha Chin (PM)   
- Dekun Ma (Tech Lead)
- Xinyue Yu (Frontend)
- Kuiduan Zeng (Frontend)
- Irene Hsieh (Frontend)
- Ziang Hong (Backend)
- Jiahao Lou (PD)
- Xiangyu Jia (PD)
- Binyuan Yan (BD)
- Meijiang Shen (HR)

## 技术栈/框架
**前端：**  
- React.js
- Redux
- Material UI  

**后端：**
- Feathers.js
- Express.js
- MongoDB
- AWS S3

**设计：**  
- Figma

## 基本功能
- 找到你在上的课，在所属的板块发帖来实现：
    - 问问题
    - 分享资源
    - 找课友
- 自适应的手机端UI
- 上传文件
- 全局搜索

## 核心技术/难点
- 论坛发帖功能
- 前端所有页面（比较）完美地支持了手机视图
- 后端实现了完整的用户 注册/登录/找回密码 服务
    - 登录：JWT authentication
    - 注册/找回密码：通过向用户邮箱发送邮件，用户点击邮件里的链接即可直达验证邮箱/改密码的portal
- nodejs (Express) 实现向AWS S3上传文件服务
- 高效（搞笑？）的后端数据库架构

## 不足/反思
### 技术
- 前端代码***非常***不规范，并且很多地方逻辑混乱，或有hard-code，非常不利于后期维护
- 前端注释量很少，不利于后期维护
- 前端代码风格不统一，包括缩进格式和React的class/functional component的选择上
- 导致以上问题的原因主要是没有花足够的时间进行代码审核 & tech lead经验不足  
<br/>
- 后端使用的框架非常冷门，后期维护学习成本较高
- 后端 micro services 的命名不规范
- 后端注释量很少，且很多地方的代码逻辑都可以被优化
- 后端从未做过安全性确认，**可能存在安全问题**
- 导致以上问题的原因是后端一直都是一个人 (tech lead) 在写，比较放飞自我

### 开发流程
- tech lead 在开始开发之前没有确认前端/后端人员已经基本掌握了需要的框架，导致正式开发开始之后出现了很多框架相关的问题。建议后续项目组tech lead在开始开发之前务必确保 developers 对框架已经熟悉
- tech lead 在布置每周任务的时候没有用 dashboard 或 文档 等方式记录。导致 developers 经常对自己的任务有感到迷茫；并且后期难以追溯哪个功能是谁负责的

### UI设计
- 不够精细，并且设计风格不够现代，导致后期 developers 都很少再看设计图，而是直接用 Material UI 的现成组件/布局来实现前端

### 产品设计
- 总体而言, 我 (tech lead) 个人认为产品设计非常失败
- > 一个想要发展市场的产品, 要么是可以解决某个核心痛点 (市场上没有同类产品), 要么就是相比于市场上同类产品来说, 有自己非常独特的竞争力  
 -- PM from XPlore UCSD, 易山韜  

    我们 Courum 的核心功能就是让同一节课的学生在我们的线上论坛针对课程内容进行交流  
    这个功能直接对标的产品就是 Piazza, 但是我们除了一些无关紧要的细节 (UI等) 之外, 找不到太多能直接证明我们比 Piazza 更好用的理由 (向别人介绍 Courum 的时候, 很多人在听完之后都会问 Courum 和 Piazza 有什么区别);   
    并且 Piazza 用户基数比我们大得多, 而且用户都非常稳定; 我们找不到可以让用户放弃 Piazza 而转为使用 Courum 的理由  
- 后来我们加了一个找课友的核心功能
- 但很明显, 用户会通过这个功能在找到课友之后前往其他的即时性交流平台 (微信/Discord等), 因为 Courum 不能提供即时消息提醒, 并且如果要问问题的话, 发一条 message 明显会比在 Courum 上发一条 post 更省时省力
- 社区运营 & 可持续性发展问题: 
- 存在大量用户的社区, 都是需要人来运营的; 我对 Courum 的可持续性发展持悲观态度的一大原因就是 Courum 完全无法提供社区支持; 举例来讲, 如果在 Piazza 上发帖, 那TA和教授会在上面解答, 但如果在 Courum 上发帖, 用户没有理由去 expect 自己的问题会得到解答, 因为 Courum 没有TA/教授的进驻, 也没有强烈有效的鼓励用户去回答问题的机制; 就算有优秀的鼓励机制, 在初期 (用户基数非常小) 的情况下, 这种机制在没有其他外力的帮助下也很难发挥作用
- 总结: Courum 不是第一个尝试去解决 "课友论坛" 痛点的产品; 并且 "找课友" 这一功能难以与同类产品竞争

### 商业发展
- 市场调查: 
- 除了 Piazza 之外, 我能想到的现成可用的论坛竞品就还有 campuswire 和 edstem, 需要自己配置的论坛软件还有 Discourse 和 Discuz! 等; 我觉得我们的市场调查和竞品分析做得非常不全面
- 没有想过盈利模式/引流模式

## 优点
- 起码我们还是把整个项目完整做完了, 就算没有实现市场价值, 我们还是可以把这个项目写到简历里
- 组内氛围非常融洽, 组员之间的合作非常顺畅
- 我们一直都鼓励 developers 给产品/UI设计/市场发展等方向提意见, 而且所有 developers 也都这么做了; 有效提升了 developers 在开发任务之外的项目参与度; 也对产品/UI设计/市场方面起到了帮助

## 未来发展
- 如果你想重启这个项目 或 复用这个项目的代码，欢迎联系我。联系方式在下方
- Courum 可能会作为 “UCSD中国学生新生论坛” 重启：从商业性项目转换为工具（公益）型项目。  
    我注意到去年新生入学的时候，有学长学姐自发创建了新生群，在群里给新生答疑。
    经常会遇到的情况是很多问题会有不同的人重复询问，因为微信不支持查看入群之前的消息历史，
    并且有500人的人数上限，不同群之间消息不互通。  
    这些学长学姐可以使用改版后的 Courum，把常见问题/资源发在相应的版块里，这样新生在问问题之前可以去 Courum 里搜一下有没有人问过了相关的问题，
    有效节省了学长学姐们的时间，并且资源丰富之后的 Courum 可以一届一届往后流传
- 上述的改动之前已经开始写了，具体什么时候会发行还待定

## 联系方式
- Tech Lead 马德堃：
- **Email:** William@dekun.me
- **Wechat:** Magnoliae_Flos 

    
