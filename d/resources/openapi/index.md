# WebAPI 接口


* 天气接口
    * 气象局接口:
        `http://m.weather.com.cn/data/101010100.html`
* 音乐接口
    * 虾米接口
        `http://kuang.xiami.com/app/nineteen/search/key/歌曲名称/diandian/1/page/歌曲当前页?_=当前毫秒&callback=getXiamiData`
    * QQ空间收藏音乐接口
        `http://qzone-music.qq.com/fcg-bin/fcg_music_fav_getinfo.fcg?dirinfo=0&dirid=1&uin=QQ号&p=0.519638272547262&g_tk=1284234856`
* IP接口
    * 新浪接口(ip值为空的时候 获取本地的)
        `http://int.dpool.sina.com.cn/iplookup/iplookup.php?format=json&ip=218.4.255.255`
    * 淘宝接口
        `http://ip.taobao.com/service/getIpInfo.php?ip=63.223.108.42`
* 手机信息查询接口
    * 淘宝网接口
        `http://tcc.taobao.com/cc/json/mobile_tel_segment.htm?tel=手机号`
    * 拍拍接口
        `http://virtual.paipai.com/extinfo/GetMobileProductInfo?mobile=手机号&amount=10000&callname=getPhoneNumInfoExtCallback`
    * 百付宝接口
        `https://www.baifubao.com/callback?cmd=1059&callback=phone&phone=手机号`
    * 115接口
        `http://cz.115.com/?ct=index&ac=get_mobile_local&callback=jsonp1333962541001&mobile=手机号`
    * 有道接口
        `http://www.youdao.com/smartresult-xml/search.s?jsFlag=true&type=mobile&q=手机号`
* 视频信息接口
    * 优酷
        `http://v.youku.com/player/getPlayList/VideoIDS/视频ID (比如 http://v.youku.com/v_show/id_XNTQxNzc4ODg0.html的ID就是XNTQxNzc4ODg0)`
* 翻译、词典接口
    * 腾讯
        `http://dict.qq.com/dict?q=词语`

## 视频接口

其它[视频接口](video.md)
