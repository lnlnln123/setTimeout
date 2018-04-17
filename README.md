# setTimeout
作用域，闭包，异步
for(var i = 0;i < 3;i++){
			setTimeout(function(){
				console.log(i);//3个3
			},0)
		}
    输出3个3是因为setTimeout是异步进程，i的每次执行都执行的是setTimeout函数，并没有执行到setTImeout里面的闭包函数（function），当for循环完成后，
    i的值已经是3，所以执行三次setTimeout函数，输出3个3.
    
    for(var i = 0;i < 3; i++){
          (function(i){
            setTimeout(function(){
              console.log(i);//0,1,2
            },0)
          })(i)
    }
    
    讲函数改成上述方式就不会出现这种情况了；
    或者将var声明改成let声明，
