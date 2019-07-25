# baidu-aip-sdk  https://ai.baidu.com/sdk
### 在开发laravel项目时，需要用到baidu云的sdk，顺手拿过来稍微调整了下

##目录
```
AipBase.php 基类
AipBCEUtil.php 工具类
AipHttpClient.php 请求类
---------------------
AipBodyAnalysis.php 人体关键点识别
AipContentCensor.php 内容识别
AipFace.php 人脸识别
AipImageCensor.php 黄反识别
AipImageClassify.php 图片识别类别
AipImageProcess.php 图片处理
AipImageSearch.php 图片搜索
AipKg.php	任务
AipNlp.php 语言处理
AipOcr.php OCR识别
AipSpeech.php 语音识别
````
##安装
```
composer require baidu-sdk/aip

```

##用法
###具体文档请参照 http://ai.baidu.com/docs
```
以OCR为例

namespace App\Helpers;

use Baidu\Aip\AipOcr;//引入相应的模块

class OCR
{

    protected $appId='';//APP_ID
    protected $apiKey='';//API_KEY
    protected $secretKey='';//SECRET_KEY

    public function build(){
        $client = new AipOcr($this->appId, $this->apiKey, $this->secretKey);
        $image = file_get_contents('./wepay.jpg');
        $result=$client->basicGeneral($image);
        print_r($result);
        
    }
}

```
