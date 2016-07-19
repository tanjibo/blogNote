### git
##### 1.全局配置
>git config --global user.name 'github username'  
>git config --global user.email 'github email'  

##### 2.创建版本库  
 1. mkdir gitLearn   
 2. cd gitLearn  
 3. git init
 4. touch index.php
 5. git add -A 或者 git add . 或者 git add 'index.php'
 6. git commit -t 'first commit'
 7. 在github 上面创建一个版本库，但是不要初始化
    - ![tupian](https://raw.githubusercontent.com/tanjibo/gitHubImg/master/QQ20160626-0%402x.png)  
 8. git remote add origin git@github.com:tanjibo/gitLearn.git
 9. git push -u origin master  

  - 注：git 分为三个区：工作区，暂存区，历史区，`git add` 命令就是把文件从工作去提交到暂存区, `git commit` 就是从暂存区到历史区  

---
 #####  3. 使用fork功能(以tantanjibo账号)
  1. 查找到tanjibo用户下的项目`learn`  
  2. 点击fork，把项目fork到自己的项目下面  
   - ![](https://raw.githubusercontent.com/tanjibo/gitHubImg/master/QQ20160626-1%402x.png)
  3. 克隆自己的项目
  - `git clone https://github.com/tantanjibo/learn.git`
  4. 修改自己的东西，添加自己的东西
  5. git add .
  6. git commit -m 'commit'
  7. git push origin master //推送到本人的账号项目下
  8. 在github 上发一个push master ，想把自己的内容合并到原来的项目下（tanjibo的learn下）
   - ![](https://github.com/tanjibo/gitHubImg/blob/master/QQ20160626-2@2x.png?raw=true)  

   -  ![](https://github.com/tanjibo/gitHubImg/blob/master/QQ20160626-3@2x.png?raw=true)
  9. 由tanjibo 来决定是否合并你的代码
