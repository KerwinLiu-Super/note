## token

### 传统基于服务器的验证方式

- 传统的验证方式是基于服务器的，就是把登陆信息存在服务端，每次登陆需要去辨别存储的登陆信息，一般都是通过session来实现，我们比较老的项目都是通过存储session来实现登陆验证的。

- 这样会有一些问题，比如每次认证用户发起请求时，服务器都需要创建一个用记录来存储信息，当越来越多的用户发起请求时，内存的开销也会不断的增加。
### 基于token的验证原理
- 基于token的身份验证是无状态的，我们不用将信息存储在服务器或者session中。
- token通过请求头传输，而不是把认证信息存储在服务器或者session中，就意味着可以从任意一种可以发送HTTP请求的终端向服务器发送请求。
- 基本流程如下
1. 登陆时，客户端发送用户名密码
2. 服务端验证用户名密码是否正确，校验通过就会生成一个有时效的token串，发送给客户端。这个token是可以配置的基本有密钥、uid、过期时间等、HS256算法组成。
3. 客户端储存token,一般都会存储在localStorage或者cookie里面
4. 客户端每次请求时都带有token，可以将其放在请求头里，每次请求都携带token
5. 服务端验证token，所有需要校验身份的接口都会被校验token，若token解析后的数据包含用户身份信息，则身份验证通过，返回数据。
### node+ jwt(jsonwebtoken) 搭建token身份验证.

<https://blog.csdn.net/qq_37261367/article/details/81387107>


  ​