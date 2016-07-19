### MODEL

---
- 插入数据  
 ```
 /**
  * 第一种
  */
 $category = new Category;
 $categroy->create_time=time();
 $category->fill($data)->save();

 /**
  * 第二种方式
  */
 Category::create($data);
 ```

 - 更新数据  

 ```
 Category::where('c_id',$id)->update($input);
 ```


 - 删除数据
 ```
 Category::where('c_id',$id)->delete();
 ```
