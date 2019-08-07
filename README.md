#   知乎助手 with TS

##  项目说明

**知乎助手** 由 [姚泽源](http://www.yaozeyuan.online/) 创作，采用 [MIT](http://opensource.org/licenses/MIT) 协议进行许可。

*   项目基于知乎现有接口+TypeScript构建，为知友提供方便的, 以供自己阅读/自身结集整理为目的的, 将知乎内容转为Epub电子书的途径

##  使用说明

1.  下载[软件安装包(Windows版)](https://pan.baidu.com/s/1vn-96AlHPKsggSzemVKiEg), 双击安装
2.  在`任务输入框`中输入待抓取的网址信息
3.  点击`开始执行`按钮
4.  执行完毕后会打开电子书所在文件夹, 使用**多看阅读**或双击使用Edge浏览器打开均可
5.  输出文件
    1.  `知乎助手输出的电子书\epub`内, 为输出的Epub电子书, 可以直接使用电子书阅读器阅读
    2.  `知乎助手输出的电子书\html`内, 为输出的网页版答案列表
        1.   `html`文件夹中为按回答分割的单个回答页面列表, `index.html`为目录页
        2.   `单文件版`文件夹中为整个文件, 可以使用浏览器打开后, 直接打印为PDF书籍
6.  使用示例 =>
![使用说明](http://ww1.sinaimg.cn/large/6671cfa8ly1g095scec8hj20uy0pfaau.jpg)

#   注意事项

1.  在生成电子书时可能会有卡顿, 根据电子书的体积(100k~2G)卡顿时间在1s~1分钟不等, 函请谅解
2.  所有图片缓存都会存在安装目录下, 随着制作的电子书数量增加, 体积可能会非常大, 因此建议将软件安装在非系统盘根目录, 体积大了直接删除即可

##  知乎助手支持收集的网址类型

| 网址类型                          | 描述                                                                                             | 示例                                                                                                                                                                              |
| --------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 指定知乎用户赞同过的全部回答&文章 | 用户个人主页地址 + `/activities/`                                                                | `http://www.zhihu.com/people/yyln2016/activities/`,<br /> `http://www.zhihu.com/people/ying-ye-78/activities/`,<br />`http://www.zhihu.com/people/bo-cai-28-7/activities/` <br /> |
| 指定知乎用户的全部回答            | 用户个人主页地址                                                                                 | `http://www.zhihu.com/people/yyln2016`,<br /> `http://www.zhihu.com/people/ying-ye-78/answers`,<br />`http://www.zhihu.com/people/bo-cai-28-7/logs` <br />                        |
| 话题                              | 知乎话题地址，<br />保存话题信息和话题精华中的答案                                               | `http://www.zhihu.com/topic/20024374`,<br /> `http://www.zhihu.com/topic/20024374/top-answers`,<br />`http://www.zhihu.com/topic/20024374` <br />                                 |
| 公开收藏夹                        | 知乎公开收藏夹地址，<br />保存收藏夹信息和收藏夹内的答案                                         | `http://www.zhihu.com/collection/19555617`,<br /> `http://www.zhihu.com/collection/19731344`,<br /> `http://www.zhihu.com/collection/133027089`<br />                             |
| 私人收藏夹                        | 知乎私人收藏夹地址，<br />保存收藏夹信息和收藏夹内的答案，<br />需要创建者用自己的ID登陆知乎助手 | `同正常收藏夹`                                                                                                                                                                    |
| 专栏                              | 专栏的网址                                                                                       | `http://zhuanlan.zhihu.com/yyln2016`, <br />`http://zhuanlan.zhihu.com/FrontendPerusal`,<br /> `http://zhuanlan.zhihu.com/patisserie`<br />                                       |

#   目标分解
1.  基础功能
    - [x]    抓取用户回答
    - [x]    导出用户回答
    - [x]    抓取收藏夹
    - [x]    导出收藏夹
    - [x]    抓取话题精华回答
    - [x]    导出话题精华回答
    - [ ]    自定义抓取问题/回答/文章列表
    - [x]    抓取专栏文章
    - [x]    导出专栏文章
    - [x]    抓取用户行为记录
    - [x]    导出用户点赞的所有文章/回答
    - [x]    使用基础命令, 派发进程
2.  扩展功能
    - [x]    导出为单页HTML
    - [x]    导出为epub
    - [ ]    支持通过配置, 按赞同数/创建时间 正序/倒序 导出文章/答案
    - [x]    添加升级检测, 从服务器获取cookie
    - [x]    添加图形界面, 利用Electron创建图形界面/登陆知乎/生成命令配置
    - [x]    利用Electron根据命令启动配置
    - [x]    在Electron展示后端运行日志
    - [ ]    获取问题/回答/文章时, 统一使用标准的answer/article接口进行获取, 保证数据结构一致性(需要了解知乎接口相关参数原理)
    - [x]    能够自动读取上一次生成的配置文件, 而不是每次都需要重新输入
    - [ ]    能够按照赞同/答案长度等指标过滤答案
    - [ ]    开始运行时在前端界面自动检测升级, 并给与提示
    - [ ]    导出文件时, 支持自定义配置(电子书名/封面/作者/etc)
3.  todo
    - [x]    将type声明改为使用namespace形式进行声明
    - [x]    将view改为使用类继承方式进行实现
    - [x]    输出目录结构
    - [x]    当用户回答为空时, 需要跳过渲染环节
    - [x]    解决GUI下看不到运行日志的问题
    - [x]    解决GUI版本无法生成epub文件
    - [x]    解决GUI版本无法将生成结果从缓存文件夹中复制到输出文件夹中的问题
    - [x]    为电子书添加封面
    - [x]    解决Edge浏览器下用户头像过大问题
    - [x]    解决目录列表页显示有空行的问题
    - [x]    解决多看电子书结尾处右下角会换行的问题
    - [x]    添加一个tab, 作为使用说明
    - [x]    运行日志刷新频率过高会导致页面卡死, 定时刷新需要延长执行时间
    - [x]    展示日志应该限制总高度, 每次刷新后应自动滚动到最下方
    - [x]    把demo调的正规一点
    - [ ]    话题支持输出文章&回答(话题列表中同时有回答&文章, 目前为了赶进度, 只渲染的文章)
    - [ ]    支持分卷(每1000个问题分为一本电子书, 避免文件体积过大)
    - [ ]    调整回答右下角日期格式, 现在分成了三块, 不好看
    - [ ]    支持配置项中的功能
      - [ ]  答案排序
        - [ ]  创建时间
        - [ ]  更新时间
        - [ ]  赞同数
        - [ ]  评论数
          - [ ]  由高到低
          - [ ]  有新到旧
      - [ ]  图片质量
        - [ ]  高清
        - [ ]  原图
        - [ ]  无图
      - [ ]  自动分卷
        - [ ]  1000
    - [ ]    只有抓取全部记录才是高频率的抓取, 因此可以设定抓取范围, 按时间范围, 避免频繁抓取
    - [ ]    优化页面样式
    - [ ]    启动时检查是否有权限/用户是否被封禁
    - [ ]    如果用户被封禁, 暂停任务, 提示用户重新登陆
4.  fixed bug list
    - [x]    输出图片的时候, 本应该替换src属性, 但是替换成了data-default-watermark-src属性
    - [x]    致谢列表溢出了背景颜色区域
5.  二期规划
    1.  项目目标
        1.  制作电子书, 方便自己阅读
            1.  而不是制作电子书, 以对外发布
            2.  不需要商业化
            3.  因此不需要复杂的排版功能
            4.  关键在于, 是否方便
        2.  需要
            1.  收集功能
            2.  简单自定义内容
    2.  电子书制作模式
        1.  基础模式
            1.  选择数据源
                1.  问题/答案/收藏夹/话题/想法/专栏/文章/用户回答/用户提问过的问题/用户关注过的问题/用户赞同过的回答&文章/用户想法
            2.  确认输出模式
                1.  排序模式
                    1.  正序/倒序
                    2.  问题与文章
                        1.  赞同数
                        2.  评论数
                        3.  答案/文章创建时间
                        4.  答案/文章最后更新时间
                        5.  收藏时间-可选
                    3.  想法
                        1.  发布时间
                        2.  赞同数
                        3.  评论数
                        4.  转发数
                    4.  用户故事
                        1.  支持按照赞同时间顺序
                            1.  正序/倒序
                    5.  用户关注过的问题
                        1.  支持按照关注时间顺序
                            1.  正序/倒序
                    6.  问题列表/混排模式
                        1.  支持按照原始设定顺序
                        2.  答案视为一个问题
                        3.  文章也视为一个问题
                        4.  按以下进行排序
                            1.  总答案赞同数
                            2.  问题关注人数
                            3.  问题浏览数
                            4.  问题创建时间
                            5.  问题最后编辑时间
                    7.  单纯收藏夹
                        1.  支持按收藏时间排序
                2.  过滤条件
                    1.  正序/倒序
                        1.  问题与文章
                            1.  赞同数
                            2.  评论数
                            3.  答案/文章创建时间
                            4.  答案/文章最后更新时间
                        2.  想法
                            1.  发布时间
                            2.  赞同数
                            3.  评论数
                            4.  转发数
                    2.  前n条/前百分之n
                    3.  至少m条
                    4.  至多y条
                3.  图片配置
                    1.  原图
                    2.  默认
                    3.  无图
                    4.  自定义逻辑
                        1.  按最小宽高(或/且)
                            1.  宽大于指定值 => 使用原图
                            2.  高大于指定值 => 使用原图
            3.  输出单位
                1.  如果是简单类型(话题/专栏/用户回答/用户问题/用户想法/收藏夹/单个问题), 单独输出一本电子书, 允许自定义书名
                2.  如果是复杂类型(两种及以上类型混合), 按问题/文章/想法三大类聚合输出, 不支持分章节
            4.  存储单位
                1.  基本单位
                    1.  回答
                    2.  文章
                    3.  想法
                2.  id统一使用varchar(100)
                3.  使用基本接口进行查询
                4.  其余数据使用这两者进行构建, 例如, 关注问题列表的记录为
                    1.  关注问题列表
                        1.  问题下回答列表
    - [ ]    支持自定义
      - [ ]    电子书
        - [ ]    书名
        - [ ]    封面图片
        - [ ]    作者
        - [ ]    相关可配置属性
      - [ ]    电子书集合
        - [ ]    统一叫自定义电子书
        - [ ]    回答
        - [ ]    问题
        - [ ]    专栏
        - [ ]    文章
        - [ ]    想法
    - [ ]    支持抓取
      - [ ]    想法
      - [ ]    回答
      - [ ]    问题
      - [ ]    用户关注过的问题下的回答
    - [ ]  组织模式
      - [ ]  按问题组织
      - [ ]  对外的最小粒度应该是问题/文章/想法
      - [ ]  想法单条展示
        - [ ]  想法下
          - [ ]  图片 => 直接展示
          - [ ]  文章/回答 => 抓取内容进行渲染
          - [ ]  问题 => 抓取答案进行渲染, 默认只渲染按赞同数排名的前20条
    

#   代码规范
1.  变量命名规范
    1.  类型统一使用namespace方式声明, 导入时使用`Type + xxx`形式进行导入
    2.  Model导入时统一使用`M + xxx`形式进行导入
    3.  View导入时统一使用`View + xxx`形式进行导入
    4.  Util工具函数导入时统一使用`xxx + Util`形式进行导入
    5.  async函数前统一添加`async`前缀, 以和正常函数进行区分
2.  文件命名规范
    1.  统一使用下划线方式命名

#   开发说明

1.  建议只开发命令版
    1.  使用`npm run ace`启动
2.  GUI版需要为Electron编译sqlite3, 非常麻烦, 不建议尝试
    1.  编译指南: https://www.cnblogs.com/DonaHero/p/9809325.html
    2.  流程
        1.  Windows用户
            1.  安装[VS 2015社区版](http://download.microsoft.com/download/B/4/8/B4870509-05CB-447C-878F-2F80E4CB464C/vs2015.com_chs.iso), 是的你没看错
            2.  文件-新建项目-Visual C++ -> 选择 安装vs2015所需的C++开发环境
            3.  好了一个小时过去了
            6.  执行 `npm run rebuild-electron-with-sqlite3`, 编译完成sqlite3之后, 就可以启动GUI界面了
        2.  Mac用户
            1.  我没有mac谢谢
    3.  注意:
        1.  打包时会向dist目录中复制一份node_modules目录, 导致npm run 时优先从dist中获取node_module信息, 导致无法启动
            1.  因此, 打包结束后需要将dist里的node_modules目录删掉, 以免影响后续开发工作
3.  电子书封面分辨率为: 100 * 130(宽*高)
4.  commit信息规范 => 
    | 关键字 | 功能          |
    | ------ | ------------- |
    | feat   | 添加新功能    |
    | format | 调整代码格式  |
    | fix    | 修复错误      |
    | doc    | 修订文档/注释 |

#   开发指南

##  基本思路

1.  TypeScript提供类型支持, 在编写代码时可以自动提示变量下的属性 
2.  Electron提供图形界面, 利用webview标签直接登陆知乎
3.  利用知乎接口抓取数据
4.  ace/command提供命令行支持
5.  sqlite3提供数据库支持

##  实现方式
1.  将电子书制作分为以下三步
    1.  初始化环境 => 对应于`npm run ace Init:Env`命令
    2.  抓取指定内容 => 对应于`npm run ace Fetch:XXX`系列命令, 目前支持`Column`/`Author`/`Activity`/`Collection`/`Topic`
    3.  从数据库中获得数据, 生成指定内容电子书 => 对应于`npm run ace Generate:XXX`系列命令, 目前支持`Column`/`Author`/`Activity`/`Collection`/`Topic`
    4.  因此, 实际任务流程就是根据用户输入url, 生成对应命令配置, 不断执行命令即可
2.  项目开发流程
    1.  `npm run watch` 启动监控, 将`ts`自动编译为`js`文件
    2.  `npm run startgui`, 启动前端界面(vue项目, 基于Element-UI简单构建)
    3.  修改`src/index.ts`, 将代码由
        ```js
        // 线上地址
        mainWindow.loadFile('./gui/dist/index.html')
        // 本地调试 & 打开控制台
        // mainWindow.loadURL('http://127.0.0.1:8080')
        // mainWindow.webContents.openDevTools()
        ```
        替换为
        ```js
        // 线上地址
        // mainWindow.loadFile('./gui/dist/index.html')
        // 本地调试 & 打开控制台
        mainWindow.loadURL('http://127.0.0.1:8080')
        mainWindow.webContents.openDevTools()
        ```
        使用本地页面进行调试
    4.  执行`npm run start`, 启动Electron
        1.  前端点击`开始任务`按钮后, 将任务配置写入`task_config_list.json`, 再由Electron收集登陆后产生的知乎cookie, 存入`config.json`文件中, 随后启动`Dispatch:Command`命令, 开始执行任务
3.  注意事项
    1.  Electron需要编译sqlite3后才能启动, 不容易搞, 建议直接使用`npm run ace`命令行方式进行调试
    2.  命令使用说明详见代码


#   功能建议

欢迎通过[issue](https://github.com/YaoZeyuan/zhihuhelp_with_node/issues)提建议

#   支持作者

![感谢支持](http://ww1.sinaimg.cn/large/6671cfa8ly1g08k8rm5grj20ri16sq4r.jpg)

[致谢列表](https://www.easy-mock.com/mock/5c680a151b1cdb683581355c/zhihuhelp/thank_you/list)
