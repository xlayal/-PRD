# 智能博物馆PRD
## 一、价值主张设计
### 1、加值宣言
#### 在信息迅速发展的背景下，人们对文化的需求程度日益加深，越来越多的人走进博物馆。然而大型博物馆存在的结构复杂、客流量大、门票进出需要登记等问题。因此, 博物馆可以通过增加一些技术性设备，以AI人工智能技术加持。基于现状，我们计划通过人流量统计API、人脸识别API对博物馆的导览系统进行优化。
##### 优先级：基于区域人流量统计技术模型，运用百度AI中的人流量统计功能，通过照片或者视频上传对区域人流量进行统计并且反馈回人流量数据结果。
##### 次优先：运用人脸对比API，对需要再次进入博物馆的游客进行人脸识别，通过反馈识别结果，开启进馆通道。

### 2、核心价值（展品列表、地图标注功能、人流量统计功能）
#### 本产品着眼于优化博物馆的游客管理系统，解决用户对博物馆游览的基本需求以及协助博物馆的工作人员进行人流量统计。

### 3、核心价值与用户痛点
* 便捷性
##### 博物馆可以以此减少人工的支出，也为游客提供了更加便捷的通道，减少了游客需要在馆外排队候场的时间。
* 易管理性
##### 博物馆可以通过人流量统计和人脸识别更加系统地管理游客流量，也可以在某区域人数超过人数限定值的时候，让馆内工作人员进行人流量疏通。

### 4、需求列表与人工智能API加值
|  用户需求  | API接口  | 重要程度  |
|  ----  | ----  | ----  |
| 馆内工作人员统计每日进馆人流量| 人流量监控API | 重要 |
| 游客再次进入馆内 | 人脸对比API | 次重要  |

##### 具体应用场景
1、学生小明今天去博物馆游览，在使用门票进入场内时，使用了人脸识别进入了博物馆内，游览到一半，他想出馆外吃个午餐回来继续观看展览，当他吃完返回来时，在博物挂进馆通道进行人脸对比，人脸匹配成功，成功进入馆内继续观展。

2、博物馆的工作人员老王想知道博物馆内的进馆游客数据统计，他通过智能博物馆的数据统计，能看到关于今日博物馆的各个展厅提供独立的参观者出入数据。

3、还是老王，当区域人数超过一定数值时，系统会自动发出警报实现“浪涌人流超标告警”，帮助馆工作人员及时实行疏散策略，适当引导人流，实现错峰入馆，提升参观体验。保障潜在的参观者聚集区域，长期处于安全通畅的环境中。

### 5、人工智能概率性与用户痛点 
* #### 百度AI人流量识别功能的保障：
##### 1、算法领先，高精度头肩检测算法，准确率90%以上，静态人数统计不限人数，适应各种人群密集场所。
##### 2、服务稳定，可提供企业级稳定、精确的大流量服务，拥有毫秒级识别响应能力及99.9%的可靠性保障。
#### **据此，该产品人流量识别功能准确率有保障，通常不会出现与实际数据偏差太大的情况，但是由于此功能以外的因素（如网络延迟或者卡顿无法使视频图像被正确识别）会导致数据输出延迟或者不准确，此概率事件可以通过改进得到缓解，对用户的负面影响不会过大。**
* #### 百度AI中的通用物体和场景识别技术有三大产品优势：
##### 1、准确性高，基于百度海量数据，利用深度学习技术及高精度算法不断迭代模型，准确率业界领先。
##### 2、标签体系丰富，可识别出10万+物体及场景标签，并在不断丰富中，持续提供更精细的识别服务。
##### 3、简单易用，支持标准化接口封装，调用简单，只需上传单张图片，即可获取识别结果。
#### **因此，该APP用户通过拍照上传，使用了通用物体和场景识别照片中的物体返回大类及细分类的名称结果。此功能技术准确率较高，普遍情况下返回结果比较精准。但由于一些环境因素（如光线太暗）或者照片原因（如照片不清晰、识别主体精确等）造成返回识别结果不准确的状况，这些事件为小概率事件，对用户体验的负面影响不会压过正面影响的机率。**

## 二、产品设计原型
### 1、交互及界面设计
![人流量系统](https://upload-images.jianshu.io/upload_images/9412832-8c3032c684d4215f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 2、信息设计
![信息设计](https://upload-images.jianshu.io/upload_images/9412832-2628790d77891216.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 3、Axure原型文档 [博物馆Axure原型](https://gitee.com/xlayal/museum)

## 三、API 产品使用及输出展示（人流量监控）
### 1、API展示说明及输出 
* 人流量统计识别（使用百度API）
* 人脸与人体识别——人流量统计API
* 接口描述：统计图像中的人体个数和流动趋势，以头肩为主要识别目标统计人数，无需正脸、全身照，适应人群密集、各种出入口场景。 摄像头硬件选型无特殊要求，分辨率建议720p以上，更低分辨率的图片也能识别，只是效果可能有差异。暂不适用夜间红外监控图片，后续会考虑扩展。（需和各艺术馆协商提供实时监控视频图像，此API示例以某博物馆人流图为例）
* 接口地址: 百度AI人体分析之人流量统计API
* 请求方式：POST
* 请求URL： https://aip.baidubce.com/rest/2.0/image-classify/v1/body_num
* 输入代码示例

```
Python代码示例

# encoding:utf-8

import requests
import base64

'''
人流量统计
'''

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/body_num"
# 二进制方式打开图片文件
f = open('human.jpg', 'rb')  #上传人流量图像
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '[此处输入你获取到的token]'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
* 输出示例
```
{'person_num': 14, 'log_id': 8386600918089470214}  #识别图像中的人流量数字结果
```

## 价值主张练习
* **1句话版本**
#### 我们致力于为博物馆提供更方便快捷的游客管理系统，协助博物馆的工作人员对人流量进行系统管理和提高游客体验。

* **1分钟版本**
#### 本智能博物馆产品着眼于优化博物馆的游客管理系统，通过人流量检测，与博物馆内的监控以及检票系统相连接，让馆内工作人员可以直观看到馆内人流量统计，更好管理人员流动，在某区域人流量超过上限时可以及时进行疏导，保证游客的游览体验；通过人脸对比api的技术，游客再次进入馆内时可使用人脸对比检测进去馆内，减少了用户需要排队或者纸质票易丢失的可能性，大大提高了服务效率和游客体验。通过以上最小可行性的服务，帮助智慧场馆的建设以及升级文明旅游与智慧旅游的体验。
                
