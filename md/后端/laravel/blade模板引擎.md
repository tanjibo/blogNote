 **打印变量或者默认值，这个语法会自动转义变量内容中的html标记，使得html标签原样输出**  
`Welcome, {{ $name or 'California' }}`  

**打印变量原始内容，不进行转义的用法**  

`{!! 'My list <script>alert("spam spam spam!")</script>' !!}`  


普通循环
```
@foreach ($lists as $list)
<li>{{ $list }}</li>
@endforeach
```
处理变量为空的情况
```
@forelse ($lists as $list)
<li>{{ $list }}</li>
@empty
<li>You don't have any lists saved.</li>
@endforelse
```
if判断
```
@if (count($lists) > 1)
@elseif ()
@else
@endif
```
**在模板中使用以下语法创建内容的占位符**  
`@yield('content')`  
**在视图中使用以下语法使用模板**  
`@extends('layouts.master')`
**使用以下语法填充占位符内容**  
```
@section('content')
content
@endsection
```
**使用以下语法引用子php文件**
```
@include('partial')
@include('partials.row', ['link' => $link]),传递参数给子文件
```
**如何在子视图中决定是否用一些公用内容**
```
@section('advertisement')
parent content
@show
```
以上语法定义的advertisement section并不会直接在子视图中展示,@show相当于@endsection @yield('advertisement')
@section('advertisement')
@parent
child content
@endsection
只有在这里使用了@parent，模板中在advertisement中定义的内容才会显示在子视图中
10. 在模板中引用css,js等的语法
```
{!! HTML::style('css/app.min.css') !!}
{!! HTML::script('javascript/jquery-1.10.1.min.js') !!}
{!! HTML::script('javascript/bootstrap.min.js') !!}
{!! HTML::image('images/logo.png', 'TODOParrot logo') !!}
```
这里需要注意的是，如果写标准的html标签，路径中需要在前面加一个'/'符号
```
<script src="/javascript/jquery-1.10.1.min.js"></script>
```
要使用以上语法需要安装HTML包
11. 安装HTML包
```
composer require illuminate/html
```
在config/app.php中配置provider和alias
```
Illuminate\Html\HtmlServiceProvider::class provider配置
'Form' => Illuminate\Html\FormFacade::class, Facade配置
```
