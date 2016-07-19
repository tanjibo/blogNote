s#  jquery.validation
---
- **github网址:https://github.com/jzaefferer/jquery-validation**

- **基本用法**
  - `required`     必填
  - `remote`       远程校验
  - `minlength`    最小长度
  - `maxlength`    最大长度
  - `rangelength`  是minlength 和 maxlength 的一个集合
  - `min`          数字的范围[最小值]
  - `max`          数字的范围[最大值]
  - `range`        是min 和 max 的一个集合
  - `email`        email
  - `url`          地址
  - `date`         日期
  - `number`       数字
  - `digits`       整数
  - `equalTo`      与另一个元素相等

>实例：
```
$( "#signupForm1" ).validate( {
    debug:true
    rules: {
        firstname1: "required",
        lastname1: "required",
        username1: {
            required: true,
            minlength: 2,
            equalTo: "#password1",
            maxlength:20,
            email:true,
            rangelength:[2,20]
            remote:{
                url:'data.json',
                data:{
                    id:1
                }
            }
        },
        num:{
            required:true,
            max:10,
            min:2,
            range:[2,10]
        }
    },
    messages: {
        firstname1: "Please enter your firstname",
        lastname1: "Please enter your lastname",
        username1: {
            required: "Please enter a username",
            minlength: "Your username must consist of at least 2 characters"
        },
        password1: {
            required: "Please provide a password",
            minlength: "Your password must be at least 5 characters long"
        },
        confirm_password1: {
            required: "Please provide a password",
            minlength: "Your password must be at least 5 characters long",
            equalTo: "Please enter the same password as above"
        },
        email1: "Please enter a valid email address",
        agree1: "Please accept our policy"
    },
    errorElement: "em",
    errorPlacement: function ( error, element ) {
        // Add the `help-block` class to the error element
        error.addClass( "help-block" );

        // Add `has-feedback` class to the parent div.form-group
        // in order to add icons to inputs
        element.parents( ".col-sm-5" ).addClass( "has-feedback" );

        if ( element.prop( "type" ) === "checkbox" ) {
            error.insertAfter( element.parent( "label" ) );
        } else {
            error.insertAfter( element );
        }

        // Add the span element, if doesn't exists, and apply the icon classes to it.
        if ( !element.next( "span" )[ 0 ] ) {
            $( "<span class='glyphicon glyphicon-remove form-control-feedback'></span>" ).insertAfter( element );
        }
    },
    success: function ( label, element ) {
        // Add the span element, if doesn't exists, and apply the icon classes to it.
        if ( !$( element ).next( "span" )[ 0 ] ) {
            $( "<span class='glyphicon glyphicon-ok form-control-feedback'></span>" ).insertAfter( $( element ) );
        }
    },
    highlight: function ( element, errorClass, validClass ) {
        $( element ).parents( ".col-sm-5" ).addClass( "has-error" ).removeClass( "has-success" );
        $( element ).next( "span" ).addClass( "glyphicon-remove" ).removeClass( "glyphicon-ok" );
    },
    unhighlight: function ( element, errorClass, validClass ) {
        $( element ).parents( ".col-sm-5" ).addClass( "has-success" ).removeClass( "has-error" );
        $( element ).next( "span" ).addClass( "glyphicon-ok" ).removeClass( "glyphicon-remove" );
    }
} );
} );
```

## 高级api

- **rules()方法(只针对表单里的元素，而不是某个整个表单)**

   1.可以使用rules("add",{})的方法来为元素添加规则，如

    `$("#username").rules("add",{minlength:2,maxlength:10})`  

   2.可以使用rules("remove",{})的方法来为元素去掉规则，如

    `$("#username").rules("remove","email")`

- **validator**
 - ![tupian](http://img.mukewang.com/5756c88100014aad12800720.jpg)
 - `validator.form()` //整个表单是否有效 true/false
 - validator.element("username") //验证元素是否有效
 - validator.resetFrom() //表单回复到验证前状态
 - validator.showErrors({}) //针对某个元素显示特定的错误信息
 - validator.numberOfInvalids() 返回无效元素数量


 - ![tupian](http://img.mukewang.com/575bd2e000018d0012800720.jpg)  


 - ![tupian](http://img.mukewang.com/574bf02500010dae12800720.jpg)



  - ![tupian](http://img.mukewang.com/573044c1000171fe12800720.jpg)  

  - ![tupian](http://img.mukewang.com/5756cc83000122ec12800720.jpg)  
