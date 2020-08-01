## Node.js + Vue.js 开发王者荣耀手机端官网和管理后台

### 一、 初始化

1. 工具安装和环境搭建(nodejs,npm,mongodb)  
下载mongodb   
githup创建仓库     
git clone // 到本地   
git status 查看状态     
git add . 添加       
git commit -m "" 提交     
git push 推送 

2. 初始化项目  
安装 npm i -g @vue/cli  
后端 vue create admin         
前端  vue create  web       
开发 server  
初始化 npm init -y   

## 二、 管理后台

1. Element UI搭建后台管理基础界面  
添加element ：npm install Element UI    
[Element UI官网](https://element.eleme.cn/)  
创建路由 npm install vue-router   main.js里添加路由  
```
new Vue({
    router,
    render: h => h(App),
}).$mount('#app') 
```  
了解vue相关知识[vue.js官网](https://vuejs.org/)  
在views里加Main.vue ,构成后端页面  

2. 分类  
接口请求 http.js (npm i axios)     
error  'res' is assigned a value but never used  no-unused-vars (加注释// eslint-disable-line no-unused-vars)  
服务端 npm i express@next mongoose cors  
请求地址 post,get  
删除 delete  
mongodb数据库插件  
$router.push("") 跳转页面  
populate ("")关联取出  

3. **通用 CRUD 接口**

4. 装备管理

5. 图片上传 (multer)    
npm i multer 处理上传事件  
```
<el-upload 
class="avatar-uploader"  
:action="$http.defaults.baseURL+'/upload'"   :show-file-list="false"  :on-success="afterUpload">
</el-upload>
```
__dirname  绝对地址  

6. 英雄管理  
关联,多选,el-select, multiple  
:md 控制一行个数 12表示一行  
技能编辑  

7.  文章管理  
富文本编辑器 (quill)用vue2-editor 

8.  首页广告管理

9.  管理员账号管理 (bcrypt 加密)
```
password: {
        type: String,
        select: false,
        set(val) {
            return require('bcrypt').hashSync(val, 10) //散列加密
        }
    }
```

10.  登录(jwt,jsonwebtoken)  
localStorage.token 登录界面查看数或sessionStorage.token  
axios.interceptors.response.use（）  信息拦截  
compareSync(password, user.password) 判断明文和密文  
设置密钥 'secret'     
```
app.set('secret', 'i2u34y12oi3u4y8')(自己随便设置)
```

11. 服务端登录校验  
http-assert  判断存在，确保正确      
npm i http-assert 

12. 客户端路由限制 (beforeEach, meta)

13. 上传文件的登录校验 (el-upload, headers)
```Vue.mixin({
    computed: {
        uploadUrl() {
            return this.$http.defaults.baseURL + '/upload'
        }
    },
    methods: {
        getAuthHeaders() {
            return {
                Authorization: `Bearer ${localStorage.token || ''}`
            }
        }
    }
})
```

### 三、移动端网站

1. "工具样式"概念和 SASS (SCSS)  
安装sass

2. 样式重置

3. 网站色彩和字体定义 (colors, text)
 ```
$colors()
@each $key in $colors { }
```

3. 通用flex布局样式定义 (flex)

4. 常用边距定义 (margin, padding)
   
5. 主页框架和顶部菜单

6. 首页顶部轮播图片 (vue swiper)    
安装vue-awesome-swiper 

1. 使用精灵图片 (sprite)  
[精灵图标网站](spritecow.com)

8.  使用字体图标 (iconfont)  
[字体图标网站](https://www.iconfont.cn/)

9.  卡片和列表卡片组件 (card，list-card, nav, swiper)

10.  首页新闻资讯  
安装require-all  
```
require('require-all')(__dirname + '/../models')
```

11.   首页英雄列表

12.   新闻详情页

13.   英雄详情页

### 四、发布和部署 (阿里云)

1. 生产环境编译  
npm run build 打包  
```
module.exports = {
    outputDir: __dirname + '/../server/web',
    // publicPath: process.env.NODE_ENV === 'production'
    //   ? '/'
    //   : '/'
}
```

2. Nginx 安装和配置  
安装remote-ssh插件  
[ngnx免费配置网站]( https://www.digitalocean.com/community/tools/nginx#?)  

3. MongoDB数据库的安装和配置

4. git 安装、配置ssh-key

5. Node.js 安装、配置淘宝镜像

6. 拉取代码，安装pm2并启动项目

7. 配置 Nginx 的反向代理

8.  迁移本地数据到服务器 (mongodump)  
用Robo 3T  

### 五、网站安全与存放文件

1. 使用免费SSL证书启用HTTPS安全连接  
用let's encrypt  
[let's encrypt网站](https://letsencrypt.org/) 

2. 使用阿里云OSS云存储存放上传文件  
在server安装multer-aliyun-oss  
