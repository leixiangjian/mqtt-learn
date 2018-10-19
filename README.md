# mqtt-learn
# 一、MQTT协议解决什么问题？  
首先我们要明确MQTT协议是一个客户端服务端架构的发布/订阅模式的消息传输协议。由于它的设计思想是轻巧、开放、简单、规范，易于实现，这些特点使得它对很多场景来说都是很好的选择，
特别是对于受限的环境如机器与机器的通信（M2M）以及物联网环境（IoT）。目前腾讯云平台、百度云平台、阿里云平台的物联网云服务器都支持此协议，此协议是开源的。  
# 二、此协议的开源项目有哪些？  
1、MQTT服务器    
1）Apache Apollo  
http://activemq.apache.org/apollo/community/developers.html  
2、MQTT客户端   
1）Websockets client  
百度开放云基于浏览器开发的mqtt客户端  
2）MQTT.fx  
目前主流的mqtt客户端，可以快速验证是否可以与iot hub服务交流发布或订阅消息  
3）Paho  
Eclipse基金会提供的开源MQTT客户端=实现，可以很好的支持百度开放云物链接lot hub服务以实现设备互联和物联网应用
# 三、物接入iot hub-概念  
<table>
  <tr>
   <th>概念</th><th>描述</th>
  </tr>
  <tr>
    <td>MQTT</td><td>MQTT是基于二进制消息的发布/订阅(Publish/Subscribe)模式的协议,最早由IBM提出的，如今已经成为OASIS规范，更符合M2M大规模沟通
  </tr>
  <tr>
    <td>endpoint</td>
    <td>iot hub的服务实例，代表一个完整的iot hub服务</td>
  </tr>
  <tr>
    <td>thing</td>
    <td>表示iot hub设备，用户可以在每个endpoint中创建一个或多个thing</td>
  </tr>
  <tr>
    <td>principal</td>
    <td>principal是一个抽象概念，表示设备的（thing）身份，每个thing可以绑定一个principal，每个principal拥有一个policy权限</td>
  </tr>
  <tr>
    <td>policy</td>
    <td>为身份principal设置对应的策略policy，一个principal对应一个policy</td>
  </tr>
  <tr>
    <td>permission</td>
    <td>为每一个policy设置一组权限permission，其中包括主题topic和对该主题的操作权限operation。</td>
  </tr>
  <tr>
    <td>topic</td>
    <td>
    每一个policy都需要指定一个主题项目(topic)，在进行使用iot hub服务之前,
    需要先为我们即将开展的订阅发布信息创建一个主题名称，
    该主题应用于MQTT客户端。topic规则允许字符串可以带一个通配符"#",
    例如"temperature/#"就是匹配前缀是temperature的所有topic;单独的"#"表示匹配所有topic
    </td>
  </tr>
  <tr>
    <td>operation</td>
    <td>
    对topic的操作权限。目前基于MQTT协议，iot hub支持创建发布PUBLISH和订阅SUBSCRIBE两种权限
    </td>
  </tr>
</table>
