



![](https://github.com/liangtongdev/WxWeather/blob/master/propaganda.png)

####  天气预报

微信小程序之练手项目，天气接口使用阿里云平台 https://market.aliyun.com/ 天气接口

![](https://github.com/liangtongdev/WxWeather/blob/master/screenshot.png)

#### [流程](https://developers.weixin.qq.com/miniprogram/dev/framework/structure.html)


##### 申请AppID

 + 邮箱（一个邮箱只能注册一个小程序AppID）
    + 未注册过公众平台
    + 未注册过开放平台
    + 未注册过企业号
    + 未绑定个人号

 + 类型
    + 个人
    + 企业
      + 需要300RMB认证费用
      + 权限更大，比如可以获取用户手机号
    + 政府
    + 媒体
    + 其他

 + 认证
    + 个人类型账号不支持微信认证
    + 认证成功后可申请微信支付权限

 + 公众号关联小程序
    + 所有公众号均可关联
    + 一个公众号可以关联10个同主体的小程序，3个不同主体的小程序
    + 一个小程序可以关联500个公众号
    + 公众号一个月内可新增关联小程序13次
    + 小程序一个月可新增关联500次

##### 限制

 + https域名
    + https://developers.weixin.qq.com/miniprogram/dev/api/api-network.html
 + 手机号
    + https://developers.weixin.qq.com/miniprogram/dev/api/getPhoneNumber.html?search-key=%E6%89%8B%E6%9C%BA%E5%8F%B7


##### 文件格式

 + .json 配置文件
    + app.json 全局配置
      + https://developers.weixin.qq.com/miniprogram/dev/framework/config.html
      + 页面路径：pages字符串数组，表示[路径+文件名]，不需要写后缀
        + 数组第一项表示初始页面
        + 页面需要与pages字段对应
      + 窗口表现：window
        + 导航栏颜色，标题，样式
        + 背景、窗口、刷新等
      + 底部Tabbar：tabBar
        + 文字，背景、边框颜色
        + position：top/bottom
        + tab列表
          + 数组，包含[2,5]个对象
          + pagePath：页面路径，必须在pages中先定义
          + text：按钮上的文字
          + iconPath：图标，大小限制40kb，尺寸81px， 不支持网络图标
          + selectedIconPath：选中图标
      + 网络超时时间：networkTimeout
      + 是否开启Debug模式：debug

    + page.json 页面配置
      + 定制化页面UI时，会用到，比如特定页面的导航栏颜色，标题等

    + project.config.json 工具配置

 + .wxml 模板文件
    + https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxml/index.html
    + 标签
    + 数据绑定
    + 渲染
    + 模板
    + 事件

 + .wxss 样式文件
    + https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html
    + app.wxss 全局样式
    + page.wxss 局部样式
    + 单位：rpx，不用考虑设备宽度与像素比
    + 仅支持部分CSS选择器
    + 使用
      + 样式导入：@import 相对路径;
      + 内联样式
          + style：动态样式，运行时解析，速度慢
          + class：静态样式，样式类名之间用空格隔开
          + 选择器


 + .js 脚本逻辑文件
    + https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxml/event.html
    + 事件绑定
      + 写法同组件的属性，以key.value的形式
      + key以bind或者catch开头
          + 多种事件，例如bindtap ， bind:tap
          + bind事件不会阻止事件向上冒泡
          + catch事件绑定可以阻止事件向上冒泡
      + dataset
      + detail携带数据


##### 服务通知

 + 消息模版（可以自定义）
 + 接口调用

##### 注意点
 + 分包加载时
    + 单个分包/主包2M限制，提交代码时工具会检查
    + 整个小程序所有分包大小不得超过8M

