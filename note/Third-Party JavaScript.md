# 第三方JavaScript编程

## 1. 第三方JavaScript简介
### 1.1 第三方JavaScript的定义
### 1.2 第三方JavaScript的用法
#### 1.2.1 嵌入式微件
#### 1.2.2 分析和统计
#### 1.2.3 Web服务API封装
### 1.3 开发一个简单的微件
#### 1.3.1 服务端生成脚本
#### 1.3.2 通过iframe分发微件
### 1.4 第三方开发的挑战
#### 1.4.1 未知的上下文
#### 1.4.2 共享环境
#### 1.4.3 浏览器限制
### 1.5 总结

## 2. 应用的分法和加载
### 2.1 配置第三方开发环境
#### 2.1.1 发布者的测试页面
#### 2.1.2 Web服务器
#### 2.1.3 模拟多个域
### 2.2 加载初始的脚本
#### 2.2.1 阻塞式脚本引入
#### 2.2.2 使用async和defer无阻塞加载脚本
#### 2.2.3 动态脚本插入
### 2.3 初始脚本文件
#### 2.3.1 window和undefined混淆
#### 2.3.2 基本应用程序流程
### 2.4 加载额外的文件
#### 2.4.1 JavaScript文件
#### 2.4.2 库
### 2.5 脚本参数传递
#### 2.5.1 使用查询字符串
#### 2.5.2 使用片段标识符
#### 2.5.3 使用自定义数据属性
#### 2.5.4 使用全局变量
### 2.6 获取应用数据
### 2.7 总结

## 3. HTML和CSS的渲染
### 3.1 输出HTML
#### 3.1.1 使用document.write
#### 3.1.2 追加到已知位置
#### 3.1.3 追加多个微件
#### 3.1.4 解耦渲染对象
### 3.2 为你的HTML添加样式
#### 3.2.1 使用内联样式
#### 3.2.2 加载CSS文件
#### 3.2.3 嵌入CSS到JavaScript中
### 3.3 防御性的HTML和CSS
#### 3.3.1 命名空间
#### 3.3.2 CSS的特殊性
#### 3.3.3 过度设置CSS的特殊性
### 3.4 将内容嵌入到iframe中
#### 3.4.1 没有设置src的iframe
#### 3.4.2 外部iframe
#### 3.4.3 样式继承
#### 3.4.4 何时避免使用iframe
### 3.5 小结

## 4. 与服务器通信
### 4.1 AJAX和浏览器的同源策略
#### 4.1.1 判定同源的规则
#### 4.1.2 同源策略和脚本加载
### 4.2 带填充的JSON（JSONP）
#### 4.2.1 通过脚本元素加载JSON
#### 4.2.2 动态的回调函数
#### 4.2.3 局限性和安全问题
### 4.3 子域名代理
#### 4.3.1 使用document.domain更改文档的源
#### 4.3.2 使用子域代理实现跨域通信
#### 4.3.3 子域名代理与JSONP相结合
#### 4.3.4 IE和子域代理
#### 4.3.5 安全隐患
### 4.4 跨域资源共享
#### 4.4.1 发送简单的HTTP请求
#### 4.4.2 使用CORS传输Cookie
#### 4.4.3 发送预检请求
#### 4.4.4 浏览器支持
### 4.5 总结

## 5. 跨域iframe通信
### 5.1 HTML5 window.postMessage API
#### 5.1.1 使用window.postMessage发送信息
#### 5.1.2 接收发送给窗口的消息
#### 5.1.3 浏览器的支持
### 5.2 降级
#### 5.2.1 使用window.name发送消息
#### 5.2.2 使用URL片段标识符发送消息
#### 5.2.3 使用Flash发送消息
### 5.3 使用easyXDM简化跨域消息通信
#### 5.3.1 加载并初始化easyXDM
#### 5.3.2 使用easyXDM.Socket发送简单信息
#### 5.3.3 使用easyXDM.Rpc定义JSON-RPC接口
### 5.4 总结

## 6. 验证和会话
### 6.1 第三方Cookie
#### 6.1.1 Session的设置和读取
#### 6.1.2 禁用第三方Cookie
#### 6.1.3 IE和P3P头
#### 检测cookies是否可用
### 6.2 设置第三方Cookie
#### 6.2.1 使用独立窗口
#### 6.2.2 iframe的解决方案（只针对Safari）
#### 6.2.3 Chrome和Firefox中的单页面回话
### 6.3 会话安全
#### 6.3.1 HTTPS和更安全的cookie
#### 6.3.2 多级身份认证
### 6.4 总结

## 7. 安全性
### 7.1 Cookies，会话和会话的窃取
### 7.2 跨站脚本
#### 7.2.1 XSS攻击
#### 7.2.2 CSS中的XSS漏洞
#### 7.2.3 防止XSS对应用的攻击
### 7.3 跨站请求伪造
#### 7.3.1 XSRF攻击
#### 7.3.2 JSON劫持
#### 7.3.3 保护应用免受XSRF攻击
### 7.4 发布者漏洞
#### 7.4.1 发布者模拟
#### 7.4.2 点击劫持
#### 7.4.3 拒绝服务
### 7.5 总结

## 8. 独特的框架
### 8.1 实现一个最基本的SDK
#### 8.1.1 初始化
#### 8.1.2 异步加载
#### 8.1.3 暴露公共方法
#### 8.1.4 事件监听器
### 8.2 版本管理
#### 8.2.1 URL版本管理
#### 8.2.2 通过初始化进行版本控制
### 8.3 封装Web服务的APIs
#### 8.3.1 在客户端访问Web服务APIs
#### 8.3.2 封装Camera Stork API
#### 8.3.3 识别发布者
#### 8.3.4 用户授权和OAuth
### 8.4 总结

## 9. 性能
### 9.1 优化负荷
#### 9.1.1 合并和压缩源代码
#### 9.1.2 减少图像请求
#### 9.1.3 缓存文件
#### 9.1.4 推迟HTTP请求
### 9.2 JavaScript优化
#### 9.2.1 浏览器内部：UI线程、重绘和回流
#### 9.2.2 控制耗性能的调用：throttle和debounce函数
#### 9.2.3 使用setTimeout延迟计算
### 9.3 被感知的性能
#### 9.3.1 对用户的操作保持乐观
#### 9.3.2 在文档就绪之前渲染
### 9.4 总结

## 10. 调试和测试
### 10.1 调试
#### 10.1.1 在生产环境中使用开发环境的代码
#### 10.1.2 单步执行代码
### 10.2 测试
#### 10.2.1 单元测试、集成测试和回归测试
#### 10.2.2 使用QUnit编写回归测试
#### 10.2.3 使用Hiro写回归测试
### 10.3 总结