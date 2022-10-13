# pythonProject01
yuan01test
这是猿人学web端的第一题，主要是有一个参数m进行了md5加密，可以直接通过浏览器进行调试，这里有个无限debugger和防止格式化的反调试。过掉后可以通过观察栈堆或者xhr断点寻找加密位置，这里的request栈
有明显的混淆代码可以得到大概加密位置，然后通过以下代码hook到生成加密值的位置。
Object.defineProperty(window, 'f', {
   set: function(val) {
            console.log('f的值:', val);
           	debugger
            return val;
        }
    }
)
