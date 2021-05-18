<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="./lib/vue.js"></script>
</head>
<body>
    <div id="app">
        <my-component>
            <template v-slot:header>
                <div style="background-color: #ccc;height: 50px">
                    这里是导航栏:
                </div>
            </template>
            <template v-slot:content>
                <div style="background-color: #ddd;height: 50px">
                    这里是图书信息
                </div>
            </template>
            <template v-slot:footer>
                <div style="background-color: #eee;height: 50px">
                    这里是信息底部
                </div>
            </template>
        </my-component>
    </div>
    <script>
        Vue.component('my-component',{
            render(createElement){
                return createElement('div',[
                    createElement('header',this.$slots.header),
                    createElement('content',this.$slots.content),
                    createElement('footer',this.$slots.footer)
                ])
            }
        })
        var vm=new Vue({el:'#app'})
    </script>
</body>
</html>
