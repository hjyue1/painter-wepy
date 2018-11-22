## 小程序生成图片库[Painter]的Wepy版本
### 安装
```bash
    npm install painter-wepy --save
```
```bash
    import painter from 'painter-wepy'
```
### 例子
```bash

<script>
    <template lang="wxml" minapp="wepy">
        <painter :palette.sync="palette" @imgOK.user="onImgOK" />
    </template>
</script>

import wepy from 'wepy';
import painter from 'painter-wepy'

export default class Index extends wepy.page {
    components = {
        painter,
    };
    data = {
        palette: {
            {
                width: '654rpx',
                height: '1000rpx',
                background: '#eee',
                views: [
                        {
                        type: 'text',
                        text: 'borderWidth',
                        css: {
                            bottom: '40rpx',
                            right: '200rpx',
                            color: 'green',
                            borderWidth: '2rpx',
                        }
                    }
                ]
            }
        }
    }
    methods = {
        onImgOK(e) {
            wepy.hideLoading();
            this.imgUrl = e.path
            this.$apply();
        }
    }
}
```


[Painter]: https://github.com/Kujiale-Mobile/Painter