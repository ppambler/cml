### ✍️ Tangxt ⏳ 2021-12-10 🏷️ API

## baseURL

`https://api.imooc-blog.lgdsunday.club/api`

## 用户信息

### 1. 登录（微信用户）

- 请求路径：/sys/login
- 请求方法：post
- 请求参数

| 参数名    | 参数说明                                                         | 备注 |
| --------- | ---------------------------------------------------------------- | ---- |
| signature | 使用 sha1( rawData + sessionkey ) 得到字符串，用于校验用户信息， |      |
| iv        | 加密算法的初始向量                                               |      |
| nickName  | 用户昵称                                                         |      |
| gender    | 性别（0：女 1：男）                                              |      |
| city      | 所在城市                                                         |      |
| province  | 所在省份                                                         |      |
| avatarUrl | 头像路径                                                         |      |

- 响应参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
| token  |          |      |
|        |          |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "token": "Bearer d8c6ed7a-3fd4-46e4-a477-b20d1ce9cda0"
  },
  "message": "执行成功"
}
```

## 热搜

### 1 热搜文章类型

- 请求路径：/hot/tabs
- 请求方法：get
- 请求参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
| 无     |          |      |

- 响应参数

| 参数名 | 参数说明   | 备注 |
| ------ | ---------- | ---- |
| id     | tab ID     |      |
| text   | tab 的名称 |      |

- 响应数据

```json
{
  "data": {
    "list": [
      {
        "id": "0",
        "label": "热榜"
      },
      {
        "id": "1",
        "label": "前端"
      },
      {
        "id": "2",
        "label": "JAVA"
      },
      {
        "id": "3",
        "label": "PHP"
      },
      {
        "id": "4",
        "label": "Python"
      },
      {
        "id": "5",
        "label": "C / C++"
      },
      {
        "id": "6",
        "label": "数据库"
      }
    ]
  },
  "meta": {
    "msg": "success",
    "status": 200
  }
}
```

### 2 热搜文章列表

- 请求路径：/hot/list
- 请求方法：get
- 请求参数

| 参数名 | 参数说明  | 备注 |
| ------ | --------- | ---- |
| type   | tab 的 id |      |

- 响应参数

| 参数名     | 参数说明           | 备注 |
| ---------- | ------------------ | ---- |
| avatarurl  | 小头像             |      |
| user_name  | 用户名             |      |
| created_at | 创建时间           |      |
| title      | 标题               |      |
| nickname   | 用户名             |      |
| desc       | 简介               |      |
| type       | 文章类型           |      |
| summary    | 摘要               |      |
| shown_time | 展示时间（时间戳） |      |
| avatar     | 大图头像           |      |
| typeLabel  | 文章类型的描述     |      |

- 响应数据

```json
{
    "success": true,
    "code": 10000,
    "data": {
        "list": [
           {
                "_id": "6086a06482820e018ce54b3b",
                "avatarurl": "https://profile.csdnimg.cn/B/8/2/3_hebtu666",
                "user_name": "hebtu666",
                "created_at": "01月01日",
                "title": "大学四年自学进BAT，私下存的资源/工具/网站我全贡献出来了",
                "nickname": "兔老大RabbitMQ",
                "desc": "这些工具/网站是我横扫BAT的重要一步，甚至是决定性的一步。",
                "type": "0",
                "summary": "这些工具/网站是我横扫BAT的重要一步，甚至是决定性的一步。",
                "shown_time": "1619435402",
                "avatar": "https://profile.csdnimg.cn/B/8/2/1_hebtu666",
                "typeLabel": "home"
            },
            ...
        ]
    },
    "message": "执行成功"
}
```

## 文章搜索

### 1 热搜搜索列表

- 请求路径：/search/hot-list
- 请求方法：get
- 请求参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
| 无     |          |      |

- 响应参数

| 参数名 | 参数说明   | 备注 |
| ------ | ---------- | ---- |
| id     | tab ID     |      |
| text   | tab 的名称 |      |

- 响应数据

```json
{
  "data": {
    "list": [
      {
        "id": "0",
        "label": "python人工智能"
      },
      {
        "id": "1",
        "label": "程序员离职小技巧"
      },
      {
        "id": "2",
        "label": "java集合常见面试题"
      },
      {
        "id": "3",
        "label": "Linux 常用命令大全"
      },
      {
        "id": "4",
        "label": "spring"
      },
      {
        "id": "5",
        "label": "程序员如何找对象"
      },
      {
        "id": "6",
        "label": "前端常用技术"
      },
      {
        "id": "7",
        "label": "程序员如何接私活"
      }
    ]
  },
  "meta": {
    "msg": "success",
    "status": 200
  }
}
```

### 2 搜索结果

- 请求路径：/search
- 请求方法：get
- 请求参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
| q      | 搜索内容 |      |
| p      | 分页页数 |      |

- 响应参数

| 参数名          | 参数说明                  | 备注 |
| --------------- | ------------------------- | ---- |
| pic             | 大图                      |      |
| type            | 文章类型                  |      |
| body            | 内容                      |      |
| author_label    | 作者的 label              |      |
| id              | id                        |      |
| blogId          | 博客 id                   |      |
| create_time     | 创建时间（时间戳）        |      |
| author          | 作者                      |      |
| author_id       | 作者 id                   |      |
| description     | 文章描述                  |      |
| created_at      | 创建时间（字符串）        |      |
| title           | 标题                      |      |
| nickname        | 作者昵称                  |      |
| digest          | 文章摘要                  |      |
| updateTime      | 更新时间（时间戳）        |      |
| url             | 文章地址                  |      |
| create_time_str | 创建时间（字符串 年月日） |      |
| pic_list        | 图片列表                  |      |

- 响应数据

```json
{
    "success": true,
    "code": 10000,
    "data": {
        "list": [
            {
                "pic": "",
                "type": "blog",
                "body": "<em>uniapp</em>快速入门 一、uni-app简单介绍 **什么是uni-app？** uni-app的优点 二、如何创建<em>uniapp</em>项目 1、安装HBuilderX 2、如何在微信小程序里面跑起来 3、官方提示 三、学习框架 1、项目结构介绍 2、开发规范 2.1 uni-...",
                "author_label": "作者",
                "id": "110665347",
                "blogId": "9999649",
                "create_time": "1607083188000",
                "level": "0",
                "author": "weixin_47592687",
                "author_id": "9999649",
                "description": "<em>uniapp</em>快速入门一、uni-app简单介绍**什么是uni-app？**uni-app的优点二、如何创建<em>uniapp</em>项目1、安装HBuilderX2、如何在微信小程序里面跑起来3、官方提示三、学习框架1、项目结构介绍2、开发规范2.1 uni-app 约定的...",
                "created_at": "2020-12-04 19:59:48",
                "title": "<em>uniapp</em>快速入门",
                "nickname": "祎祎呀",
                "digest": "<em>uniapp</em>快速入门一、uni-app简单介绍**什么是uni-app？**uni-app的优点二、如何创建<em>uniapp</em>项目1、安装HBuilderX2、如何在微信小程序里面跑起来3、官方提示三、学习框架1、项目结构介绍2、开发规范2.1 uni-app 约定的...",
                "updateTime": "2020-12-04 19:59:48",
                "url": "https://blog.csdn.net/weixin_47592687/article/details/110665347?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522161943829416780255238009%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=161943829416780255238009&biz_id=0&utm_medium=distribute.wap_search_result.none-task-blog-2~all~top_positive~default-1-110665347.wap_first_rank_v2_rank_v29&utm_term=uniapp",
                "create_time_str": "2020-12-04",
                "pic_list": [
                    "https://img-blog.csdnimg.cn/20201204185747416.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NzU5MjY4Nw==,size_16,color_FFFFFF,t_70,image/resize,m_fixed,h_150",
                    "https://img-blog.csdnimg.cn/20201204190018414.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NzU5MjY4Nw==,size_16,color_FFFFFF,t_70,image/resize,m_fixed,h_150",
                    "https://img-blog.csdnimg.cn/20201204190203290.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NzU5MjY4Nw==,size_16,color_FFFFFF,t_70,image/resize,m_fixed,h_150"
                ]
            },
            ...
        ]
    },
    "message": "执行成功"
}
```

### 3 返回默认搜索内容

- 请求路径：/search/default-text
- 请求方法：get
- 请求参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
| 无     |          |      |

- 响应参数

| 参数名      | 参数说明     | 备注 |
| ----------- | ------------ | ---- |
| defaultText | 默认搜索内容 |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "defaultText": "mysql"
  },
  "message": "执行成功"
}
```

## 文章详情

### 1. 文章详情

- 请求路径：/article/details
- 请求方法：get
- 请求参数

| 参数名    | 参数说明                                  | 备注 |
| --------- | ----------------------------------------- | ---- |
| author    | 作者名 （列表中的 author \|\| user_name） |      |
| articleId | id（列表中的 id）                         |      |

- 响应参数

| 参数名        | 参数说明         | 备注 |
| ------------- | ---------------- | ---- |
| title         | 标题名           |      |
| date          | 发布时间         |      |
| nickName      | 作者             |      |
| username      | 用户名           |      |
| articleTitle  | 文章标题         |      |
| avatar        | 头像             |      |
| articleDesc   | 简介             |      |
| articleTitles | 文章标题（详细） |      |
| content       | 文章内容         |      |
| isFollow      | 是否关注         |      |
| isPraise      | 是否收藏         |      |
| isCollect     | 是否点赞         |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "data": {
      "title": "uniapp快速入门_祎祎呀的博客-CSDN博客_uniapp入门",
      "nickName": "祎祎呀",
      "username": "weixin_47592687",
      "articleTitle": "uniapp快速入门",
      "avatar": "https://profile.csdnimg.cn/8/4/5/3_weixin_47592687",
      "articleDesc": "uniapp快速入门一、uni-app简单介绍**什么是uni-app？**uni-app的优点二、如何创建uniapp项目1、安装HBuilderX2、如何在微信小程序里面跑起来3、官方提示三、学习框架1、项目结构介绍2、开发规范2.1 uni-app 约定的开发规范2.2 uni-app 开发的注意事项3、页面样式与布局（1）尺寸单位三，如何使用组件四、路由跳转1、uni.navigateTo(OBJECT)2、uni.redirectTo(OBJECT)3、uni.reLaunch(OBJECT)4、",
      "articleTitles": "uniapp快速入门_祎祎呀的博客-CSDN博客_uniapp入门",
      "content": "\n        <div id=\"article_content\" class=\"article_content clearfix\">\n        <link rel=\"stylesheet\" href=\"https://csdnimg.cn/release/blogv2/dist/mdeditor/css/editerView/ck_htmledit_views-b5506197d8.css\">\n                <div id=\"content_views\" class=\"markdown_views prism-atelier-sulphurpool-light\">\n                    <svg xmlns=\"http://www.w3.org/2000/svg\" style=\"display: none;\">\n                        <path stroke-linecap=\"round\" d=\"M5,0 0,2.5 5,5z\" id=\"raphael-marker-block\" style=\"-webkit-tap-highlight-color: rgba(0, 0, 0, 0);\"></path>\n                    </svg>\n                    <p></p>\n<div class=\"toc\">\n <h3>uniapp快速入门</h3>\n <ul><li><a href=\"#uniapp_3\">一、uni-app简单介绍</a></li><li><ul><li><a href=\"#uniapp_5\">**什么是uni-app&#xff1f;**</a></li><li><a href=\"#uniapp_11\">uni-app的优点</a></li></ul>\n  </li><li><a href=\"#uniapp_31\">二、如何创建uniapp项目</a></li><li><ul><li><a href=\"#1HBuilderX_33\">1、安装HBuilderX</a></li><li><a href=\"#2_40\">2、如何在微信小程序里面跑起来</a></li><li><a href=\"#3_43\">3、官方提示</a></li></ul>\n  </li><li><a href=\"#_48\">三、学习框架</a></li><li><ul><li><a href=\"#1_50\">1、项目结构介绍</a></li></ul>\n  </li><li><a href=\"#2_53\">2、开发规范</a></li><li><ul><li><a href=\"#21_uniapp__55\">2.1 uni-app 约定的开发规范</a></li><li><a href=\"#22_uniapp__63\">2.2 uni-app 开发的注意事项</a></li></ul>\n  </li><li><a href=\"#3_81\">3、页面样式与布局</a></li><li><ul><li><a href=\"#1_83\">&#xff08;1&#xff09;尺寸单位</a></li></ul>\n  </li><li><a href=\"#_89\">三&#xff0c;如何使用组件</a></li><li><a href=\"#_95\">      </div>\n    "
    }
  },
  "message": "执行成功"
}
```

###

### 2. 文章评论列表

- 请求路径：/article/comment/list
- 请求方法：get
- 请求参数

| 参数名    | 参数说明 | 备注 |
| --------- | -------- | ---- |
| articleId | 文章 ID  |      |
| page      | 页数     |      |
| size      | 每页数据 |      |

- 响应参数

| 参数名          | 参数说明     | 备注 |
| --------------- | ------------ | ---- |
| count           | 评论总数     |      |
| pageCount       | 总页数       |      |
| list            | 评论列表     |      |
| -- info         | 数据对象     |      |
| -- -- commentId | 当前评论 ID  |      |
| -- --articleId  | 文章 ID      |      |
| -- --postTime   | 发送时间     |      |
| -- --content    | 评论内容     |      |
| -- --userName   | 评论用户名   |      |
| -- --digg       | 点赞数       |      |
| -- --avatar     | 评论用户头像 |      |
| -- --nickName   | 用户昵称     |      |
| -- --date       | 评论时间     |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "count": 28,
    "pageCount": 28,
    "list": [
      {
        "info": {
          "commentId": 12464458,
          "articleId": 106501992,
          "parentId": 0,
          "postTime": "2020-06-06 22:08:25",
          "content": "用心了，谢谢作者了，支持",
          "userName": "qq_45623325",
          "digg": 1,
          "diggArr": [],
          "parentUserName": null,
          "parentNickName": null,
          "avatar": "https://profile.csdnimg.cn/4/D/3/3_qq_45623325",
          "nickName": "格子衫程序范",
          "dateFormat": "10 月前",
          "tag": "",
          "parentTag": null,
          "years": null,
          "vip": null,
          "vipIcon": null,
          "companyBlog": null,
          "companyBlogIcon": null,
          "flag": null,
          "flagIcon": null,
          "levelIcon": null
        },
        "pointCommentId": null
      }
    ]
  },
  "message": "执行成功"
}
```

## 需要登录验证

### 1. 关注用户

- 请求路径：/user/follow
- 请求方法：get
- 请求头

| 参数名        | 参数说明 | 备注         |
| ------------- | -------- | ------------ |
| Authorization | token    | 用户登录凭证 |

- 请求参数

| 参数名   | 参数说明                                  | 备注 |
| -------- | ----------------------------------------- | ---- |
| author   | 作者名 （列表中的 author \|\| user_name） |      |
| isFloolw | true \|\| false                           |      |

- 响应参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
|        |          |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": null,
  "message": "执行成功"
}
```

### 2. 文章点赞

- 请求路径：/user/praise
- 请求方法：get
- 请求头

| 参数名        | 参数说明 | 备注         |
| ------------- | -------- | ------------ |
| Authorization | token    | 用户登录凭证 |

- 请求参数

| 参数名    | 参数说明        | 备注 |
| --------- | --------------- | ---- |
| articleId | 文章 ID         |      |
| isPraise  | true \|\| false |      |

- 响应参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
|        |          |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": null,
  "message": "执行成功"
}
```

### 3. 文章收藏

- 请求路径：/user/collect
- 请求方法：get
- 请求头

| 参数名        | 参数说明 | 备注         |
| ------------- | -------- | ------------ |
| Authorization | token    | 用户登录凭证 |

- 请求参数

| 参数名    | 参数说明        | 备注 |
| --------- | --------------- | ---- |
| articleId | 文章 ID         |      |
| isCollect | true \|\| false |      |

- 响应参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
|        |          |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": null,
  "message": "执行成功"
}
```

### 4. 发布 文章 / 视频 评论

- 请求路径：/user/article/comment
- 请求方法：post
- 请求头

| 参数名        | 参数说明 | 备注         |
| ------------- | -------- | ------------ |
| Authorization | token    | 用户登录凭证 |

- 请求参数

| 参数名    | 参数说明 | 备注 |
| --------- | -------- | ---- |
| articleId | 文章 ID  |      |
| content   | 评论内容 |      |

- 响应参数

| 参数名    | 参数说明 | 备注 |
| --------- | -------- | ---- |
| articleId | 文章 ID  |      |
| content   | 文章内容 |      |
| nickName  | 用户名   |      |
| avatar    | 头像     |      |
| date      | 时间     |      |
|           |          |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "articleId": "123",
    "content": "评论内容",
    "nickName": "LGD_Sunday",
    "avatar": "https://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTL0tPwpUVQT510UXOSKw1zoSZ5881SsibKT5THhOkY1PNmxdqCiahMavNlY8PXwrSNb23rukpznN3mg/132",
    "date": "2021-04-27T03:39:22.957Z"
  },
  "message": "执行成功"
}
```

## 热播

### 1.热播列表

- 请求路径：/video/list
- 请求方法：get
- 请求参数

| 参数名 | 参数说明 | 备注 |
| ------ | -------- | ---- |
| page   | 页数     |      |
| size   | 每页数据 |      |

- 响应参数

| 参数名        | 参数说明     | 备注 |
| ------------- | ------------ | ---- |
| id            |              |      |
| title         | 标题         |      |
| poster_small  | 封面图（小） |      |
| poster_big    | 封面图（大） |      |
| poster_pc     | 封面图（PC） |      |
| source_name   | 资源名       |      |
| play_url      | 播放地址     |      |
| duration      | 时长         |      |
| url           | url          |      |
| show_tag      | tag          |      |
| publish_time  | 发布时间     |      |
| is_pay_column | 是否付费     |      |
| like          | 喜欢的数量   |      |
| comment       | 评论的数量   |      |
| playcnt       | 播放数       |      |
| fmplaycnt     | 播放数       |      |
| fmplaycnt_2   | 播放数       |      |
| outstand_tag  |              |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "list": [
      {
        "id": "4928366710166295155",
        "title": "贵州山歌《人生一辈都在忙》，送给大家！",
        "poster_small": "https://f7.baidu.com/it/u=1057114786,3797755990&fm=222&app=108&f=JPEG@s_0,w_660,h_370,q_80",
        "poster_big": "https://f7.baidu.com/it/u=1057114786,3797755990&fm=222&app=108&f=JPEG@s_0,w_660,h_370,q_80",
        "poster_pc": "https://f7.baidu.com/it/u=1057114786,3797755990&fm=222&app=108&f=JPEG@s_0,w_660,h_370,q_80",
        "source_name": "醉美歌声",
        "play_url": "http://vd4.bdstatic.com/mda-mdsd1ir2xadd1252/mda-mdsd1ir2xadd1252.mp4?v_from_s=tc_haokan_4469",
        "duration": "01:02",
        "url": "https://haokan.hao123.com/v?vid=4928366710166295155&pd=&context=",
        "show_tag": 0,
        "publish_time": "2021年04月27日",
        "is_pay_column": 0,
        "like": "17",
        "comment": "1",
        "playcnt": "1294",
        "fmplaycnt": "1294次播放",
        "fmplaycnt_2": "1294",
        "outstand_tag": ""
      }
    ]
  },
  "message": "执行成功"
}
```

### 2. 视频弹幕

- 请求路径：/video/danmu
- 请求方法：get
- 请求参数

| 参数名  | 参数说明 | 备注 |
| ------- | -------- | ---- |
| videoId | 视频 ID  |      |

- 响应参数

| 参数名      | 参数说明             | 备注 |
| ----------- | -------------------- | ---- |
| thread_id   |                      |      |
| reply_id    |                      |      |
| uname       | 用户名               |      |
| create_time | 评论时间             |      |
| like_count  | 点赞数               |      |
| avatar      | 用户头像             |      |
| content     | 评论内容             |      |
| text        | 弹幕内容             |      |
| time        | 弹幕时间（单位：秒） |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "list": [
      {
        "thread_id": "1118000039009692",
        "reply_id": "1115669301634011514",
        "parent_id": "0",
        "user_id": 0,
        "uname": "亿团和气",
        "user_ip": "",
        "portrait": "02e17598",
        "create_time": "1613482028",
        "like_count": "607",
        "dislike_count": "0",
        "avatar": "https://himg.bdimg.com/sys/portrait/item/wise.1.2a8c15e1.t06_14gkTb1ulPHpJruCXQ.jpg?time=1116",
        "reply_to_uname": "",
        "content": "这首歌被黄丽玲演绎得出神入化！后部分才是精典！可惜视频却放了一半！黄丽玲是歌坛最为出色的女歌者之一！",
        "triple": 0,
        "game_time": "0",
        "content_rich": "",
        "score": "2835.0150795284",
        "cmt_from": "1",
        "type": "0",
        "is_lz": 0,
        "is_author": false,
        "reserved3": [],
        "reserved4": "",
        "relate_replyid": "",
        "is_self": "0",
        "vtype": "0",
        "reply_to_vtype": "0",
        "hot_level": 0,
        "author_uped": "0",
        "author_comment": "0",
        "author_replied": "0",
        "is_anonymous": 0,
        "favor": "0",
        "reply_count": "52",
        "reply_count2": "58",
        "uk": "",
        "is_uped": "0",
        "is_bomb": "0",
        "is_subscribe": 0,
        "is_friend": 0,
        "is_god": "0",
        "receiver_name": "",
        "owner_id": "",
        "vip_comment": "0",
        "vip_replied": "0",
        "reply_to_comment": [],
        "author_favor": "0",
        "third_id": "pqDZQHJCVpvIu6GTBaMTcQ",
        "user_type": "ugc",
        "commentor": [],
        "decorations": [],
        "create_time_text": "02月16日",
        "_bjh_is_author_reply": 0,
        "appid": "pqDZQHJCVpvIu6GTBaMTcQ",
        "vip": 0
      }
    ]
  },
  "message": "执行成功"
}
```

### 3. 视频评论

- 请求路径：/video/comment/list
- 请求方法：get
- 请求参数

| 参数名  | 参数说明 | 备注 |
| ------- | -------- | ---- |
| videoId | 视频 ID  |      |
| page    | 页数     |      |
| size    | 每页数据 |      |

- 响应参数

| 参数名      | 参数说明             | 备注 |
| ----------- | -------------------- | ---- |
| thread_id   |                      |      |
| reply_id    |                      |      |
| uname       | 用户名               |      |
| create_time | 评论时间             |      |
| like_count  | 点赞数               |      |
| avatar      | 用户头像             |      |
| content     | 评论内容             |      |
| text        | 弹幕内容             |      |
| time        | 弹幕时间（单位：秒） |      |

- 响应数据

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "list": [
      {
        "thread_id": "1118000039009692",
        "reply_id": "1115669301634011514",
        "parent_id": "0",
        "user_id": 0,
        "uname": "亿团和气",
        "user_ip": "",
        "portrait": "02e17598",
        "create_time": "1613482028",
        "like_count": "607",
        "dislike_count": "0",
        "avatar": "https://himg.bdimg.com/sys/portrait/item/wise.1.2a8c15e1.t06_14gkTb1ulPHpJruCXQ.jpg?time=1116",
        "reply_to_uname": "",
        "content": "这首歌被黄丽玲演绎得出神入化！后部分才是精典！可惜视频却放了一半！黄丽玲是歌坛最为出色的女歌者之一！",
        "triple": 0,
        "game_time": "0",
        "content_rich": "",
        "score": "2835.0150795284",
        "cmt_from": "1",
        "type": "0",
        "is_lz": 0,
        "is_author": false,
        "reserved3": [],
        "reserved4": "",
        "relate_replyid": "",
        "is_self": "0",
        "vtype": "0",
        "reply_to_vtype": "0",
        "hot_level": 0,
        "author_uped": "0",
        "author_comment": "0",
        "author_replied": "0",
        "is_anonymous": 0,
        "favor": "0",
        "reply_count": "52",
        "reply_count2": "58",
        "uk": "",
        "is_uped": "0",
        "is_bomb": "0",
        "is_subscribe": 0,
        "is_friend": 0,
        "is_god": "0",
        "receiver_name": "",
        "owner_id": "",
        "vip_comment": "0",
        "vip_replied": "0",
        "reply_to_comment": [],
        "author_favor": "0",
        "third_id": "pqDZQHJCVpvIu6GTBaMTcQ",
        "user_type": "ugc",
        "commentor": [],
        "decorations": [],
        "create_time_text": "02月16日",
        "_bjh_is_author_reply": 0,
        "appid": "pqDZQHJCVpvIu6GTBaMTcQ",
        "vip": 0
      }
    ]
  },
  "message": "执行成功"
}
```

## 案例接口

### 1： get 请求测试用接口

- 请求路径：/test/getList
- 请求方法：get
- 请求参数

| 参数名 | 参数说明   | 备注 |
| ------ | ---------- | ---- |
| page   | 当前页数   |      |
| size   | 每页的数据 |      |

- 响应参数

| 参数名        | 参数说明 | 备注 |
| ------------- | -------- | ---- |
| page          | 当前页   |      |
| size          | 每页页数 |      |
| total         | 总数     |      |
| list -> title | 标题     |      |

- 响应数据

```json
{
    "success": true,
    "code": 10000,
    "data": {
        "page": 1,
        "size": 20,
        "total": 14,
        "list": [
            {
                "title": "用 JavaScript 实现手势库 — 手势逻辑【前端组件化】"
            },
            ...
        ]
    },
    "message": "执行成功"
}
```

### 2：post 请求测试用接口

- 请求路径：/test/postData
- 请求方法：post
- 请求参数：请求内容与返回内容相同

### 3：使用 promise 解决异步编程的测试接口

- 请求路径：`/test/A` || `/test/B` || `/test/C` || `/test/D`
- 请求方法：get
- 请求参数：
