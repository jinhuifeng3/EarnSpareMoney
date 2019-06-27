## UI设计
<hr>

### 总述
挣闲钱通过微信小程序平台实现，因此在UI设计主要采用了微信的原生风格，界面布局多使用微信原生组件实现。
<br><br>
根据我们的业务逻辑，前端的UI可以主要分为五个部分：

* 登录/注册
* 找任务
* 发布任务
* 我的任务（进行任务管理）
* 我（修改个人信息、充值闲钱币）

除登录注册以外，其他的四个部分通过小程序的tabbar将业务逻辑隔开
![](images/tabbar.jpg)

### 设计理念和优势
1）整洁简约：整个小程序的风格完全融入了微信的环境，采用原生组件的搭配可以让用户更有亲切感。同时设计整体没有冗余的部分，简单实用，又不乏一种纯粹的美感。<br><br>
2）效率高：没有多余的修饰可以让用户快速找到自己需要的功能；同时，UI的设计很多源于对微信本身的模仿，让已经熟悉微信操作的用户对本软件可以快速上手。<br><br>
3）交互感强：对于用户的操作提供了及时的确认成功信息反馈，如果用户操作不当也会有及时的提示信息，整体上较好地引导用户操作。<br><br>
4）突出重点：整个UI的设计都以实用性为主，用户在每个界面都可以快速抓住重点，完成所需要的业务流程。



### 界面样例


登录/注册相关界面

![](images/UI_p1.jpg)

个人信息/充值相关界面
![](images/UI_p5.jpg)

## 模块划分
<hr>

### 登录/注册
用户刚进入小程序中可以选择登录或者注册，并跳转到对应的界面进行操作。（界面可参考UI设计部分）
<br>
登录通过用户名和密码进入用户。
<br>
如果是新用户，需要填写一下信息完成注册：
* 用户名（20字符内，必填）
* 密码（6位以上，必填）
* 确认密码（必填）
* 昵称（15字符内，必填）
* 个性签名（少于50字）
* 电话（11位手机号，必填）
* 学校（30字符内）

### 参加活动

用户登录成功后进入的第一个页面就是找活动的界面，在这个界面中，可以通过分类找到自己感兴趣的活动，获取相应的信息（发布者、任务详情），确认无误后可以参加相应的活动。
![](images/search.jpg)

### 发布任务

每个用户不但可以参加任务，也有权利发布任务。<br>
任务的类型主要包括三种：
* 问卷（会有单独介绍）
* 活动
* 跑腿（可以是拿外卖之类的）

如果是发布问卷的话，发布时候会跳转到相应的编辑题目页面，每个任务包括以下属性：
* 标题
* 报酬
* 参加人数
* 类别
* 详情
* 描述图片

![](images/releasettask.jpg)
### 管理任务
挣现钱的业务逻辑是：每个人都可以发布任务（问卷、参加活动、跑腿），每个人也可以参加任务。<br>
因此，就需要有特定的模块对与用户本身相关的任务进行处理。我的活动部分分为我参加的和我发布的，同时用户对于这两种情况都可以查看当前进行中的或者历史记录（已结束）。参与者如果需要取消参加、发布者如果需要取消发布和确认活动完成状态也是在这部分完成任务。
![](images/mytasks.jpg)
![](images/cancel.jpg)
### 个人信息修改
用户可以在"我"的部分修改个人信息，可以修改的内容包括：
* 昵称（15字以内）
* 个性签名（50字内）
* 学校（30个字符内）
* 电话（11位有效数字）
* 头像

具体的修改流程和效果可以参照UI设计的样例展示，如果用户的修改内容不符合要求将会出现对应的提示，如果修改成功将会出现“已完成”的成功提示。

### 闲钱币系统
闲钱币是在挣闲钱小程序中的一种虚拟代币，用户在发布有偿的活动时就是通过闲钱币进行奖励，参加者在参与成功时将会以闲钱币的方式获得奖励。<br>
用户发布任务时将会扣除对应设置的闲钱币，确认任务结束状态时，对应的闲钱币将会发到对应参与的用户账户里。每个人可以充值闲钱币，也可以提现，由于小程序本身对于微信支付API的限制，这里只能模拟一个充值提现的过程。具体UI和流程可以参照UI设计部分的图片展示。

### 信用评级
信用评级用于让用户判别合作伙伴是否可靠。在个人信息部分给出了相应的说明让用户了解信用机制。
![](images/introcredit.jpg)

每个人可以在任务详情中通过点击发布者/参加者的头像获得该用户的信息，查看信用度。

![](images/checkinfo1.jpg)
![](images/checkinfo2.jpg)

### 问卷系统
由于项目本身要求，这里单独特别实现了问卷系统。需要发布问卷的人在发布任务的时候要设置相关题目，参加任务的人在“我的活动->我参加的”的部分完成填写问卷。
![](images/ques1.jpg)
![](images/ques2.jpg)
![](images/cancel.jpg)