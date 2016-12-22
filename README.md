# signaling-proto



*version 1*

*2016-12-22*

*notedit*





## message struct



系统中流转的信息格式为固定的,并且使用json编解码

信息基本格式如下

```
{
	'from':str,
	'type':str,
	'target':str,
	'data':object
}
```





## system message



#### peers



当一个连接建立的时候, 服务端主动向连接发送此消息,这时user_id为固定值system.

```
{
	'from':system
	'type:'peers'
	'target':str,
	'data':{'users':[]}
}
```





#### peer_connected

当一个连接建立的时候, 服务端主动向房间的其他连接发送此消息, 具体的格式为:

```

{
	'from':str
	'type:'peer_connected'
	'target':str,
	'data':{}
}
```







#### peer_removed

当一个连接断开的时候, 服务端主动向房间的其他连接发送此消息, 具体的格式为:

```

{
	'from':str
	'type:'peer_removed'
	'target':str,
	'data':{}
}
```







## signaling  message



#### offer



当一个用户向另一个用户发起offer时, 消息格式为



```
{
	'from':str
	'type:'offer'
	'target':str,
	'data':{
      	sdp info 
	}
}
```





#### answer

当一个用户回复一个用户的offer,并发送answer时



```
{
	'from':str
	'type:'answer'
	'target':str,
	'data':{
      	sdp info 
	}
}
```







#### ice

交换ice信息

```
{
	'from':str
	'type:'ice'
	'target':str,
	'data':{
      	ice data
	}
}
```







#### bye

但一个用户要想主动断开与另一个用户的连接时

```
{
	'from':str
	'type:'bye'
	'target':str,
	'data':{
      	
	}
}
```





