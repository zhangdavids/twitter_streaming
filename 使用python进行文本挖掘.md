# 使用python进行文本挖掘

标签（空格分隔）： python twitter

---

如何从浩瀚的twitter中获取一些我们需要的信息呢？
从twitter的文档我们知道twitter提供了Twitter Streaming API ,我们可以成为一名twitter开发者获取里面的数据并且提取出来进行分析。
如下：

第一步 从twitter获取相关数据
    1 获取twitter api keys
    
    注册一个twitter账户，然后到https://app.twitter.com/ 创建一个新的app，得到四个参数 api keys，api secret，access token，access token secret。
    
    2 连接到twitter streaming api并下载数据
    
    这里我们有两段python的代码 config.py twitter_data.py
    config.py 中是我们的twitter开发者参数，这个我们单独列出来。
    twitter_data.py 是我们从python获取数据的脚本，这里我们搜索三个关键词，python javascript 和ruby。
    注意一下，中国大陆的环境无法直接在命令行中连接twitter，我们需要先配置好proxychains4。
    接着我们先运行 proxychains4 python twitter_data.py
    可以看到程序在不断从twitter中获取数据，这里把数据下载下来
    proxychains4 python twitter_data.py > twitter_data.txt
    
    通过ctrl＋c可以终止程序。
    
    这个程序我在这运行了1到2个小时，从中获取了1094条推文。
    
    
第二步 分析理解数据并图形化

我们第一步获取了一个txt的文件，打开发现很难从中直接看出啥端倪。
这里决定使用ipython notebook来进行数据的分析

文件 textmining.ipynb

   1 导入json pandas matplotlib
   
   2 读取数据
   
   3 查看下数据条数 是1094条（样本数据不太够！！）
   
   4 数据结构化到pandas DataFrame
   
   5 这里先分析推文里的三项 推文text,语言lang,国家country
   
   6 把推特中top5 languages的图形化
   
   7 推特中top5 country 图形化
   
第三步 挖掘twitter文本

  1 通过正则把数据分块
     python 277 javascript 275 ruby 477
     
  2 作出ranking的对比图
  
  3 定位相关推文
   通过关键词programming和tutorial来准确定位推文，到这只剩下了30来条推文，python 12 javascript 14 ruby 1，然后把推文的链接也一并打印出来供参考。
   
   结语
   
   参考了很多国外的资料，包括百科 博客等等。当如还有很多todo。
   
   代码 数据都这这  https://github.com/zhangdavids/twitter_streaming
    




