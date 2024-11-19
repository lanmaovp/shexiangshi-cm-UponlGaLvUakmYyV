
HarmonyOS 5\.0\.1 Beta3，是HarmonyOS开发套件基于API 13正式发布的首个Beta版本。该版本在OS能力上主要增强了C API的相关能力，多个特性补充了C API供开发者使用。


## OS平台能力增加


首先是系统能力增加了，这次增加了很多C接口能力，像我们用得比较多的场景有：Ability组件中元能力新增C API，可以从ApplicationContext中获取cache路径、Area以及bundleName的能力；ArkData组件中，Preferences可能在C API中使用了，但是不支持C API与ArkTS API混合使用；AVSession媒体播控模块可以在C中进行播放、暂停、停止、快进、快退等等；后台任务中像短时任务也增加C接口；Image组件支持通过C API从PixelMap中读取ARGB格式的数据。还有其它很多模块都对C的能力进行的增加，这次更新，算是全面提升了C接口的能力。


除了C能力的提升，其它一些常用的功能也有增强。像RichEditor支持配置滚动条的显隐；Web组件支持获取资源响应数据和响应数据的准备状态，以及获取网页当前的滚动偏移量；后台任务新增音视频通话长时任务；Map组件支持设置地图经纬度范围和4个方向与边界之间的距离；在默认界面扫码界面，支持用户点击关闭“隐私横幅”。当重新打开应用的默认界面扫码将只显示安全访问提示，3s后消失；新增了新增数字人民币的接口。


PhotoViewPicker能力有5项增强：


* PickerOptions新增是否支持滑动多选的选项和设置大图页checkbox的位置的选项
* 新增向picker发送退出大图的通知的API
* 新增设置大图页大图预览组件外其他UI元素是否可见的API
* 新增定义大图页大图预览组件外其他UI元素的API
* 支持PhotoPicker组件的删除通知等相关能力


新增加了NearLink Kit（星闪服务），星闪服务提供一种低功耗、高速率的短距离通信服务，支持星闪设备之间的连接、数据交互。中心设备可以通过扫描发现外围设备，并发起连接。外围设备可以通过发送广播的方式被中心设备发现，和中心设备连接之后可以进行相应的数据传输。


## DevEco Studio特性增加


hvigor新增getOverrides、setOverrides和setProperty能力。这对于多环境处理三方依赖将非常方便。在之前的版本中，我们要区分不同的环境去依赖不同的包，必须在各自模块下自己替换依赖库，不能很好的做到统一处理，像静态har模块中可能处理起来更麻烦了。现在有了getOverrides和setOverrides接口，我们可以统一在项目根目录下的hvigor.ts中直接判断不同的环境进行依赖了，这简直是太方便了。


在最新的DevEco Studio中，我们可以直接在IDE内上传应用软件包。在DevEco Studio菜单栏，点击Build \> Upload Product，点击Sign in登录华为开发者账号。
![img1](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20241112100958.17602805648809250329023956527387:50001231000000:2800:599E8FB1EE2AC20F7BC4872316AFD582FF360C0616B99B4446457509DBCE99C7.png)
登录成功后，返回DevEco Studio进入软件包上传界面。确认当前工程的product信息，选择需要上传的软件包类型，点击OK开始上传。


* 若当前上传的软件包仅做测试发布，请选择Generate app package and upload it to AppGallery Connect for test
* 若软件包需要在全网正式发布，请选择Generate app package and upload it to AppGallery Connect for test and publish


![img2](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20241112100958.77415939811003593473448375007997:50001231000000:2800:408217BC19D7AF09C5EAC195193490E81A45426660E3C12D7D44BFEC75673F8F.png?needInitFileName=true)
上传完成后，出现云测试的结果，点击Full results on App Gallary Connect可进入AGC查看软件包上传记录和检测结果。


Launch分析支持手动冷启动场景。启动模式分为自动启动和手动启动，可点击图标切换两种不同模式：


* 若选择自动启动模式，当用户使用Launch模板并开始录制时，将主动重启所选应用；
* 手动启动模式在开始录制时，只会主动终止所选应用，等待界面出现弹窗提示启动应用后，开发者需要手动启动应用。


### 新增的特性


* DevEco Studio支持开发API 13工程
* DevEco Profiler Frame模板新增Lost Frames和Hitch Time泳道，用于识别和优化卡顿和丢帧现象
* hvigor\-config.json5中properties下新增ohos.arkCompile.noEmitJs字段，用于指定ArkTS编译过程中是否生成js中间产物，不生成js中间产物可以降低编译过程的峰值内存，加快编译速度。
* 新增支持HWASan检测
* 应用与服务体检新增一条快速性能检测规则：避免序列化反序列化耗时长
* ohpm新增支持resolve\_conflict\_strict严格模式依赖冲突处理功能


### 增强的特性


* 意图框架新增支持多种垂域类型
* DevEco Profiler工具录制提供可视化配置
* hvigorw命令行工具支持\-\-max\-old\-space\-size参数，用于设置守护进程内存大小
* AppAnalyzer检测报告支持与Profiler工具使用时间戳联动，点击时间戳可以打开Profiler并定位到问题发生的时间点


 本博客参考[豆荚加速器](https://baitenghuo.com) 。转载请注明出处！
