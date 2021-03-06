#URI  URL URN

先举一个例子，让大家对这三个名词又一个基本的概念：

1⃣️ ftp://ftp.is.co.za/rfc/rfc1808.txt

2⃣️ http://www.cnblogs.com/nods/p/8985322.html#position

上面列举了十分常见的两个网络地址，这两个地址都是 URI。

其中的 ftp://ftp.is.co.za/rfc/rfc1808.txt 和 http://www.cnblogs.com/nods/p/8985322.html 都是 URL。

其中的 ftp.is.co.za/rfc/rfc1808.txt 和 www.cnblogs.com/nods/p/8985322.html#position 是URN。

对于 2⃣️ 来说：

http:// 是协议 ( 文章最下方给出了常用的几种模式或协议 )。

www.cnblogs.com/nods/p/8985322.html 是网络资源的具体位置。

\#position 则是资源。

那么简单的理解就是 URL 告诉你资源文件在网络上的具体位置，URN 告诉你资源在文件的什么地方。

URL 和 URN 都是 URI 的子集，以上的解释是十分简单通俗的解释。上面两个网络地址，都叫做 URI， 但URI 但表现形式并不单单只有上述两种，还有很多其他但形式。

URI 英文全称为 Uniform Resource Identifier（统一资源标识符），它是一个标准，而非定义具体但表现方式。

URL Uniform Resource Locator（统一资源定位符），它实际上是一个资源标识符，但更具体的，它定位了资源的位置。

URN Uniform Resource Name（统一资源命名），作为特定内容的唯一名称使用的，与当前资源的所在地无关。使用URN，就可以将资源四处迁移，而不用担心迁移后无法访问。P2P下载中使用的磁力链接是URN的一种实现，它可以持久化的标识一个BT资源，资源分布式的存储在P2P网络中，无需中心服务器用户即可找到并下载它。



首先给大家举个例子，有一家公司的总经理，某天，给了我一张名片，上面写了他的头衔，北京XXX公司总经理 张三，还有他的办公室地址，北京市海淀区长安街35号北京XXX公司总经理办公室，那么，我以后给我的朋友吹牛，我认识北京XXX公司的总经理张三，我的朋友都知道北京XXX公司的总经理是一个叫张三的人，那么，这个头衔就和张三对应起来了，只要一说到这个头衔，大家都知道说的是张三，反应到网络世界，这个头衔就叫做URI，只要你给我一个URI，我就知道它代表了什么，比如，[http://www.sina.com.cn](http://www.sina.com.cn/)代表了新浪网，admin@qq.com代表了某一个人的qq邮箱，你的qq号也是一个URI(腾讯服务器内可以识别就是你的QQ账户)，URI就是网络资源的头衔，通过URI标记可以把网络世界里面的每一个事物都加以标记并区分开来。

  好的，现在出现了一个问题，你现在知道北京XXX公司总经理是张三，“北京XXX公司总经理”就是张三这个人的URI，可是，我让你亲自去和张三见一面，你做得到吗？你肯定做不到，因为你不知道他的地址，虽然你有他的URI头衔，但是除此以外，你对他具体的情况一无所知，于是你要定位到他，你就必须得到他的办公室地址，通过“北京市海淀区长安街35号北京XXX公司总经理办公室”这个地址，你就找到了张三。反应到网络世界，网络世界里面的每一个资源不光有自己的头衔，还要能够被人访问，被人找到，所以，网络地址是必须的，否则，这个网络资源的存在没有任何意义，这个地址就叫做URL。

  通过上面的描述，可以发现，URI强调的是给资源标记命名，URL强调的是给资源定位，但是你会发现，URL显然比URI包含信息更多，我通过URL也可以知道张三是总经理，并且我还知道了他的地址，所以大多数情况下大家觉得给一个网络资源分别命名和给出地址太麻烦，干脆就用地址既当地址用，又当标记名用，所以，URL也充当了WWW万维网里面URI的角色，但是他比URI多了一层意义，我不光知道你叫什么，我还知道你在哪里。我们在浏览器输入的都是URL，因为我们输入的目的是为了找到某一个资源，当然你输入的是URI也是没错的，因为URL也是URI。

  总结：URI标记了一个网络资源，仅此而已； URL标记了一个WWW互联网资源（用地址标记），并给出了他的访问地址。(URI是Uniform Resource Identifier,表示是一个资源； URL是Uniform Resource Locator，表示是一个地址，光看英文缩写确实难懂)



# RESTful

RESTful API的原则之一是无状态



## HTTP状态码

##CRUD

get 和 post的区别

get可以传送json吗





# 跨域

JSONP

CORS



# jar war

jar 和 war在工作使用中的异同