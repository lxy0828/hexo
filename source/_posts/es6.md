---
title: ES6语法（一）
---
*对于ES6中的一些基础语法，包括对数组/对象/函数/字符串的操作，chroem已经支持了这些语法*
``
       
    
        {
            console.log(Number.isFinite(15))
            console.log(Number.isFinite(NaN))
            console.log(Number.isFinite('true'/0))
            console.log('NaN',Number.isNaN(NaN))
        }

        {
            console.log(4.1,Math.trunc(4.1)) //4
            console.log(4.9,Math.trunc(4.9)) //4
        }
        {
            console.log('-5',Math.sign(-5)) //-1
            console.log('0',Math.sign(0)) //0
            console.log('5',Math.sign(5)) //1
            console.log('5',Math.sign('5')) //1
        }

        /*--数组扩展--*/
        {
            let arr = Array.of(3,4,7,9,11)
            console.log(arr)
        }
        {
            let p = document.querySelectorAll('p')
            let pArr = Array.from(p)
            pArr.forEach((item)=>{
                console.log(item.textContent)
            })
        }

        {
            // 填充数组
            console.log([1,'a',undefined].fill(7))
            console.log([1,'a',undefined].fill(7,1,3))//fill内参数，第一个为替换的数值，第二和第三为起止位置
        }
    
        {
            for (let index of ['11','22','32'].keys()) {
                console.log('keys',index)//返回数组下标
            }
            for (let value of ['11','22','32'].values()) {
                console.log('keys',value)//返回数组内的值
            }
            for (let [index,value] of ['11','22','32'].entries()) {
                console.log('keys',index,value)//返回数组值和下标
            }
        }
        {
           console.log([1,2,3,4,5].copyWithin(0,3,4)) //第一个参数起始位置，第二个和第三个是要替换的数值起止位置
        }
        {
            console.log([1,2,3,4].find((item) => {
                return item > 3//只找到符合条件的第一个值
            }))
            console.log([1,2,3,4].findIndex((item) => {
                return item > 3//只找到符合条件的第一个下标
            }))
        }
        {
            console.log([1,2,NaN].includes(1))//类似字符串中的indexOf
        }

        /*----函数扩展-----*/
        {
            function test(x, y = "hello") {
                console.log(x, y)
            }
            test('你好')//如果没有传入y值则默认为‘hello’
        }
        {
            let x = 'test';
            function test2(x, y=x) {
                console.log(x,y)//作用域，在开始已经定义了x值，y=x，y值取函数中的参数值
            }
            test2('world')
        }
        {
            function test3(...arg) {
                for (let v of arg) {
                    console.log(v)//rest参数
                }
            }
            test3(1,2,3,4,'a')
        }
        {
            let a = [1,2,3]
            let b = [4,5,6]
            console.log([...a,...b])//数组合并
        }
        {
            let arrow = v => v*2;
            console.log(arrow(3))
        }
        {
            function tail(x){
                console.log(x)
            }
            function fx(x) {
                return tail(x)//伪调用，提升性能
            }
            fx(123)
        }
        /*----对象扩展-----*/
        {
            let o = 1;//简单表示法
            let k = 2;
            let es5 = {
                o: o,
                k: k
            }
            let es6 = {
                o,
                k
            }
            console.log(es5,es6)
            // 对象内函数
            let es5_methods = {
                hello: function(){
                    console.log("hello")
                }
            }
            let es6_methods = {
                hello(){
                    console.log('hello')
                }
            }
        }
        {
            // 属性表达书
            let a = 'b';
            let es5_obj  = {
                a: 'c'
            }
            let es6_obj = {
                [a]: 'c'//在es6中的key值是可以变的，可以是一个变量
            }
            console.log(es6_obj)
        }
        {
            // 新增APi
            console.log(Object.is('abc','abc'),'abc' === 'abc')

            console.log(Object.assign({a:'a'},{b:'b'}))//拷贝，第一个参数是要拷贝的对象上，第二个参数是要拷贝的值

        }
``