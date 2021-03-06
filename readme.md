# groupChallengeEveryDay

[![Powered by Wechaty](https://img.shields.io/badge/Powered%20By-Wechaty-green.svg)](https://github.com/chatie/wechaty)
[![Wechaty开源激励计划](https://img.shields.io/badge/Wechaty-开源激励计划-green.svg)](https://github.com/juzibot/Welcome/wiki/Everything-about-Wechaty)

## 开发背景

某微信群中有人每天发布系列性的学习文章（专辑），文本形式。同事这些内容又对另外一些群适用，但是鉴于群的社交特性，不便都放到一个群里。而且bot不是群主。bot想做个雷锋，转发一下。

bot有几个垂直领域的群，都不是群主，但是每个群每天都在打开学习（可以持续365天的那种），但是微信新出的群打卡1.列表长2.书写麻烦，于是乎想做一个群打卡机器人，在使用特定关键词打卡后，进行友好回应提示，并给出激励提醒。（@you，恭喜您完成今日xx学习挑战，您已坚持count天，✊加油啊！）

![2020-04-22_14-47-57](https://i.loli.net/2020/04/22/GbYLMgv39A7JdZf.jpg)

## 功能

- 群转发
  - [x] 万群群发: 使用场景，新年问候，群发给所有群。
    - [x] 新建或配置一个群（主人群0421），本群里的所有消息将转发给（除本群外）的所有群！
  - [x] 经典转发： 指定A群里的任意成员b的消息，转发到其他指定C、D、E..群里
  - [ ] UI + BE + 数据库配置
- 群挑战GCED
  - [ ] 进群发送欢迎语/群公告
  - [ ] 任意成员发送指令【GCED】开启本群挑战模式，发送欢迎语与挑战说明
    - [ ] 恭喜，您已成功为本群发起【xx挑战365】打卡学习任务。@ALL 如同意参与挑战，请24小时内回复指令【我接受】即可在每日排行榜看到你漂亮的身影！
  - [ ] 用户每日回复指令（模糊识别关键词）打卡
  - [ ] 每日凌晨 `5:00` 统计打卡情况并进行公布
  - [ ] 每日早上 `8:00` 推送一条名人语录/挑战的系列内容
  - [ ] 打卡排行榜
- 管理员功能
  - [ ] 查看当天未签到用户 (当天0点前)
  - [ ] 查看三天未签到用户
  - [ ] 设置管理员
  - [ ] 设置黑名单（移除放弃挑战的成员）
  - [ ] 所有指令可后台配置/正则匹配
- Other
  - [ ] 配置使用群ID/以防群改名字了
  - [ ] 多种挑战类型供发起挑战，为避免混乱，一个群只能开一种
    - [ ] GTED-读经
    - [ ] GTED-诗篇
    - [ ] GTED-祷告 0101.mp3 ~ 1231.mp3
    - [ ] GTEP-视频 0101.mp4 ~ 1231.mp4


## 配置

```
# 设置token
copy .env.example .env
vi .env
    WECHATY_PUPPET_PADPLUS_TOKEN=puppet_padplus_13f028f0cba*******

# 设置转发规则
copy forward.json.example forward.json
vi forward.json
```



## 开发

```
npm install
npm start
```



## 上线

```
docker-compose up -d
```


