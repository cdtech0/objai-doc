# 对象识别服务
1. 服务是用golang开发的，使用darknet框架，程序小，占用资源少，安装简单。
2. 通过对图片进行局部处理增强识别结果，可支持80m左右的物体识别（720P)，没优化时大约支持30m左右,并且室外环境下的效果比较差。
3. 可根据摄像图片的摄像头角度和时间优化
4. 可配套拍照服务[getimg](https://github.com/cdtech0/getimg-doc)来使用
## 特性说明
1. 通过配置文件由用户根据自已的模型和GPU数量进行按需配置
2. 支持置信度过滤，只有达到某个置信度的物体才认可
3. 支持电子围栏，可按物体的面积占比对识别结果进行过滤
4. 支持将识别结果另存为文件，文件有三个（原图，识别图，识别结果）
5. 支持打洞（将某些识别错误的区域加入黑名单）进行过滤
6. 安装后直接通过测试页面进行测试查看识别结果
### 性能说明

|主机配置|显卡|模型数|压测请求数|正常模式|增强模式|
|--------|--------|:----:|:----:|-----:|-----:|
| i5-8600+8M内存| Gtx1650(4G)|1个yolov4|10个并发|100ms/张|240ms/张|
| i5-8600+8M内存| Gtx1660(6G)|2个yolov4|20个并发|95ms/张|240ms/张|
| E5-2620(双路)+64M内存| Gtx1080 Ti|4个yolov4|50个并发|90ms/张|200ms/张|

**以上测试数据来自压力测试(1080p)
## 使用说明
1. 见[api.md](https://github.com/cdtech0/objai-doc/blob/main/api.md)

