# Lantern
为你的前端网页挂上灯笼
## 一、前言

除夕夜，在门前挂上灯笼有鸿（红）运当头的吉祥寓意，逢年过节挂的灯笼上，基本都是吉祥的图案和祝福的吉祥话。而灯笼的正红色是朱砂的颜色，而朱砂是风水上讲去邪挡煞效力极强的宝物，所以自古逢年过节，就有在大门上挂红色灯笼的传统。

## 二、效果展示

### 局部效果

![5.gif](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/559d09b8e8b34361bceefe084a3e7550~tplv-k3u1fbpfcp-watermark.image?)

### 全局效果

![6.gif](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/02d23dbb441a4ae5b5c16cc5ac52d1c9~tplv-k3u1fbpfcp-watermark.image?)

## 三、代码讲解

### 确定位置

我们平常挂灯笼一般是挂在大门的两侧，所以我们把灯笼的位置确定在网页的左侧和右侧，平时讲究好事成双，所以网页两侧的灯笼要对称，距离适中。

右侧的灯笼位置：

    .spring_lantern__deng-box {
    position: fixed;//固定位置
    top: -20px;//最顶端
    right: -20px;//右侧
    z-index: 99999;
    }

左侧的灯笼位置：

    .spring_lantern__deng-box1 {
     position: fixed;//固定位置
     top: -10px;//顶端
     left: 10px;//左侧灯笼
     z-index: 99999;
    }

### 绘制灯笼

灯笼文字，为了喜庆，改成福字。

文字样式const word = '福福'

    .spring_lantern__deng-t {
     font-family: 华文行楷,华文楷体,Arial,Lucida Grande,Tahoma,sans-serif;
     font-size: 53px !important;
     color: ${colors.suiLight};
     font-weight: bold;
     line-height: 85px;
     text-align: center;
     user-select:none;
    }


灯笼颜色样式：

    const colors = {
        suiLight: '#dc8f03',
        suiDark: '#ffa500',
        deng_box_shadow: 'rgba(250, 108, 0, 1)',
        r1: 'rgba(216, 0, 15, 0.8)',
        r2: 'rgba(216, 0, 15, 0.1)',

附加一个清明恶搞灯笼，

    喜迎清明，黑白分明
      const colors = {
        suiLight: '#ffffff',
        suiDark: '#9b9b9a',
        deng_box_shadow: 'rgb(74,74,74)',
        r1: 'rgba(16, 16, 16, 80%)',
        r2: 'rgba(16, 16, 16, 10%)',
      }


​      

### 动态效果

核心代码：

        if (isDown) {//如果灯笼在摇摆的过程中下降
          _spring_lantern_LightUpFlag = false
          box.style.display = 'block'
          box1.style.display = 'block'
        }
        if (isUp) {//如果灯笼在摇摆的过程中上升
          _spring_lantern_LightUpFlag = true
          box.style.display = 'none'
          box1.style.display = 'none'
        }
      }
