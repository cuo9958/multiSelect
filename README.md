# multiSelect
快速多选，优雅的搜索

![例子](http://img.blog.csdn.net/20170103160657388?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3VvOTk1OA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

简单的使用方法：

>var options = {
            left: 0, //下拉框的左侧偏移
            top: 2,//下拉框的顶部偏移
            wid: 200,//下拉框的宽度，输入框的最小宽度跟这个一样
            hei: 38,//下拉框的高度
            name: "name",//搜索插件返回的数据中的key
            code: "code",//搜索插件返回的数据中的value
            max: 9,//最多选择几个
            //搜索的时候触发
            //t:搜索的字符串
            //服务器返回结果之后的回调
            onInput: function(t,fn) {
              var data = [{
                name: "test" + Math.random(),
                code: "123"
              }, {
                name: "test2",
                code: "123"
              }];
              fn(data);
            },
        }
        
$("#demo").multiSelect({
    onInput: function(t, fn) {
        ajax.searchABC(t, function(res) {
            if (res.status.code == 0) {
                fn(res.data);
            } 
        });
    }
>});

