### âï¸ Tangxt â³ 2021-12-10 ð·ï¸ API

## baseURL

`https://api.imooc-blog.lgdsunday.club/api`

## ç¨æ·ä¿¡æ¯

### 1. ç»å½ï¼å¾®ä¿¡ç¨æ·ï¼

- è¯·æ±è·¯å¾ï¼/sys/login
- è¯·æ±æ¹æ³ï¼post
- è¯·æ±åæ°

| åæ°å    | åæ°è¯´æ                                                         | å¤æ³¨ |
| --------- | ---------------------------------------------------------------- | ---- |
| signature | ä½¿ç¨ sha1( rawData + sessionkey ) å¾å°å­ç¬¦ä¸²ï¼ç¨äºæ ¡éªç¨æ·ä¿¡æ¯ï¼ |      |
| iv        | å å¯ç®æ³çåå§åé                                               |      |
| nickName  | ç¨æ·æµç§°                                                         |      |
| gender    | æ§å«ï¼0ï¼å¥³ 1ï¼ç·ï¼                                              |      |
| city      | æå¨åå¸                                                         |      |
| province  | æå¨çä»½                                                         |      |
| avatarUrl | å¤´åè·¯å¾                                                         |      |

- ååºåæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
| token  |          |      |
|        |          |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "token": "Bearer d8c6ed7a-3fd4-46e4-a477-b20d1ce9cda0"
  },
  "message": "æ§è¡æå"
}
```

## ç­æ

### 1 ç­ææç« ç±»å

- è¯·æ±è·¯å¾ï¼/hot/tabs
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
| æ      |          |      |

- ååºåæ°

| åæ°å | åæ°è¯´æ   | å¤æ³¨ |
| ------ | ---------- | ---- |
| id     | tab ID     |      |
| text   | tab çåç§° |      |

- ååºæ°æ®

```json
{
  "data": {
    "list": [
      {
        "id": "0",
        "label": "ç­æ¦"
      },
      {
        "id": "1",
        "label": "åç«¯"
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
        "label": "æ°æ®åº"
      }
    ]
  },
  "meta": {
    "msg": "success",
    "status": 200
  }
}
```

### 2 ç­ææç« åè¡¨

- è¯·æ±è·¯å¾ï¼/hot/list
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ  | å¤æ³¨ |
| ------ | --------- | ---- |
| type   | tab ç id |      |

- ååºåæ°

| åæ°å     | åæ°è¯´æ           | å¤æ³¨ |
| ---------- | ------------------ | ---- |
| avatarurl  | å°å¤´å             |      |
| user_name  | ç¨æ·å             |      |
| created_at | åå»ºæ¶é´           |      |
| title      | æ é¢               |      |
| nickname   | ç¨æ·å             |      |
| desc       | ç®ä»               |      |
| type       | æç« ç±»å           |      |
| summary    | æè¦               |      |
| shown_time | å±ç¤ºæ¶é´ï¼æ¶é´æ³ï¼ |      |
| avatar     | å¤§å¾å¤´å           |      |
| typeLabel  | æç« ç±»åçæè¿°     |      |

- ååºæ°æ®

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
                "created_at": "01æ01æ¥",
                "title": "å¤§å­¦åå¹´èªå­¦è¿BATï¼ç§ä¸å­çèµæº/å·¥å·/ç½ç«æå¨è´¡ç®åºæ¥äº",
                "nickname": "åèå¤§RabbitMQ",
                "desc": "è¿äºå·¥å·/ç½ç«æ¯ææ¨ªæ«BATçéè¦ä¸æ­¥ï¼çè³æ¯å³å®æ§çä¸æ­¥ã",
                "type": "0",
                "summary": "è¿äºå·¥å·/ç½ç«æ¯ææ¨ªæ«BATçéè¦ä¸æ­¥ï¼çè³æ¯å³å®æ§çä¸æ­¥ã",
                "shown_time": "1619435402",
                "avatar": "https://profile.csdnimg.cn/B/8/2/1_hebtu666",
                "typeLabel": "home"
            },
            ...
        ]
    },
    "message": "æ§è¡æå"
}
```

## æç« æç´¢

### 1 ç­ææç´¢åè¡¨

- è¯·æ±è·¯å¾ï¼/search/hot-list
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
| æ      |          |      |

- ååºåæ°

| åæ°å | åæ°è¯´æ   | å¤æ³¨ |
| ------ | ---------- | ---- |
| id     | tab ID     |      |
| text   | tab çåç§° |      |

- ååºæ°æ®

```json
{
  "data": {
    "list": [
      {
        "id": "0",
        "label": "pythonäººå·¥æºè½"
      },
      {
        "id": "1",
        "label": "ç¨åºåç¦»èå°æå·§"
      },
      {
        "id": "2",
        "label": "javaéåå¸¸è§é¢è¯é¢"
      },
      {
        "id": "3",
        "label": "Linux å¸¸ç¨å½ä»¤å¤§å¨"
      },
      {
        "id": "4",
        "label": "spring"
      },
      {
        "id": "5",
        "label": "ç¨åºåå¦ä½æ¾å¯¹è±¡"
      },
      {
        "id": "6",
        "label": "åç«¯å¸¸ç¨ææ¯"
      },
      {
        "id": "7",
        "label": "ç¨åºåå¦ä½æ¥ç§æ´»"
      }
    ]
  },
  "meta": {
    "msg": "success",
    "status": 200
  }
}
```

### 2 æç´¢ç»æ

- è¯·æ±è·¯å¾ï¼/search
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
| q      | æç´¢åå®¹ |      |
| p      | åé¡µé¡µæ° |      |

- ååºåæ°

| åæ°å          | åæ°è¯´æ                  | å¤æ³¨ |
| --------------- | ------------------------- | ---- |
| pic             | å¤§å¾                      |      |
| type            | æç« ç±»å                  |      |
| body            | åå®¹                      |      |
| author_label    | ä½èç label              |      |
| id              | id                        |      |
| blogId          | åå®¢ id                   |      |
| create_time     | åå»ºæ¶é´ï¼æ¶é´æ³ï¼        |      |
| author          | ä½è                      |      |
| author_id       | ä½è id                   |      |
| description     | æç« æè¿°                  |      |
| created_at      | åå»ºæ¶é´ï¼å­ç¬¦ä¸²ï¼        |      |
| title           | æ é¢                      |      |
| nickname        | ä½èæµç§°                  |      |
| digest          | æç« æè¦                  |      |
| updateTime      | æ´æ°æ¶é´ï¼æ¶é´æ³ï¼        |      |
| url             | æç« å°å                  |      |
| create_time_str | åå»ºæ¶é´ï¼å­ç¬¦ä¸² å¹´ææ¥ï¼ |      |
| pic_list        | å¾çåè¡¨                  |      |

- ååºæ°æ®

```json
{
    "success": true,
    "code": 10000,
    "data": {
        "list": [
            {
                "pic": "",
                "type": "blog",
                "body": "<em>uniapp</em>å¿«éå¥é¨ ä¸ãuni-appç®åä»ç» **ä»ä¹æ¯uni-appï¼** uni-appçä¼ç¹ äºãå¦ä½åå»º<em>uniapp</em>é¡¹ç® 1ãå®è£HBuilderX 2ãå¦ä½å¨å¾®ä¿¡å°ç¨åºéé¢è·èµ·æ¥ 3ãå®æ¹æç¤º ä¸ãå­¦ä¹ æ¡æ¶ 1ãé¡¹ç®ç»æä»ç» 2ãå¼åè§è 2.1 uni-...",
                "author_label": "ä½è",
                "id": "110665347",
                "blogId": "9999649",
                "create_time": "1607083188000",
                "level": "0",
                "author": "weixin_47592687",
                "author_id": "9999649",
                "description": "<em>uniapp</em>å¿«éå¥é¨ä¸ãuni-appç®åä»ç»**ä»ä¹æ¯uni-appï¼**uni-appçä¼ç¹äºãå¦ä½åå»º<em>uniapp</em>é¡¹ç®1ãå®è£HBuilderX2ãå¦ä½å¨å¾®ä¿¡å°ç¨åºéé¢è·èµ·æ¥3ãå®æ¹æç¤ºä¸ãå­¦ä¹ æ¡æ¶1ãé¡¹ç®ç»æä»ç»2ãå¼åè§è2.1 uni-app çº¦å®ç...",
                "created_at": "2020-12-04 19:59:48",
                "title": "<em>uniapp</em>å¿«éå¥é¨",
                "nickname": "ç¥ç¥å",
                "digest": "<em>uniapp</em>å¿«éå¥é¨ä¸ãuni-appç®åä»ç»**ä»ä¹æ¯uni-appï¼**uni-appçä¼ç¹äºãå¦ä½åå»º<em>uniapp</em>é¡¹ç®1ãå®è£HBuilderX2ãå¦ä½å¨å¾®ä¿¡å°ç¨åºéé¢è·èµ·æ¥3ãå®æ¹æç¤ºä¸ãå­¦ä¹ æ¡æ¶1ãé¡¹ç®ç»æä»ç»2ãå¼åè§è2.1 uni-app çº¦å®ç...",
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
    "message": "æ§è¡æå"
}
```

### 3 è¿åé»è®¤æç´¢åå®¹

- è¯·æ±è·¯å¾ï¼/search/default-text
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
| æ      |          |      |

- ååºåæ°

| åæ°å      | åæ°è¯´æ     | å¤æ³¨ |
| ----------- | ------------ | ---- |
| defaultText | é»è®¤æç´¢åå®¹ |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "defaultText": "mysql"
  },
  "message": "æ§è¡æå"
}
```

## æç« è¯¦æ

### 1. æç« è¯¦æ

- è¯·æ±è·¯å¾ï¼/article/details
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å    | åæ°è¯´æ                                  | å¤æ³¨ |
| --------- | ----------------------------------------- | ---- |
| author    | ä½èå ï¼åè¡¨ä¸­ç author \|\| user_nameï¼ |      |
| articleId | idï¼åè¡¨ä¸­ç idï¼                         |      |

- ååºåæ°

| åæ°å        | åæ°è¯´æ         | å¤æ³¨ |
| ------------- | ---------------- | ---- |
| title         | æ é¢å           |      |
| date          | åå¸æ¶é´         |      |
| nickName      | ä½è             |      |
| username      | ç¨æ·å           |      |
| articleTitle  | æç« æ é¢         |      |
| avatar        | å¤´å             |      |
| articleDesc   | ç®ä»             |      |
| articleTitles | æç« æ é¢ï¼è¯¦ç»ï¼ |      |
| content       | æç« åå®¹         |      |
| isFollow      | æ¯å¦å³æ³¨         |      |
| isPraise      | æ¯å¦æ¶è         |      |
| isCollect     | æ¯å¦ç¹èµ         |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "data": {
      "title": "uniappå¿«éå¥é¨_ç¥ç¥åçåå®¢-CSDNåå®¢_uniappå¥é¨",
      "nickName": "ç¥ç¥å",
      "username": "weixin_47592687",
      "articleTitle": "uniappå¿«éå¥é¨",
      "avatar": "https://profile.csdnimg.cn/8/4/5/3_weixin_47592687",
      "articleDesc": "uniappå¿«éå¥é¨ä¸ãuni-appç®åä»ç»**ä»ä¹æ¯uni-appï¼**uni-appçä¼ç¹äºãå¦ä½åå»ºuniappé¡¹ç®1ãå®è£HBuilderX2ãå¦ä½å¨å¾®ä¿¡å°ç¨åºéé¢è·èµ·æ¥3ãå®æ¹æç¤ºä¸ãå­¦ä¹ æ¡æ¶1ãé¡¹ç®ç»æä»ç»2ãå¼åè§è2.1 uni-app çº¦å®çå¼åè§è2.2 uni-app å¼åçæ³¨æäºé¡¹3ãé¡µé¢æ ·å¼ä¸å¸å±ï¼1ï¼å°ºå¯¸åä½ä¸ï¼å¦ä½ä½¿ç¨ç»ä»¶åãè·¯ç±è·³è½¬1ãuni.navigateTo(OBJECT)2ãuni.redirectTo(OBJECT)3ãuni.reLaunch(OBJECT)4ã",
      "articleTitles": "uniappå¿«éå¥é¨_ç¥ç¥åçåå®¢-CSDNåå®¢_uniappå¥é¨",
      "content": "\n        <div id=\"article_content\" class=\"article_content clearfix\">\n        <link rel=\"stylesheet\" href=\"https://csdnimg.cn/release/blogv2/dist/mdeditor/css/editerView/ck_htmledit_views-b5506197d8.css\">\n                <div id=\"content_views\" class=\"markdown_views prism-atelier-sulphurpool-light\">\n                    <svg xmlns=\"http://www.w3.org/2000/svg\" style=\"display: none;\">\n                        <path stroke-linecap=\"round\" d=\"M5,0 0,2.5 5,5z\" id=\"raphael-marker-block\" style=\"-webkit-tap-highlight-color: rgba(0, 0, 0, 0);\"></path>\n                    </svg>\n                    <p></p>\n<div class=\"toc\">\n <h3>uniappå¿«éå¥é¨</h3>\n <ul><li><a href=\"#uniapp_3\">ä¸ãuni-appç®åä»ç»</a></li><li><ul><li><a href=\"#uniapp_5\">**ä»ä¹æ¯uni-app&#xff1f;**</a></li><li><a href=\"#uniapp_11\">uni-appçä¼ç¹</a></li></ul>\n  </li><li><a href=\"#uniapp_31\">äºãå¦ä½åå»ºuniappé¡¹ç®</a></li><li><ul><li><a href=\"#1HBuilderX_33\">1ãå®è£HBuilderX</a></li><li><a href=\"#2_40\">2ãå¦ä½å¨å¾®ä¿¡å°ç¨åºéé¢è·èµ·æ¥</a></li><li><a href=\"#3_43\">3ãå®æ¹æç¤º</a></li></ul>\n  </li><li><a href=\"#_48\">ä¸ãå­¦ä¹ æ¡æ¶</a></li><li><ul><li><a href=\"#1_50\">1ãé¡¹ç®ç»æä»ç»</a></li></ul>\n  </li><li><a href=\"#2_53\">2ãå¼åè§è</a></li><li><ul><li><a href=\"#21_uniapp__55\">2.1 uni-app çº¦å®çå¼åè§è</a></li><li><a href=\"#22_uniapp__63\">2.2 uni-app å¼åçæ³¨æäºé¡¹</a></li></ul>\n  </li><li><a href=\"#3_81\">3ãé¡µé¢æ ·å¼ä¸å¸å±</a></li><li><ul><li><a href=\"#1_83\">&#xff08;1&#xff09;å°ºå¯¸åä½</a></li></ul>\n  </li><li><a href=\"#_89\">ä¸&#xff0c;å¦ä½ä½¿ç¨ç»ä»¶</a></li><li><a href=\"#_95\">      </div>\n    "
    }
  },
  "message": "æ§è¡æå"
}
```

###

### 2. æç« è¯è®ºåè¡¨

- è¯·æ±è·¯å¾ï¼/article/comment/list
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å    | åæ°è¯´æ | å¤æ³¨ |
| --------- | -------- | ---- |
| articleId | æç«  ID  |      |
| page      | é¡µæ°     |      |
| size      | æ¯é¡µæ°æ® |      |

- ååºåæ°

| åæ°å          | åæ°è¯´æ     | å¤æ³¨ |
| --------------- | ------------ | ---- |
| count           | è¯è®ºæ»æ°     |      |
| pageCount       | æ»é¡µæ°       |      |
| list            | è¯è®ºåè¡¨     |      |
| -- info         | æ°æ®å¯¹è±¡     |      |
| -- -- commentId | å½åè¯è®º ID  |      |
| -- --articleId  | æç«  ID      |      |
| -- --postTime   | åéæ¶é´     |      |
| -- --content    | è¯è®ºåå®¹     |      |
| -- --userName   | è¯è®ºç¨æ·å   |      |
| -- --digg       | ç¹èµæ°       |      |
| -- --avatar     | è¯è®ºç¨æ·å¤´å |      |
| -- --nickName   | ç¨æ·æµç§°     |      |
| -- --date       | è¯è®ºæ¶é´     |      |

- ååºæ°æ®

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
          "content": "ç¨å¿äºï¼è°¢è°¢ä½èäºï¼æ¯æ",
          "userName": "qq_45623325",
          "digg": 1,
          "diggArr": [],
          "parentUserName": null,
          "parentNickName": null,
          "avatar": "https://profile.csdnimg.cn/4/D/3/3_qq_45623325",
          "nickName": "æ ¼å­è¡«ç¨åºè",
          "dateFormat": "10 æå",
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
  "message": "æ§è¡æå"
}
```

## éè¦ç»å½éªè¯

### 1. å³æ³¨ç¨æ·

- è¯·æ±è·¯å¾ï¼/user/follow
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±å¤´

| åæ°å        | åæ°è¯´æ | å¤æ³¨         |
| ------------- | -------- | ------------ |
| Authorization | token    | ç¨æ·ç»å½å­è¯ |

- è¯·æ±åæ°

| åæ°å   | åæ°è¯´æ                                  | å¤æ³¨ |
| -------- | ----------------------------------------- | ---- |
| author   | ä½èå ï¼åè¡¨ä¸­ç author \|\| user_nameï¼ |      |
| isFloolw | true \|\| false                           |      |

- ååºåæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
|        |          |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": null,
  "message": "æ§è¡æå"
}
```

### 2. æç« ç¹èµ

- è¯·æ±è·¯å¾ï¼/user/praise
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±å¤´

| åæ°å        | åæ°è¯´æ | å¤æ³¨         |
| ------------- | -------- | ------------ |
| Authorization | token    | ç¨æ·ç»å½å­è¯ |

- è¯·æ±åæ°

| åæ°å    | åæ°è¯´æ        | å¤æ³¨ |
| --------- | --------------- | ---- |
| articleId | æç«  ID         |      |
| isPraise  | true \|\| false |      |

- ååºåæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
|        |          |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": null,
  "message": "æ§è¡æå"
}
```

### 3. æç« æ¶è

- è¯·æ±è·¯å¾ï¼/user/collect
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±å¤´

| åæ°å        | åæ°è¯´æ | å¤æ³¨         |
| ------------- | -------- | ------------ |
| Authorization | token    | ç¨æ·ç»å½å­è¯ |

- è¯·æ±åæ°

| åæ°å    | åæ°è¯´æ        | å¤æ³¨ |
| --------- | --------------- | ---- |
| articleId | æç«  ID         |      |
| isCollect | true \|\| false |      |

- ååºåæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
|        |          |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": null,
  "message": "æ§è¡æå"
}
```

### 4. åå¸ æç«  / è§é¢ è¯è®º

- è¯·æ±è·¯å¾ï¼/user/article/comment
- è¯·æ±æ¹æ³ï¼post
- è¯·æ±å¤´

| åæ°å        | åæ°è¯´æ | å¤æ³¨         |
| ------------- | -------- | ------------ |
| Authorization | token    | ç¨æ·ç»å½å­è¯ |

- è¯·æ±åæ°

| åæ°å    | åæ°è¯´æ | å¤æ³¨ |
| --------- | -------- | ---- |
| articleId | æç«  ID  |      |
| content   | è¯è®ºåå®¹ |      |

- ååºåæ°

| åæ°å    | åæ°è¯´æ | å¤æ³¨ |
| --------- | -------- | ---- |
| articleId | æç«  ID  |      |
| content   | æç« åå®¹ |      |
| nickName  | ç¨æ·å   |      |
| avatar    | å¤´å     |      |
| date      | æ¶é´     |      |
|           |          |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "articleId": "123",
    "content": "è¯è®ºåå®¹",
    "nickName": "LGD_Sunday",
    "avatar": "https://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTL0tPwpUVQT510UXOSKw1zoSZ5881SsibKT5THhOkY1PNmxdqCiahMavNlY8PXwrSNb23rukpznN3mg/132",
    "date": "2021-04-27T03:39:22.957Z"
  },
  "message": "æ§è¡æå"
}
```

## ç­æ­

### 1.ç­æ­åè¡¨

- è¯·æ±è·¯å¾ï¼/video/list
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ | å¤æ³¨ |
| ------ | -------- | ---- |
| page   | é¡µæ°     |      |
| size   | æ¯é¡µæ°æ® |      |

- ååºåæ°

| åæ°å        | åæ°è¯´æ     | å¤æ³¨ |
| ------------- | ------------ | ---- |
| id            |              |      |
| title         | æ é¢         |      |
| poster_small  | å°é¢å¾ï¼å°ï¼ |      |
| poster_big    | å°é¢å¾ï¼å¤§ï¼ |      |
| poster_pc     | å°é¢å¾ï¼PCï¼ |      |
| source_name   | èµæºå       |      |
| play_url      | æ­æ¾å°å     |      |
| duration      | æ¶é¿         |      |
| url           | url          |      |
| show_tag      | tag          |      |
| publish_time  | åå¸æ¶é´     |      |
| is_pay_column | æ¯å¦ä»è´¹     |      |
| like          | åæ¬¢çæ°é   |      |
| comment       | è¯è®ºçæ°é   |      |
| playcnt       | æ­æ¾æ°       |      |
| fmplaycnt     | æ­æ¾æ°       |      |
| fmplaycnt_2   | æ­æ¾æ°       |      |
| outstand_tag  |              |      |

- ååºæ°æ®

```json
{
  "success": true,
  "code": 10000,
  "data": {
    "list": [
      {
        "id": "4928366710166295155",
        "title": "è´µå·å±±æ­ãäººçä¸è¾é½å¨å¿ãï¼éç»å¤§å®¶ï¼",
        "poster_small": "https://f7.baidu.com/it/u=1057114786,3797755990&fm=222&app=108&f=JPEG@s_0,w_660,h_370,q_80",
        "poster_big": "https://f7.baidu.com/it/u=1057114786,3797755990&fm=222&app=108&f=JPEG@s_0,w_660,h_370,q_80",
        "poster_pc": "https://f7.baidu.com/it/u=1057114786,3797755990&fm=222&app=108&f=JPEG@s_0,w_660,h_370,q_80",
        "source_name": "éç¾æ­å£°",
        "play_url": "http://vd4.bdstatic.com/mda-mdsd1ir2xadd1252/mda-mdsd1ir2xadd1252.mp4?v_from_s=tc_haokan_4469",
        "duration": "01:02",
        "url": "https://haokan.hao123.com/v?vid=4928366710166295155&pd=&context=",
        "show_tag": 0,
        "publish_time": "2021å¹´04æ27æ¥",
        "is_pay_column": 0,
        "like": "17",
        "comment": "1",
        "playcnt": "1294",
        "fmplaycnt": "1294æ¬¡æ­æ¾",
        "fmplaycnt_2": "1294",
        "outstand_tag": ""
      }
    ]
  },
  "message": "æ§è¡æå"
}
```

### 2. è§é¢å¼¹å¹

- è¯·æ±è·¯å¾ï¼/video/danmu
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å  | åæ°è¯´æ | å¤æ³¨ |
| ------- | -------- | ---- |
| videoId | è§é¢ ID  |      |

- ååºåæ°

| åæ°å      | åæ°è¯´æ             | å¤æ³¨ |
| ----------- | -------------------- | ---- |
| thread_id   |                      |      |
| reply_id    |                      |      |
| uname       | ç¨æ·å               |      |
| create_time | è¯è®ºæ¶é´             |      |
| like_count  | ç¹èµæ°               |      |
| avatar      | ç¨æ·å¤´å             |      |
| content     | è¯è®ºåå®¹             |      |
| text        | å¼¹å¹åå®¹             |      |
| time        | å¼¹å¹æ¶é´ï¼åä½ï¼ç§ï¼ |      |

- ååºæ°æ®

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
        "uname": "äº¿å¢åæ°",
        "user_ip": "",
        "portrait": "02e17598",
        "create_time": "1613482028",
        "like_count": "607",
        "dislike_count": "0",
        "avatar": "https://himg.bdimg.com/sys/portrait/item/wise.1.2a8c15e1.t06_14gkTb1ulPHpJruCXQ.jpg?time=1116",
        "reply_to_uname": "",
        "content": "è¿é¦æ­è¢«é»ä¸½ç²æ¼ç»å¾åºç¥å¥åï¼åé¨åææ¯ç²¾å¸ï¼å¯æè§é¢å´æ¾äºä¸åï¼é»ä¸½ç²æ¯æ­åæä¸ºåºè²çå¥³æ­èä¹ä¸ï¼",
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
        "create_time_text": "02æ16æ¥",
        "_bjh_is_author_reply": 0,
        "appid": "pqDZQHJCVpvIu6GTBaMTcQ",
        "vip": 0
      }
    ]
  },
  "message": "æ§è¡æå"
}
```

### 3. è§é¢è¯è®º

- è¯·æ±è·¯å¾ï¼/video/comment/list
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å  | åæ°è¯´æ | å¤æ³¨ |
| ------- | -------- | ---- |
| videoId | è§é¢ ID  |      |
| page    | é¡µæ°     |      |
| size    | æ¯é¡µæ°æ® |      |

- ååºåæ°

| åæ°å      | åæ°è¯´æ             | å¤æ³¨ |
| ----------- | -------------------- | ---- |
| thread_id   |                      |      |
| reply_id    |                      |      |
| uname       | ç¨æ·å               |      |
| create_time | è¯è®ºæ¶é´             |      |
| like_count  | ç¹èµæ°               |      |
| avatar      | ç¨æ·å¤´å             |      |
| content     | è¯è®ºåå®¹             |      |
| text        | å¼¹å¹åå®¹             |      |
| time        | å¼¹å¹æ¶é´ï¼åä½ï¼ç§ï¼ |      |

- ååºæ°æ®

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
        "uname": "äº¿å¢åæ°",
        "user_ip": "",
        "portrait": "02e17598",
        "create_time": "1613482028",
        "like_count": "607",
        "dislike_count": "0",
        "avatar": "https://himg.bdimg.com/sys/portrait/item/wise.1.2a8c15e1.t06_14gkTb1ulPHpJruCXQ.jpg?time=1116",
        "reply_to_uname": "",
        "content": "è¿é¦æ­è¢«é»ä¸½ç²æ¼ç»å¾åºç¥å¥åï¼åé¨åææ¯ç²¾å¸ï¼å¯æè§é¢å´æ¾äºä¸åï¼é»ä¸½ç²æ¯æ­åæä¸ºåºè²çå¥³æ­èä¹ä¸ï¼",
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
        "create_time_text": "02æ16æ¥",
        "_bjh_is_author_reply": 0,
        "appid": "pqDZQHJCVpvIu6GTBaMTcQ",
        "vip": 0
      }
    ]
  },
  "message": "æ§è¡æå"
}
```

## æ¡ä¾æ¥å£

### 1ï¼ get è¯·æ±æµè¯ç¨æ¥å£

- è¯·æ±è·¯å¾ï¼/test/getList
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°

| åæ°å | åæ°è¯´æ   | å¤æ³¨ |
| ------ | ---------- | ---- |
| page   | å½åé¡µæ°   |      |
| size   | æ¯é¡µçæ°æ® |      |

- ååºåæ°

| åæ°å        | åæ°è¯´æ | å¤æ³¨ |
| ------------- | -------- | ---- |
| page          | å½åé¡µ   |      |
| size          | æ¯é¡µé¡µæ° |      |
| total         | æ»æ°     |      |
| list -> title | æ é¢     |      |

- ååºæ°æ®

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
                "title": "ç¨ JavaScript å®ç°æå¿åº â æå¿é»è¾ãåç«¯ç»ä»¶åã"
            },
            ...
        ]
    },
    "message": "æ§è¡æå"
}
```

### 2ï¼post è¯·æ±æµè¯ç¨æ¥å£

- è¯·æ±è·¯å¾ï¼/test/postData
- è¯·æ±æ¹æ³ï¼post
- è¯·æ±åæ°ï¼è¯·æ±åå®¹ä¸è¿ååå®¹ç¸å

### 3ï¼ä½¿ç¨ promise è§£å³å¼æ­¥ç¼ç¨çæµè¯æ¥å£

- è¯·æ±è·¯å¾ï¼`/test/A` || `/test/B` || `/test/C` || `/test/D`
- è¯·æ±æ¹æ³ï¼get
- è¯·æ±åæ°ï¼
