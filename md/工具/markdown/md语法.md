# <center> **语法**
***

####1.样式居中(可以写html)  

`<center> content </center>`
 <center style="color:red">content</center>

 #### 2.代码区块和行代码(``)
 
 `this is test`

 ```
 class IndexController extends Controller{
     public $layout='home';

     /**
      * 首页控制器
      */
    public function actionIndex()
    {
      $data = User::find()->all();
       return $this->render('index');
    }
}
```
