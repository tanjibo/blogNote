# 活动记录

> - 查询数据

```
//sql语句
User::findBySql('select * from user where(id=1')－>asArray()->all();  

//占位符方式 ,防止sql 攻击  `id=1 or 1=1`
$sql="select * from test where id=:id";
User::findBySql($sql,array(':id'=>'1 or 1=1'))->all();  

User::find()->where(['id'=>1])->all();

['>','id',0] //id 大于0

['between','id',1,2] // 大于等于1且等于小于2

['like','username','tanjibo'] // username like %tanjibo%

//查询结果转换成数组
asArray()

//批量查询,batch() 英文意思：一批
$tmp=array();
foreach(User::find()->batch(2) as $test){
  $tmp[]=$test;
}
```  
> - 删除    

```
User::deleteAll('id>:id',array(':id'=>0));
```
> - 插入和修改

```
$user=new User;
$user->validate();  //activeRecord 定义了rules 方法
if(!$user->hasErrors()){
  $user->save();
}
//修改数据
$test=User::find()->where(['id'=>4])->one();
$test->username='tanjibo';
$test->save();

```
> - 关联  

```
//hasMany
hasMany(order::className(),['user_id'=>'user_id'])
//hasOne
hasOne(User::className(),['user_id']=>'user_id'])
```
