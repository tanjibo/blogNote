## <center style="color:red;font-size:14px"> nodejs </center>

***
> 1.nodejs



#### 2.获取地址栏参数

 ```
  var url=require('url');
  var result=url.parse(req.url,true).query;
  //{name:tanjibo,age:12}
```

#### 3.堵塞和非堵塞
