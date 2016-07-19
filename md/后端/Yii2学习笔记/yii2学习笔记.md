### **yii2 学习笔记**
 ### <center style="color:purple">控制器</center>

>1.获得参数
```
 $request=\Yii::$app->request; //获取请求组件

 $request->get('id',20) //默认值为20

 $request->post('id',20) //post,默认值为20

 /*
 *判断是否是get和post请求
 */
 if($request->isGet && $request->isPost){

}

//判断用户ip
$request->userIp
```
***
>2.响应
```
$res=\YII::$app->response;
$res->statusCode='404';
$res->headers->add('pragma','no-cache');
$res->headers->set('pragma','max-age＝5'); //缓冲5秒
$res->headers->remove('pragma'); //移除
//跳转
$res->headers->add('location','http://www.baidu.com');
$this->redirect('http://www.baidu.com',302);
//文件下载
$res->headers->add('content-disposition','attachment;filename="a.jpg"');
/文件下载专用函数
$res->sendFile('./b.jpg'); //把根目录文件用于下载
```

---
>3.session处理
```
$session=\YII::$app->session;
//判断session是否开启
if($session->isActive){

}else｛
$session->open(); //开启
｝
//查看php.ini 配置项session.save_path 知道session 存储路径
$session->set('user','tanjibo'); //设置session
$session->get('user'); /获取
$session->remove('user');  //删除
```
---
>4.cookie
```
use yii\web\Cookie;
$cookies=\YII::$app->response->cookies;
/添加
$cookies->add(new Cookie(array('name'=>'user','value'=>'zhangsan')));
／／删除
$cookies->remove('user');


 $cookies=\YII::$app->request->cookies;
 echo $cookies->getValue('user',20); //第二个参数是默认参数


```
 ### <center style="color:purple">视图</center>

 >1.载入视图之函数
 ```
 $this->renderPartical('index',['index'=>123]);
 $this->render('index');

//过滤数据
<?php
yii\helpers\Html;
yii\helpers\HtmlPurifier;
?>
<h1><?=Html:encode($arr);?></h1>
//彻底的过滤js代码
<h1><?=HtmlPurifier::process($arr);?></h1>
 ```

 >2.布局文件
 ```
 <html>
 <head>
   <title></title>
 </head>
   <body>
   <?=$content;?>
   //在视图中载入模版
   <?php echo $this->render('about');?>
   </body>
 </html>
 ```
