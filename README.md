## 简介
Timeline是一个视频监控播放控制进度条插件,代码主要参考[liaoanran/timeline-canvas](https://github.com/liaoanran/timeline-canvas),因源代码命名习惯及接口较为不方便使用,故重新写了一遍并上传分享.插件类似海康视频管理平台提供的时间轴,支持显示事件区间,滚轮放大缩小,拖动.本人也是菜鸟,欢迎提issue..

### init
`new Timeline(canvasId, initTime, timeParts, isMove, timeChangeCallback)`
其中,除了`canvasId`为必传项, 其他均可不传;默认值及 含义如下
- `canvasId` timeline容器, canvas元素id
- `initTime` Date.now() 初始默认事件
- `timeParts` [] 事件区间
- `isMove` false 初始状态时间轴是否在移动
- `timeChangeCallback` 空函数 当时间轴被**拖动**时的回调函数,参数为拖动后的时间

## API
- `setCurrentTime` 重新设置当前时间,不改变当前播放状态
- `setTimeParts` 重新设置事件区间,会覆盖当前事件区间
- `addTimeParts` 添加事件区间,不会覆盖当前事件区间
- `setIsMove` 设置当前播放状态
- `setChangeCallback` 设置拖动时间轴后的回调函数
- `getCurrentTime` 获取时间轴当前时间
- `destroy` 销毁 主要是用于组件销毁时,取消计数器