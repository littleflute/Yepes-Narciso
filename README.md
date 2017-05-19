



<!DOCTYPE>
<html>
<head>
<meta charset="utf-8">
<title>musicPlayer</title> 
<style type="text/css">
/*Ã¥Ë†ÂÃ¥Â§â€¹Ã¥Å’â€“*/
body, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, p, blockquote, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }
ul, ol { list-style:outside none; }
fieldset, img { border:0; }
table { border-collapse:collapse; border-spacing:0; }
body, small, sup, sub, button, input, textarea, select { font:12px/1 Arial, Helvetica, Verdana, SimSun, sans-serif; }
body { line-height:1.5; }
h1, h2, h3, h4, h5, h6 { font-size:100%; }
address, cite, dfn, em, var { font-style:normal; }
code, kbd, pre, samp { font-family:Consolas, "Lucida Console", Courier, SimSun, monospace; }
sup, sub { position:relative; vertical-align:baseline; }
sup { top:-3px; }
sub { bottom:-3px; }
button { padding:5px 10px; overflow:visible; }
.clearfix:after{ content:"."; display:block; height:0; clear:both; visibility:hidden; }
.clearfix{ display:inline-block; }
* html .clearfix{ height:1%; }
.clearfix{ display:block; }

/*Ã¦â€™Â­Ã¦â€Â¾Ã¥â„¢Â¨Ã¦Â¡â€ Ã¦Å¾Â¶*/
.hidden{ display:none; }
.m-player-wrap{ position:fixed; left:-550px; bottom:20px; z-index:1; width:570px; height:96px; color:#828282; font:normal 12px/1.5 Arial,Helvetica,Tahoma,"Ã¥Â®â€¹Ã¤Â½â€œ",sans-serif; }
.m-player-wrap .m-player{ float:left; padding:10px; width:530px; height:76px; background:#000; box-shadow: 3px 3px 6px RGBA(0,0,0,.42); }
.m-player-wrap .m-player-switch{ float:left; padding:38px 0 0 5px; width:15px; height:58px; background:#383838; border-radius:0 6px 6px 0; cursor:pointer; -webkit-transition-duration:300ms; -moz-transition-duration:300ms; box-shadow:3px 3px 6px RGBA(0,0,0,.42); }
.switch-on,
.switch-off,
.play-lists,
.album-lists,
.lyrics,
.favorites,
.m-play,
.m-pause,
.m-next,
.m-prev,
.broadcast-control-l,
.broadcast-control-r,
.volume,
.mute,
.list-cycle,
.single-cycle,
.shuffle-play,
.order-play,
.close-list,
.add-favorites,
.play-icon,
.speaker{ background:url(https://littleflute.github.io/blMp3Player/images/player_img.png); }

/*Ã¦â€™Â­Ã¦â€Â¾Ã¥â„¢Â¨Ã¥Â¼â‚¬Ã¥â€¦Â³*/
.m-player-switch:hover{ background:#4b4b4b; }
.switch-off,
.switch-on{ display:block; width:9px; height:18px; }
.switch-off{ background-position:-120px 0; }
.switch-on{ background-position:-132px 0; }

/*Ã¦â€™Â­Ã¦â€Â¾Ã¦Â­Å’Ã¦â€ºÂ²Ã¤Â¿Â¡Ã¦ÂÂ¯*/
.m-info{ float:left; position:relative; width:200px; }
.m-info .album-front-cover{ float:left; width:75px; height:75px; overflow:hidden; }
.m-info .front-cover-mask{ position:absolute; left:0; width:75px; height:75px; background:url(https://littleflute.github.io/blMp3Player/images/album_cover_mask.png) no-repeat; cursor:pointer; -webkit-transition-duration:300ms; -moz-transition-duration:300ms; }
.m-info .front-cover-mask:hover{ opacity:0.5; }
.m-info .info-wrap{ padding:0 5px; width:115px; overflow:hidden; cursor:default; }
.m-info .info-wrap dt{ color:#fff; }
.m-info .info-wrap dt,
.m-info .info-wrap dd{ width:120px; height:18px; overflow:hidden;}
.m-info .m-function{ padding-top:8px; }
.album-lists,
.lyrics,
.favorites{ float:left; margin-right:7px; width:15px; height:12px; cursor:pointer; }
.album-lists{ background-position:-16px 0; }
.lyrics{ background-position:-58px 0; }
.favorites{ background-position:-79px 0; }
.album-lists:hover,
.album-lists-hover{ background-position:-16px -18px; }
.lyrics:hover,
.lyrics-hover{ background-position:-58px -18px; }
.favorites:hover,
.favorites-hover{ background-position:-79px -18px; }

/*Ã¦Å½Â§Ã¥Ë†Â¶Ã©ÂÂ¢Ã¦ÂÂ¿*/
.broadcast-control{ float:left; width:330px; height:75px; }
.broadcast-control .broadcast-control-l,
.broadcast-control .broadcast-control-r{ float:left; width:5px; height:75px; }
.broadcast-control .broadcast-control-l{ background-position:0 0; }
.broadcast-control .broadcast-control-r{ background-position:-5px 0; }
.broadcast-control .broadcast-control-m{ float:left; position:relative; width:320px; height:75px; background:url(https://littleflute.github.io/blMp3Player/images/control_panel_bg.png) repeat-x; }
.m-next,
.m-prev{ position:absolute; top:23px; width:21px; height:22px; cursor:pointer; }
.m-next{ left:197px; background-position:-28px -80px; }
.m-next:hover{ background-position:-28px -102px; }
.m-prev{ left:101px; background-position:0 -80px; }
.m-prev:hover{ background-position:0 -102px; }
.m-play{ position:absolute; top:15px; left:147px; width:27px; height:38px; background-position:-152px -81px; cursor:pointer; }
.m-play:hover{ background-position:-124px -81px; }
.m-pause{ position:absolute; top:18px; left:148px; width:22px; height:34px; background-position:-85px -86px; cursor:pointer; }
.m-pause:hover{ background-position:-63px -86px; }

/*Ã¨Â¿â€ºÃ¥ÂºÂ¦Ã¦ÂÂ¡*/
.play-progress-rate{ position:absolute; top:63px; width:320px; height:10px; }
.play-progress-rate .progress-rate-bg{ position:absolute; top:0; left:27px; width:260px; height:5px; overflow:hidden; background:-webkit-gradient(linear,0 0,0 100%,from(#9c9d8b),to(#c0c2ae)); background:-moz-linear-gradient(center top , #9c9d8b, #c0c2ae); border:1px solid #898b7c; border-radius:6px; cursor:pointer; }
.play-progress-rate .progress-rate-bg .progress-rate-color{ height:5px; background:-webkit-gradient(linear,0 0,0 100%,from(#8e9082),to(#4d4f42)); background:-moz-linear-gradient(center top , #8e9082, #4d4f42); background-color:#7b7d6f\9; border-radius:2px; }
.play-progress-rate .play-time,
.play-progress-rate .surplus-time{ position:absolute; top:-2px; height:10px; line-height:10px; overflow:hidden; font-size:10px; color:#65675a; -webkit-text-size-adjust:none; }
.play-progress-rate .play-time{ left:0; width:26px; text-align:right; }
.play-progress-rate .surplus-time{ left:291px; width:29px; text-align:left; }

/*Ã©Å¸Â³Ã©â€¡Â*/
.volume-wrap,
.play-manner-wrap{ position:absolute; top:-51px; z-index:1000; width:26px; height:75px; background:#6a6e5b; border-radius:4px; }
.volume-wrap{ left:0; }
.volume,
.mute{ position:absolute; left:6px; top:56px; width:17px; height:14px; cursor:pointer; -webkit-transition-duration:200ms; -moz-transition-duration:200ms; }
.volume{ background-position:-16px -36px; }
.mute{ background-position:-35px -36px; }
.volume-active{ background-position:-16px -56px; }
.mute-active{ background-position:-35px -56px; }
.volume-active,
.mute-active{ opacity:1; }
.now-volume{ top:5px; }
.volume-wrap .volume-size-bg{ position:absolute; left:11px; top:4px; width:4px; height:48px; background:#ebeede; border-radius:2px; cursor:pointer; }
.volume-wrap .volume-size-bg .volume-size-color{ height:48px; background:#3c3d37; }

/*Ã¦â€™Â­Ã¦â€Â¾Ã¦â€“Â¹Ã¥Â¼Â*/
.play-manner-wrap{ padding:5px 4px; width:18px; height:65px; }
.list-cycle,
.single-cycle,
.shuffle-play,
.order-play{ display:block; margin-bottom:3px; width:18px; height:14px; opacity:0.8; cursor:pointer; }
.list-cycle{ background-position:-57px -36px; }
.list-cycle-active{ background-position:-57px -56px; }
.single-cycle{  background-position:-105px -36px; }
.single-cycle-active{ background-position:-105px -56px; }
.order-play{  background-position:-81px -36px; }
.order-play-active{ background-position:-81px -56px; }
.shuffle-play{  background-position:-129px -36px; }
.shuffle-play-active{ background-position:-129px -56px; }
.list-cycle-active,
.single-cycle-active,
.order-play-active,
.shuffle-play-active{ opacity:1; }
.now-manner{ position:absolute; right:5px; top:5px; }
.play-manner-wrap{ left:294px; }
.list-cycle:hover,
.single-cycle:hover,
.order-play:hover,
.shuffle-play:hover{ opacity:1; }

/*Ã¦â€™Â­Ã¦â€Â¾Ã¥Ë†â€”Ã¨Â¡Â¨*/
.music-list{ position:fixed; bottom:116px; width:550px; height:470px; overflow:hidden; color:#999; }
.music-list .list-title{ position:relative; padding:0 15px; height:50px; line-height:50px; background:#000; }
.music-list .list-title strong{ margin-right:13px; font:normal 18px "Microsoft Yahei"; color:#fff; }
.music-list .list-title .cutover-list{ cursor:pointer; }
.music-list .list-title .cutover-list:hover{ color:#fff; }
.music-list .list-title .close-list{ display:block; position:absolute; right:5px; top:10px; width:10px; height:20px; background-position:-151px 0; opacity:0.8; cursor:pointer; }
.music-list .list-title .close-list:hover{ opacity:1; }
.music-list .song{ padding:1px 0; height:420px; background:#1b1b1b; }
.music-list .song li{ position:relative; padding:0 15px; margin-bottom:1px; height:24px; line-height:24px; cursor:pointer; }
.music-list .song li:hover{ background:#000; color:#ccc; }
.music-list .song .s-name,
.music-list .song .s-album,
.music-list .song .s-time{ display:inline-block; overflow:hidden; text-align:left; }
.music-list .song .s-name{ width:300px; }
.music-list .song .s-album{ width:183px; }
.music-list .song .s-time{ width:30px; text-align:right; }
.music-list .song .add-favorites{ position:absolute; right:22px; top:5px; width:15px; height:12px; background-position:-79px 0; }
.music-list .song .add-favorites:hover{ background-position:-79px -18px; }
.music-list .song .playIng{ color:#fff; }
.music-list .album{ padding:13px 6px 13px 13px; height:394px; background:#1b1b1b; }
.music-list .album li{ float:left; position:relative; margin-right:15px; width:160px; height:205px; text-align:center; }
.music-list .album li .album-cover{ margin-bottom:10px; width:160px; height:160px; overflow:hidden; box-shadow:2px 4px 6px #0a0a0a; cursor:pointer; }
.music-list .album li .album-name{ display:inline-block; padding:1px 10px; max-width:139px; height:18px; overflow:hidden; background:#101010; border-radius:10px; text-align:center; color:#979797; }
.music-list .album .album-cover-hover{ position:absolute; top:0; left:0; width:158px; height:158px; border:1px solid #fff; cursor:pointer; }
.music-list .album .album-cover-hover .album-song-num{ display:block; position:absolute; right:7px; top:7px; width:16px; height:16px; background:#000; border-radius:16px; color:#fff; font-size:10px; text-align:center; line-height:16px; -webkit-text-size-adjust:none; }
.music-list .album .album-cover-hover .play-btn{ position:absolute; top:135px; left:42px; width:78px; height:20px; line-height:20px; line-height:21px\9; background:#000; border-radius:10px; opacity:0.8; color:#fff; }
.music-list .album .album-cover-hover .play-icon{ float:right; width:12px; height:12px; background-position:-171px -1px; margin:4px 5px 0 -2px; }
.music-list .album .album-cover-hover .mask{ position:absolute; top:0; left:0; width:158px; height:158px; background:#000; opacity:0.2; }
.music-list .album .playIng .speaker{ display:inline-block; margin-right:4px; width:10px; height:10px; background-position:-172px -19px; }

/*Ã¦Â­Å’Ã¨Â¯Â*/
.lrc-wrap{ position:absolute; right:-251px; padding-top:2px; width:250px; height:94px; overflow:hidden; background:#1B1B1B; border-radius:4px; box-shadow: 3px 3px 6px RGBA(0,0,0,.42); }
.lrc-wrap .lrc-box .no-lrc,
.lrc-wrap .load-lrc{ height:94px; line-height:94px; text-align:center; }
.lrc-wrap .lrc-box p{ display:block; height:30px; line-height:30px; text-align:center; color:#ccc; font-size:12px; }
.lrc-wrap .lrc-box .color{ color:#9ae40a; }
.mr15{ margin-right:15px; }

.page-info { padding:8px 15px; background:#fcea9e; border-bottom:1px solid #b6bac0; font:normal 16px Georgia; }
.page-info h1 { float:left; }
.page-info a { font-weight:bold; color:#222; }
.return-article { float:right; }
.return-article h2{ display:inline; }
.main{ padding:20px; height:1000px; color:#444; }
.wrap{ float:right; padding:15px; background:#FFFFE1; border:1px solid paleGoldenrod; border-radius:4px; }
.f-list{ padding:20px 0; line-height:36px; font-size:14px; font-weight:bold; }
.f-list a{ margin:0 5px 0 0; padding:0 10px 0 0; background:url(http://www.feelcss.com/wp-content/themes/fengchao/images/external_link.png) no-repeat scroll right top transparent; color:#006600; text-decoration:none; }
.f-list a:hover{ text-decoration:underline; }
cite{ display:block; }
</style>
</head>
<body>
<div class="page-info clearfix">
  <h1>
    <a href="https://github.com/littleflute/blMp3Player/images/edit/master/index.html" target="_blank">v0.0.6</a>
    <a href="https://github.com/littleflute/blMp3Player/images" title="回到 PrjPage 首页">PrjPage</a> 
    <a href="https://littleflute.github.io/blog">blog</a>
  </h1>
</div>
  <div id="xddbg" style="border:1px red solid;width:100px;height:30px;"></div>
  
<div class="main">
  <div class="wrap">
    <cite>*推荐浏览器: chrome & firefox | 作者: fengchao</cite>
    <cite>*音频文件: MP3</cite>
    <ul class="f-list">
      <li><a href="http://www.feelcss.com/html5-music-player-design.html" title="设计" target="_blank">1.设计</a></li>
      <li><a href="http://www.feelcss.com/html5-music-player-basic-control.html" title="基本的控制（播放，暂停，上一曲，下一曲）" target="_blank">2.基本的控制（播放，暂停，上一曲，下一曲）</a></li>
      <li><a href="http://www.feelcss.com/html5-music-player-progress-time-volume.html" title="播放进度，时间显示以及音量的调节" target="_blank">3.播放进度，时间显示以及音量的调节</a></li>
     <li><a href="http://www.feelcss.com/html5-music-player-playlist-and-playback.html" title="播放列表与播放方式（列表循环，单曲循环，随机播放，顺序播放）" target="_blank">4.播放列表与播放方式（列表循环，单曲循环，随机播放，顺序播放）</a></li>
      <li><a href="http://www.feelcss.com/html5-music-player-synchronous-display-lyrics.html" title="同步显示歌词" target="_blank">5.同步显示歌词</a></li>
    </ul>
    <p>xd test
    </p>
  </div>
</div>
  


<!--播放器开始 { -->
<div id="musicPlayerWrap" class="m-player-wrap">
  <div id="musicPlayer" class="m-player">
    <div id="musicInfo" class="m-info">
      <img src="images/index.jpg" alt="" id="albumFrontCover" class="album-front-cover">
      <div class="front-cover-mask" title=""></div>
      <div id="infoWrap" class="info-wrap">
        <dl>
          <dt id="musicName" title="FeelPlayer">FeelPlayer</dt>
          <dd id="musicSinger" title="播放最爱的音乐">播放最爱的音乐</dd>
          <dd id="albumName" title=""></dd>
        </dl>

        <div id="musicFunction" class="m-function clearfix">
          <a href="javascript:void(0);" id="albumLists" class="album-lists" title="打开专辑列表"></a>
          <a href="javascript:void(0);" id="lyrics" class="lyrics" title="打开歌词"></a>
          <!-- <a href="javascript:void(0);" id="favorites" class="favorites" title="打开收藏夹"></a> -->
        </div>
      </div>
    </div>
    <div id="broadcastControl" class="broadcast-control clearfix">
      <div class="broadcast-control-l"></div>
      <div class="broadcast-control-m">
        <a href="javascript:void(0);" id="play" class="m-play" title="播放"></a>
        <a href="javascript:void(0);" id="pause" class="m-pause hidden" title="暂停"></a>
        <a href="javascript:void(0);" id="next" class="m-next" title="下一曲"></a>
        <a href="javascript:void(0);" id="prev" class="m-prev" title="上一曲"></a>

        <div class="play-progress-rate">
          <span id="playTime" class="play-time">0:00</span>
          <div id="progressRateBg" class="progress-rate-bg">
            <div id="progressRateColor" class="progress-rate-color" style="width:0;"></div>
          </div>
          <span id="surplusTime" class="surplus-time">-0:00</span>
        </div>

        <a href="javascript:void(0);" id="nowVolume" class="volume volume-active now-volume"></a>
        <a href="javascript:void(0);" id="nowMute" class="mute mute-active now-volume hidden"></a>
        <a href="javascript:void(0);" id="nowPlayManner" class="now-manner list-cycle list-cycle-active" title="列表循环"></a>

        <div id="volumeControl" class="volume-wrap hidden">
          <a href="javascript:void(0);" id="volume" class="volume" title="点击设为静音"></a>
          <a href="javascript:void(0);" id="mute" class="mute hidden" title="点击开启声音"></a>
          <div id="volumeSizeBg" class="volume-size-bg" title="音量调节">
            <div id="volumeSizeColor" class="volume-size-color" data-volume="" data-height="" style="height:0;"></div>
          </div>
        </div>

        <div id="playMannerControl" class="play-manner-wrap hidden">
          <a href="javascript:void(0);" id="orderPlay" class="order-play" title="顺序播放"></a>
          <a href="javascript:void(0);" id="shufflePlay" class="shuffle-play" title="随机播放"></a>
          <a href="javascript:void(0);" id="singleCycle" class="single-cycle" title="单曲循环"></a>
          <a href="javascript:void(0);" id="listCycle" class="list-cycle" title="列表循环"></a>
        </div>

      </div>
      <div class="broadcast-control-r"></div>
    </div>
  </div>
  <div id="musicPlayerSwitch" class="m-player-switch on" title="打开播放器">
    <a href="javascript:void(0);" id="playerSwitchBtn" class="switch-on"></a>
  </div>

  <div id="lrcWrap" class="lrc-wrap hidden">
    <div id="loadLrc" class="load-lrc hidden">歌曲载入中...</div>
    <div id="lrcBox" class="lrc-box"></div>
  </div>
</div>


<!--播放器结束 } -->
</body>
</html>
<script>
var QueryString = function () {
  // This function is anonymous, is executed immediately and 
  // the return value is assigned to QueryString!
  var query_string = {};
  var query = window.location.search.substring(1);
  var vars = query.split("&");
  for (var i=0;i<vars.length;i++) {
    var pair = vars[i].split("=");
        // If first entry with this name
    if (typeof query_string[pair[0]] === "undefined") {
      query_string[pair[0]] = decodeURIComponent(pair[1]);
        // If second entry with this name
    } else if (typeof query_string[pair[0]] === "string") {
      var arr = [ query_string[pair[0]],decodeURIComponent(pair[1]) ];
      query_string[pair[0]] = arr;
        // If third or later entry with this name
    } else {
      query_string[pair[0]].push(decodeURIComponent(pair[1]));
    }
  } 
  return query_string;
}();

var url = null;
if(QueryString.l)
{
	url = "https://littleflute.github.io/" + QueryString.l + "/l.json";
}
else
{
	url = "https://littleflute.github.io/blMp3Player/images/songList.json";
	url = "https://littleflute.github.io/Elton-John/l.json"; 
}    
(function(){
	XMLHttpData(url);
})();




var xddbg = document.getElementById("xddbg");

var s = xddbg.innerHTML;
 s += "xddbg1: ";
 s += QueryString.l + "<br>";
 s += url + "<br>";
 xddbg.innerHTML = s;


//---------------------------------------------------【AJAX载入歌曲信息】
function XMLHttpData(url){
    var xmlhttp,song;

    loadXMLDoc(url);

    function loadXMLDoc(url){
        xmlhttp = null;
        if(window.XMLHttpRequest){
            xmlhttp = new XMLHttpRequest();
        }
        //IE5,6
        else if(window.ActiveXObject){
            xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
        }
        if(xmlhttp != null){
            xmlhttp.onreadystatechange = getXMLHttpData;
            xmlhttp.open("get", url, true);
            xmlhttp.send(null);
        }else{
            alert("您的浏览器不支持 XMLHTTP");
        }
    }

    function getXMLHttpData(){
        if(xmlhttp.readyState === 4){
            if(xmlhttp.status === 0 || xmlhttp.status === 200){
                song = eval("(" + xmlhttp.responseText + ")");
                //发送歌曲的信息
                formatPlayer(song);
            }else{
                alert("XMLHTTP error，请刷新浏览器");
            }
        }
    }
}

//---------------------------------------------------【播放器初始化 绑定事件】
function formatPlayer(song){
    var mEngine = new MUSICENGINE(song),
        mPlay = document.getElementById("musicEngine"),
        mPlayerSwitch = document.getElementById("musicPlayerSwitch"),
        play = document.getElementById("play"),
        pause = document.getElementById("pause"),
        next = document.getElementById("next"),
        prev = document.getElementById("prev"),
        nowVolume = document.getElementById("nowVolume"),
        nowMute = document.getElementById("nowMute"),
        volume = document.getElementById("volume"),
        mute = document.getElementById("mute"),
        volumeSizeBg = document.getElementById("volumeSizeBg"),
        progressRateBg = document.getElementById("progressRateBg"),
        lyrics = document.getElementById("lyrics"),
        albumLists = document.getElementById("albumLists");

    //打开关闭
    mPlayerSwitch.onclick = function(){
        musicPlayerSwitch();
    };
    //播放
    play.onclick = function(){
        mEngine.toPlay("play");
    };
    //暂停
    pause.onclick = function(){
        mEngine.toPlay("pause");
    };
    //下一曲
    next.onclick = function(){
        if(mPlay.src != ""){
            mEngine.next();
        }
    };
    //上一曲
    prev.onclick = function(){
        if(mPlay.src != ""){
            mEngine.prev();
        }
    };
    //静音开关
    nowVolume.onclick = function(){
        mEngine.volume("on");
    };
    nowMute.onclick = function(){
        mEngine.volume("off");
    };
    volume.onclick = function(){
        mEngine.volume("on");
    };
    mute.onclick = function(){
        mEngine.volume("off");
    };
    //音量控制杆
    volumeSizeBg.onclick = function(event){
        var realVolume = VolumeChangeProcess(event);
        mEngine.volumeControlStrip(realVolume);
    };
    //歌曲进度调节
    progressRateBg.onclick = function(event){
        if(mPlay.src != ""){
            var activeProgress = getSongProgress(event);
            mEngine.songProgressAdjust(activeProgress);
        }else{
            return false;
        }
    };
    //专辑列表
    albumLists.onclick = function(){
        mEngine.albumLists();
    };
    //事件冒泡，处理临时加入的元素事件
    document.getElementsByTagName("body")[0].onclick = function(event){
        var o = event ? event : window.event;

        //关闭列表
        if(o.target.id === "closeList"){
            closeList();
            return false;
        }

        //返回列表，全部歌曲列表
        if(o.target.id === "cutoverList"){
            if(o.target.innerHTML === "返回"){
                //先关闭列表 然后点击专辑列表按钮实现跳转
                document.getElementById("albumLists").click();
                //在专辑列表中，多点击一下，实现关闭再打开
                document.getElementById("albumLists").click();
                mEngine.formatAlbumLists();
                return false;
            }
            if(o.target.innerHTML === "专辑列表"){
                //先关闭列表 然后点击专辑列表按钮实现跳转
                document.getElementById("albumLists").click();
                mEngine.formatAlbumLists();
                return false;
            }
            if(o.target.innerHTML === "查看全部歌曲"){
                mEngine.formatAllSongLists();
                return false;
            }
        }

        //点击播放歌曲并生成播放列表
        if(o.target.parentNode){
            if(o.target.parentNode.className === "s-l"){
                //计算点击的歌曲&专辑引索
                var musicIndex = mEngine.muiscIndexAndAlbumIndex(o.target.parentNode);
                //生成引索，根据引索值播放歌曲
                mEngine.playIndex(musicIndex.albumIndex,musicIndex.songIndex);
                //突出当前播放歌曲
                currentlyPlayingSong();
                return false;
            }
        }

        //一键播放专辑列表
        if(o.target.className === "play-btn"){
            o.target.parentNode.parentNode.ondblclick();
            document.getElementById("listWrap").childNodes[0].childNodes[0].click();
            return false;
        }
        if(o.target.className === "play-icon"){
            o.target.parentNode.parentNode.parentNode.ondblclick();
            document.getElementById("listWrap").childNodes[0].childNodes[0].click();
            return false;
        }
    };

    //歌词打开关闭
    lyrics.onclick = function(){
        lrcBoxSwitch();
    };

///////////////////////////////////////
    //显示专辑列表
    albumLists.click();
    lyrics.click();
    mPlayerSwitch.click();
///////////////////////////////////////
}

/**
 * 基本播放功能（播放，暂停，上一曲，下一曲）
 */

//---------------------------------------------------【构造函数 MUSICENGINE】
function MUSICENGINE(song){
    //创建播放器
    var musicEngine = document.createElement("audio");
    musicEngine.id = "musicEngine";
    document.getElementById("musicPlayerWrap").appendChild(musicEngine);
    //获取歌曲
    this.song = song;
    //获取播放器
    this.musicPlayer = document.getElementById("musicEngine");
    //载入完成
    this.musicPlayer.addEventListener("canplaythrough",function(){
        //歌词
        hide(document.getElementById("loadLrc"));
    });
}

//---------------------------------------------------【功能：播放&暂停】
MUSICENGINE.prototype.toPlay = function(toPlay){
    var play = document.getElementById("play"),
        pause = document.getElementById("pause");

    //播放第一首
    if(this.musicPlayer.src === ""){
        this.playIndex(0,0);
    }
    //如果媒体文件被暂停，则返回true
    if(toPlay === "play"){
        this.musicPlayer.play();
        this.playbackProgress("play");
        hide(play);
        show(pause);
    }
    if(toPlay === "pause"){
        this.musicPlayer.pause();
        this.playbackProgress("pause");
        show(play);
        hide(pause);
    }
};

//---------------------------------------------------【功能：下一曲】
MUSICENGINE.prototype.next = function(){
    //获取歌曲的播放方式
    var mode = document.getElementById("nowPlayManner").title;
    //发送给songPlayMode()方法，让它处理如何播放下一首
    this.songPlayMode("next",mode);
};

//---------------------------------------------------【功能：上一曲】
MUSICENGINE.prototype.prev = function(){
    //获取歌曲的播放方式
    var mode = document.getElementById("nowPlayManner").title;
    //发送给songPlayMode()方法，让它处理如何播放下一首
    this.songPlayMode("prev",mode);
};

/**
 * 音量控制
 */

//---------------------------------------------------【功能：静音切换】
MUSICENGINE.prototype.volume = function(muteSwitch){
    var volumeSizeColor = document.getElementById("volumeSizeColor"),
        volumeSizeSave = parseInt(volumeSizeColor.style.height);

    //设为静音
    if(muteSwitch === "on"){
        //记录静音前的音量大小
        volumeSizeColor.attributes["data-volume"].nodeValue = this.musicPlayer.volume;
        //记录静音前的元素高度
        volumeSizeColor.attributes["data-height"].nodeValue = volumeSizeSave;
        this.musicPlayer.volume = 0.0;
        //音量图标切换 - 打开静音
        volumeIconSwitch("on");
        //音量控件的音量条变化(100为元素高度)
        volumeSize(100);
    }
    //取消静音
    if(muteSwitch === "off"){
        this.musicPlayer.volume = volumeSizeColor.attributes["data-volume"].nodeValue;
        //音量图标切换 - 关闭静音
        volumeIconSwitch("off");
        //音量控件的音量条变化
        volumeSize(volumeSizeColor.attributes["data-height"].nodeValue);
    }
};

//---------------------------------------------------【功能：音量控制条】
MUSICENGINE.prototype.volumeControlStrip = function(realVolume){
    this.musicPlayer.volume = realVolume;
    if(realVolume > 0){
        //音量图标切换 - 关闭静音
        volumeIconSwitch("off");
    }else{
        //音量图标切换 - 打开静音
        volumeIconSwitch("on");
    }
};

//---------------------------------------------------【音量变化过程】
function VolumeChangeProcess(event){
    var volumeSizeBg = document.getElementById("volumeSizeBg"),
        progressBP,
        realVolume;

    //获得距相对元素距离的百分比
    var coord = coordinate(event),
        offsetCoord_Y = coord.coord_Y;
    //音量杆动画变化
    progressBP = progressBarPercentage(48,offsetCoord_Y);
    volumeSize(progressBP);
    //真实的音量数值0.0~1.0
    realVolume = parseInt((100 - progressBP) / 10) / 10;
    return realVolume;
}

//---------------------------------------------------【音量的图标切换】
function volumeIconSwitch(muteSwitch){
    var nowVolume = document.getElementById("nowVolume"),
        nowMute = document.getElementById("nowMute"),
        volume = document.getElementById("volume"),
        mute = document.getElementById("mute"),
        volumeSizeColor = document.getElementById("volumeSizeColor");
    //打开静音
    if(muteSwitch === "on"){
        //静音的显示图标变化
        hide(nowVolume);
        show(nowMute);
        //音量控件的图标变化
        hide(volume);
        show(mute);
        //音量为0时，让音量杆也为0，优化视觉
        volumeSizeColor.style.height = "100%";
    }
    //关闭静音
    if(muteSwitch === "off"){
        //静音的显示图标变化
        hide(nowMute);
        show(nowVolume);
        //音量控件的图标变化
        hide(mute);
        show(volume);
    }
}

//---------------------------------------------------【音量控件的音量条变化】
function volumeSize(size){
    var volumeSizeColor = document.getElementById("volumeSizeColor");
    volumeSizeColor.style.height = size + "%";
}

//---------------------------------------------------【音量控件显示&隐藏，大小调节】
(function(){
    var nowVolume = document.getElementById("nowVolume"),
        nowMute = document.getElementById("nowMute"),
        volumeControl = document.getElementById("volumeControl");

    //音量控件显示&隐藏
    nowVolume.onmouseover = function(){
        show(volumeControl);
    };
    nowMute.onmouseover = function(){
        show(volumeControl);
    };
    //解决onmouseout事件遇到子元素时，也触发onmouseout的BUG
    volumeControl.onmouseout = function(event){
        var Event = event || window.event;
        if(Event){
        	if(volumeControl.contains(Event.relatedTarget||Event.toElement)){
                //如果是子元素，结束函数
        		return false;
        	 }else{
                //触发的事件
                hide(volumeControl);
            }
        }
    };
})();

/**
 * 歌曲播放进度，播放时间
 */

//---------------------------------------------------【功能：播放进度，播放时间】
MUSICENGINE.prototype.playbackProgress = function(playSwitch){
    var progressRateColor = document.getElementById("progressRateColor"),
        songSchedule = 0,
        timeall,
        currenttime,
        timer;

    if(playSwitch === "play"){
        timer = setInterval(function(){
            var mPlayer = document.getElementById("musicEngine");
            //获取歌曲总时间
            timeall = timeAll();
            //获取歌曲当前播放时间
            currenttime = currentTime();
            //计算歌词滚动
            lrcMove(timeall,currenttime);
            //计算歌曲播放时间
            songPlaybackTime(timeall,currenttime);
            //计算进度条宽度并赋值
            songSchedule = (currenttime / timeall) * 262;
            progressRateColor.style.width = songSchedule + "px";
            //当歌曲播放完毕后
            if(mPlayer.ended){
                //清除定时器，进度条归零，播放下一首
                clearInterval(timer);
                progressRateColor.style.width = 0;
                //如果是单曲循环
                if(document.getElementById("nowPlayManner").title === "单曲循环"){
                    mPlayer.currentTime = 0;
                    mPlayer.play();
                }else{
                    //否则点击下一曲
                    document.getElementById("next").click();
                }
            }
        },1000);
    }

    if(playSwitch === "pause"){
        clearInterval(timer);
    }
};

//---------------------------------------------------【功能：歌曲进度调节】
MUSICENGINE.prototype.songProgressAdjust = function(time){
    this.musicPlayer.currentTime = time;

    //调整歌曲播放进度后，歌词到位
    lrcAtuoMove(time);
};

//---------------------------------------------------【歌曲进度变化过程】
function getSongProgress(event){
    var progressRateBg = document.getElementById("progressRateBg"),
        mplayer = document.getElementById("musicEngine"),
        progressBP,
        SongProgress;

    //获得距相对元素距离的百分比
    var coord = coordinate(event),
        offsetCoord_X = coord.coord_X;
    //计算进度条的宽度
    songScheduleChange(offsetCoord_X);
    //计算进度条的宽度百分比
    progressBP = progressBarPercentage(262,offsetCoord_X) / 100;
    //真实的歌曲进度数值
    SongProgress = progressBP * mplayer.duration;
    return SongProgress;
}

//---------------------------------------------------【歌曲进度条变化】
function songScheduleChange(size){
    var progressRateColor = document.getElementById("progressRateColor");
    progressRateColor.style.width = size + "px";
}

//---------------------------------------------------【获取歌曲总时间】
function timeAll(){
    var mPlayer = document.getElementById("musicEngine");
    if(mPlayer.currentTime != 0){
        return mPlayer.duration;
    }else{
        return 0;
    }
}

//---------------------------------------------------【获取歌曲当前播放时间】
function currentTime(){
    var mPlayer = document.getElementById("musicEngine");
    return mPlayer.currentTime;
}

//---------------------------------------------------【计算歌曲播放时间】
function songPlaybackTime(timeall,currenttime){
    var playTime = document.getElementById("playTime"),
        surplusTime = document.getElementById("surplusTime"),
        leftTime,
        rightTime;

    if(currenttime < timeall){
        //左边时间
        leftTime = parseInt(currenttime);
        //右边时间
        rightTime = parseInt(timeall - currenttime);
        //输出时间
        playTime.innerHTML = conversionTime(leftTime);
        surplusTime.innerHTML = "-" + conversionTime(rightTime);
    }else{
        //播放完毕
        playTime.innerHTML = "0:00";
        surplusTime.innerHTML = "-0:00";
    }
}

//---------------------------------------------------【将剩余秒数转化为标准格式】
function conversionTime(time){
    var surplusMinite,
        surplusSecond,
        cTime;
    //将剩余秒数转化为分钟
    surplusMinite = Math.floor((time / 60) % 60);
    //将剩余秒数转化为秒钟
    surplusSecond = Math.floor(time % 60);
    if(surplusSecond < 10){
        surplusSecond = "0" + surplusSecond;
    }
    cTime = surplusMinite + ":" + surplusSecond;
    return cTime;
}

/**
 *  歌曲列表
 */

//---------------------------------------------------【功能：打开&关闭专辑列表】
MUSICENGINE.prototype.albumLists = function(){
    //是否创建歌曲列表的父元素
    innerMusicList();
    //列表显示&隐藏
    var musicList = document.getElementById("musicList"),
        albumLists = document.getElementById("albumLists"),
        listWrap = document.getElementById("listWrap"),
        listName = document.getElementById("listName"),
        cutoverList = document.getElementById("cutoverList");

    if(albumLists.title === "打开专辑列表"){
        //打开前先把列表都关闭
        closeList();
        //列表的父元素显示隐藏
        removeClass(musicList,"hidden");
        //歌曲列表分类 - album
        listWrap.className = "list-wrap album";
        //歌曲列表名称
        listName.innerHTML = "专辑列表";
        //显示返回专辑列表
        cutoverList.innerHTML = "查看全部歌曲";
        cutoverList.className = "cutover-list";
        //打开歌曲列表icon常亮
        addClass(albumLists,"album-lists-hover");
        //打开歌曲列表icon的title变化
        albumLists.title = "关闭专辑列表";
        //生成专辑列表
        this.formatAlbumLists();
    }else{
        //如果点击的图标是点亮状态，则关闭列表
        if(albumLists.title === "关闭专辑列表"){
            closeList();
        }
    }
};

//---------------------------------------------------【功能：生成专辑列表】
MUSICENGINE.prototype.formatAlbumLists = function(){
    var song = this.song,
        listWrap = document.getElementById("listWrap"),
        albumNum = song.songData.length,
        html = "";
    //循环数据并插入
    for(var i=0;i<albumNum;i++){
        html += "<li class=\"s-l\">";
        html += "<img src=\"" + song.songData[i].albumCoverMax + "\" class=\"album-cover\">";
        html += "<span class=\"album-name\" title=\"" + song.songData[i].albumName + "\"><span class=\"speaker\"></span><span class=\"s-a\">" + song.songData[i].albumName + "</span></span>";
        html += "<div class=\"album-cover-hover hidden\">";
        html += "<div class=\"mask\" title=\"双击打开\"></div>";
        html += "<span class=\"album-song-num\" title=\"" + song.songData[i].albumSong.length + "首歌曲\">" + song.songData[i].albumSong.length + "</span>";
        html += "<div class=\"play-btn\" title=\"播放专辑：" + song.songData[i].albumName + "\"><div class=\"play-icon\"></div>播放专辑</div>";
        html += "</div>";
        html += "</li>";
    }
    listWrap.innerHTML = html;

    //给li元素绑定事件 双击事件 鼠标划上事件
    for(var m=0;m<listWrap.getElementsByTagName("li").length;m++){
        var dom = listWrap.getElementsByTagName("li")[m];

        //鼠标划入
        dom.onmouseover = function(){
            show(this.childNodes[2]);
        };

        //鼠标划出
        dom.onmouseout = function(event){
            var Event = event || window.event;
            if(Event){
            	if(dom.contains(Event.relatedTarget||Event.toElement)){
                    //如果是子元素，结束函数
            		return false;
            	 }else{
                    //触发的事件
                    hide(this.childNodes[2]);
                }
            }
        };

        //鼠标双击
        dom.ondblclick = function(){
            //生成专辑内歌曲列表
            formatInAlbumLists(song,this.childNodes[1].childNodes[1].innerHTML);
        };
    }

    //突出当前播放歌曲
    currentlyPlayingSong();
};

//---------------------------------------------------【功能：生成全部歌曲列表】
MUSICENGINE.prototype.formatAllSongLists = function(){
    var song = this.song,
        listWrap = document.getElementById("listWrap"),
        cutoverList = document.getElementById("cutoverList"),
        albumNum = song.songData.length,
        albumSongNum,
        html = "";

    //专辑数量循环
    for(var i=0;i<albumNum;i++){
        //专辑内歌曲数量循环
        albumSongNum = song.songData[i].albumSong.length;
        for(var j=0;j<albumSongNum;j++){
            html += "<li class=\"s-l\">";
            html += "<span class=\"s-name\" title=\"" + song.songData[i].albumSong[j].musicName + "\">" + song.songData[i].albumSong[j].musicName + "</span>";
            html += "<span class=\"s-album\" title=\"" + song.songData[i].albumName + "\">" + song.songData[i].albumName + "</span>";
            html += "<span class=\"s-time\">" + song.songData[i].albumSong[j].musicTime + "</span>";
            html += "<div name=\"addFavorites\" class=\"add-favorites hidden\" title=\"喜欢\"></div>";
            html += "</li>";
        }
    }
    //先关闭列表 然后点击播放列表按钮实现跳转
    listWrap.className = "list-wrap song";
    //标识是否在专辑列表内，用于更新播放列表
    listWrap.attributes["data-temp"].nodeValue = "0";
    //显示返回专辑列表
    cutoverList.innerHTML = "返回";
    cutoverList.className = "cutover-list";
    listWrap.innerHTML = html;
    //突出当前播放歌曲
    currentlyPlayingSong();
};

//---------------------------------------------------【功能：更新当前视图下的播放列表】
MUSICENGINE.prototype.updatePlaylist = function(){
    var listWrap = document.getElementById("listWrap"),
        song = this.song,
        nextAlbumSong = song.songData[this.albumIndex].albumSong.length,
        html = "";

    //更新播放列表
    if(hasClass(listWrap,"song") && listWrap.attributes["data-temp"].nodeValue === "1"){
        for(var j=0;j<nextAlbumSong;j++){
            html += "<li class=\"s-l\">";
            html += "<span class=\"s-name\" title=\"" + song.songData[this.albumIndex].albumSong[j].musicName + "\">" + song.songData[this.albumIndex].albumSong[j].musicName + "</span>";
            html += "<span class=\"s-album\" title=\"" + song.songData[this.albumIndex].albumName + "\">" + song.songData[this.albumIndex].albumName + "</span>";
            html += "<span class=\"s-time\">" + song.songData[this.albumIndex].albumSong[j].musicTime + "</span>";
            html += "<div name=\"addFavorites\" class=\"add-favorites hidden\" title=\"喜欢\"></div>";
            html += "</li>";
        }
        listWrap.innerHTML = html;
    }
};

//---------------------------------------------------【双击专辑生成歌曲列表】
function formatInAlbumLists(song,AlbumName){
    var listWrap = document.getElementById("listWrap"),
        cutoverList = document.getElementById("cutoverList"),
        albumNum = song.songData.length,
        albumSongNum,
        html = "";

    //循环查找相同的专辑名
    for(var i=0;i<albumNum;i++){
        if(song.songData[i].albumName === AlbumName){
            albumSongNum = song.songData[i].albumSong.length;
            for(var j=0;j<albumSongNum;j++){
                html += "<li class=\"s-l\">";
                html += "<span class=\"s-name\" title=\"" + song.songData[i].albumSong[j].musicName + "\">" + song.songData[i].albumSong[j].musicName + "</span>";
                html += "<span class=\"s-album\" title=\"" + song.songData[i].albumName + "\">" + song.songData[i].albumName + "</span>";
                html += "<span class=\"s-time\">" + song.songData[i].albumSong[j].musicTime + "</span>";
                html += "<div name=\"addFavorites\" class=\"add-favorites hidden\" title=\"喜欢\"></div>";
                html += "</li>";
            }
        }
    }
    //先关闭列表 然后点击播放列表按钮实现跳转
    listWrap.className = "list-wrap song";
    //标识是否在专辑列表内，用于更新播放列表
    listWrap.attributes["data-temp"].nodeValue = "1";
    //显示返回专辑列表
    cutoverList.innerHTML = "返回";
    cutoverList.className = "cutover-list";
    listWrap.innerHTML = html;
    //突出当前播放歌曲
    currentlyPlayingSong();
}

//---------------------------------------------------【关闭歌曲列表】
function closeList(){
    var musicList = document.getElementById("musicList"),
        albumLists = document.getElementById("albumLists"),
        listWrap = document.getElementById("listWrap");

    addClass(musicList,"hidden");
    //图标变暗
    removeClass(albumLists,"album-lists-hover");
    //图标的title
    albumLists.title = "打开专辑列表";
    //歌曲列表分类
    listWrap.className = "list-wrap";
}

//---------------------------------------------------【是否创建歌曲列表的父元素】
function innerMusicList(){
    if(!document.getElementById("musicList")){
        var musicListDom = document.createElement("div");
        musicListDom.id = "musicList";
        musicListDom.className = "music-list hidden";
        document.getElementsByTagName("body")[0].appendChild(musicListDom);
        //是否插入歌曲列表结构
        var html = "";
            html += "<div class=\"list-title\">";
            html += "<strong id=\"listName\"></strong>";
            html += "<span id=\"cutoverList\" class=\"cutover-list hidden\"></span>";
            html += "<div id=\"closeList\" class=\"close-list\" title=\"关闭列表\"></div>";
            html += "</div>";
            html += "<ul id=\"listWrap\" class=\"list-wrap\" data-temp=\"\"></ul>";
        document.getElementById("musicList").innerHTML = "";
        document.getElementById("musicList").innerHTML = html;
    }
}

//---------------------------------------------------【显示当前播放歌曲】
function currentlyPlayingSong(){
    var list = document.getElementById("listWrap"),
        indexMusicName = document.getElementById("musicName").innerHTML,
        indexAlbumName = document.getElementById("albumName").innerHTML;

    for(var i=0;i<list.childNodes.length;i++){
        for(var j=0;j<list.childNodes.length;j++){
            removeClass(list.childNodes[j],"playIng");
        }
        //显示当前播放歌曲
        if(hasClass(list,"song")){
            if(list.childNodes[i].childNodes[0].innerHTML === indexMusicName){
                addClass(list.childNodes[i],"playIng");
                break;
            }
        }
        //显示当前播放专辑
        if(hasClass(list,"album")){
            if(list.childNodes[i].childNodes[1].childNodes[1].innerHTML === indexAlbumName){
                addClass(list.childNodes[i],"playIng");
                break;
            }
        }
    }
}

/**
 * 控制歌曲播放方式（列表循环，单曲循环，随机播放，顺序播放）
 */

//---------------------------------------------------【功能：根据歌曲的播放方式分配下首歌曲的引索】
MUSICENGINE.prototype.songPlayMode = function(direction,mode){
    //获取歌曲引索(加一为了和歌曲数量保持一致)
    var albumIndex = this.albumIndex + 1,
        songIndex = this.songIndex + 1,
        song,
        album,
        //获取当前专辑的歌曲数量
        songNum = this.song.songData[this.albumIndex].albumSong.length,
        //获取歌曲总数
        musicNum = this.song.songNum,
        //获取专辑数量
        albumNum = this.song.songData.length;

    //【列表循环】
    if(mode === "列表循环"){
        //下一曲
        if(direction === "next"){
            //如果是最后一首，跳到下张专辑
            if(songIndex === songNum){
                //如果是最后一张专辑，并也是最后一首歌，循环列表
                if(albumIndex === albumNum && songIndex === songNum){
                    //播放第一张专辑第一首歌
                    album = 1;
                    song = 1;
                }else{
                    //正常跳到下张专辑，播放第一首歌
                    album = albumIndex + 1;
                    song = 1;
                }
            }else{
                //本专辑下一首
                album = albumIndex;
                song = songIndex + 1;
            }
        }
        //上一曲
        if(direction === "prev"){
            //如果是第一首，跳到上张专辑
            if(songIndex === 1){
                //如果是第一张专辑第一首歌，循环列表
                if(albumIndex === 1 && songIndex === 1){
                    //播放最后一张专辑最后一首歌
                    album = albumNum;
                    song = this.song.songData[albumNum - 1].albumSong.length;
                }else{
                    //跳转到上一个专辑的最后一首
                    album = albumIndex - 1;
                    song = this.song.songData[this.albumIndex - 1].albumSong.length;
                }
            }else{
                //本专辑上一首
                album = albumIndex;
                song = songIndex - 1;
            }
        }
    }

    //【随机播放】
    if(mode === "随机播放"){
        var randomAlbum = parseInt(albumNum * Math.random()),
            randomSong  = parseInt(this.song.songData[randomAlbum].albumSong.length * Math.random());
        album = randomAlbum + 1;
        song = randomSong + 1;
    }

    //【顺序播放 & 单曲循环】
    if(mode === "顺序播放" || mode === "单曲循环"){
        //下一曲
        if(direction === "next"){
            //如果是最后一首，跳到下张专辑
            if(songIndex === songNum){
                //如果是最后一张专辑，并也是最后一首歌，不跳转
                if(albumIndex === albumNum && songIndex === songNum){
                    //播放器初始化
                    playerInitialization();
                    return false;
                }else{
                    //正常跳到下张专辑，播放第一首歌
                    album = albumIndex + 1;
                    song = 1;
                }
            }else{
                //本专辑下一首
                album = albumIndex;
                song = songIndex + 1;
            }
        }
        //上一曲
        if(direction === "prev"){
            //如果是第一首，跳到上张专辑
            if(songIndex === 1){
                //如果是第一张专辑第一首歌，不跳转
                if(albumIndex === 1 && songIndex === 1){
                    //播放器初始化
                    playerInitialization();
                }else{
                    //跳转到上一个专辑的最后一首
                    album = albumIndex - 1;
                    song = this.song.songData[this.albumIndex - 1].albumSong.length;
                }
            }else{
                //本专辑上一首
                album = albumIndex;
                song = songIndex - 1;
            }
        }
    }

    //发送新的引索值,减一为了发送真实引索值
    this.playIndex(album - 1,song - 1);
};

//---------------------------------------------------【功能：计算点击的歌曲&专辑引索】
MUSICENGINE.prototype.muiscIndexAndAlbumIndex = function(activeSong){
    var song = this.song,
        albumNum = song.songData.length,
        //点击歌曲的名称
        indexSongName = activeSong.childNodes[0].innerHTML,
        //点击歌曲的专辑名称
        indexAlbumName = activeSong.childNodes[1].innerHTML,
        index = {};

    //专辑引索
    for(var i=0;i<albumNum;i++){
        if(indexAlbumName === song.songData[i].albumName){
            index.albumIndex = i;
            //歌曲引索
            for(var j=0;j<song.songData[i].albumSong.length;j++){
                if(indexSongName === song.songData[i].albumSong[j].musicName){
                    index.songIndex = j;
                    break;
                }
            }
            break;
        }
    }
    //返回引索
    return index;
};

//---------------------------------------------------【功能：根据系统返回的歌曲&专辑引索，准备播放器】
MUSICENGINE.prototype.playIndex = function(albumIndex,songIndex){
    var albumFrontCover = document.getElementById("albumFrontCover"),
        musicName = document.getElementById("musicName"),
        musicSinger = document.getElementById("musicSinger"),
        albumName = document.getElementById("albumName"),
        loadLrc = document.getElementById("loadLrc"),
        playTime = document.getElementById("playTime"),
        surplusTime = document.getElementById("surplusTime"),
        progressRateColor = document.getElementById("progressRateColor"),
        song = this.song;

    //记录引索
    this.albumIndex = albumIndex;
    this.songIndex = songIndex;

    //显示正在载入中...并初始化进度条
    show(loadLrc);
    playTime.innerHTML = "0:00";
    surplusTime.innerHTML = "-0:00";
    progressRateColor.style.width = "0";

    //歌曲地址
    this.musicPlayer.src = song.songData[albumIndex].albumSong[songIndex].musicLink;

    //专辑封面 没有则显示默认封面
    albumFrontCover.src = song.songData[albumIndex].albumSong[songIndex].albumCoverMin || "images/album.png";

    //歌曲名称
    musicName.innerHTML = song.songData[albumIndex].albumSong[songIndex].musicName;
    musicName.title = musicName.innerHTML;

    //歌手
    musicSinger.innerHTML = song.songData[albumIndex].albumSong[songIndex].musicSinger;
    musicSinger.title = musicSinger.innerHTML;

    //专辑
    albumName.innerHTML = song.songData[albumIndex].albumName;
    albumName.title = albumName.innerHTML;

    //播放
    this.toPlay("play");

    //歌词
    this.processingLyrics(song.songData[albumIndex].albumSong[songIndex].lyricsLink);

    //更新播放列表
    this.updatePlaylist();

    //突出显示当前播放歌曲
    currentlyPlayingSong();
};

//---------------------------------------------------【播放方式控件显示&隐藏，调节】
(function(){
    var nowPlayManner = document.getElementById("nowPlayManner"),
        playMannerControl = document.getElementById("playMannerControl"),
        orderPlay = document.getElementById("orderPlay"),
        shufflePlay = document.getElementById("shufflePlay"),
        singleCycle = document.getElementById("singleCycle"),
        listCycle = document.getElementById("listCycle");

    //播放方式控件显示&隐藏
    nowPlayManner.onmouseover = function(){
        show(playMannerControl);
    };
    //解决onmouseout事件遇到子元素时，也触发onmouseout的BUG
    playMannerControl.onmouseout = function(event){
        var Event = event || window.event;
        if(Event){
        	if(playMannerControl.contains(Event.relatedTarget||Event.toElement)){
                //如果是子元素，结束函数
        		return false;
        	 }else{
                //触发的事件
                hide(playMannerControl);
            }
        }
    };

    //点击选择相对应的播放方式（利用事件冒泡，事件委托的方式）
    //给dom的父节点添加事件，然后触发的时候，通过event.target得到子节点对象的id,然后根据id触发相应操作
    playMannerControl.onclick = function(event){
        var o = event ? event : window.event;
        PlayModeIconChange(document.getElementById(o.target.id));
    };
})();

//---------------------------------------------------【改变播放方式时图标变化】
function PlayModeIconChange(PlayMode){
    var nowPlayManner = document.getElementById("nowPlayManner"),
        playMannerControl = document.getElementById("playMannerControl"),
        className = PlayMode.className,
        title = PlayMode.title,
        newPlayMode;

    //class赋值
    nowPlayManner.className = "now-manner" + " " + className + " " + className + "-active";
    //title赋值
    nowPlayManner.title = title;

    //播放方式图标重新排序
    //重新创建这个元素
    newPlayMode = document.createElement("a");
    newPlayMode.href = "javascript:void(0);";
    newPlayMode.id = PlayMode.id;
    newPlayMode.className = PlayMode.className;
    newPlayMode.title = PlayMode.title;
    //删除这个元素再重新插入
    playMannerControl.removeChild(PlayMode);
    playMannerControl.appendChild(newPlayMode);
    hide(playMannerControl);
}

//---------------------------------------------------【播放器初始化】
function playerInitialization(){
    var albumFrontCover = document.getElementById("albumFrontCover"),
        musicName = document.getElementById("musicName"),
        musicSinger = document.getElementById("musicSinger"),
        albumName = document.getElementById("albumName"),
        playTime = document.getElementById("playTime"),
        surplusTime = document.getElementById("surplusTime"),
        progressRateColor = document.getElementById("progressRateColor"),
        musicEngine = document.getElementById("musicEngine");

    albumFrontCover.src = "images/album.png";
    musicName.innerHTML = "FeelPlayer";
    musicName.title = "FeelPlayer";
    musicSinger.innerHTML = "播放最爱的音乐";
    musicSinger.title = "播放最爱的音乐";
    albumName.innerHTML = "";
    albumName.title = "";
    musicEngine.src = "";
    playTime.innerHTML = "0:00";
    surplusTime.innerHTML = "-0:00";
    progressRateColor.style.width = "0";
    currentlyPlayingSong();
}

/**
 *  歌词同步功能
 */

//---------------------------------------------------【功能：同步歌词】
MUSICENGINE.prototype.processingLyrics = function(lrc){

    var lrcBox = document.getElementById("lrcBox");
    lrcBox.style.marginTop = 0; //初始化

    var xmlhttp,
        lrcVal,
        lrcArray = [],
        lrcTimeArray = [],
        html = "",
        musicName,
        singer;

    //ajax获取歌词lrc文件
    loadLrc(lrc);

    function loadLrc(url){

        if(lrc === ""){
            //没有歌词
            lrcBox.innerHTML = "<div class=\"no-lrc\">暂无歌词</div>";
        }else{
            xmlhttp = null;
            if(window.XMLHttpRequest){
                xmlhttp = new XMLHttpRequest();
            }
            //IE5,6
            else if(window.ActiveXObject){
                xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
            }
            if(xmlhttp != null){
                xmlhttp.onreadystatechange = getXMLHttpData;
                xmlhttp.open("get", url , true);
                xmlhttp.send(null);
            }else{
                alert("您的浏览器不支持 XMLHTTP");
            }
        }

    }

    function getXMLHttpData(){
        if(xmlhttp.readyState === 4){
            if(xmlhttp.status === 0 || xmlhttp.status === 200){

                //获取歌词内容
                lrcVal = xmlhttp.responseText.replace(/\[\d\d:\d\d.\d\d]/g,"");
                lrcArray = lrcVal.split("\n");

                //歌曲名
                lrcArray[0].replace(/\[\w\w\:(.*?)\]/g,function(){
                    musicName = arguments[1] || "暂无";
                });

                //歌手
                lrcArray[1].replace(/\[\w\w\:(.*?)\]/g,function(){
                    singer = arguments[1] || "暂无";
                });

                //获取歌曲名和歌手名
                html += "<p class=\"lrc-line\" data-timeLine=\"0\"><span class=\"mr15\">歌曲：" + musicName + "</span>歌手：" + singer + "</p>";

                //只保留歌词部分
                lrcArray.splice(0,4);

                //获取歌词时间轴
                xmlhttp.responseText.replace(/\[(\d*):(\d*)([\.|\:]\d*)\]/g,function(){

                    var min = arguments[1] | 0, //分
                        sec = arguments[2] | 0, //秒
                        realMin = min * 60 + sec; //计算总秒数

                    lrcTimeArray.push(realMin);
                });

                //将歌词装入容器
                for(var i=0;i<lrcTimeArray.length;i++){
                    html += "<p class=\"lrc-line\" data-timeLine=\"" + lrcTimeArray[i] + "\">" + lrcArray[i] + "</p>";
                }

                lrcBox.innerHTML = html;

            }else{
                alert("获取歌词出错，请刷新浏览器");
            }
        }
    }
};

//---------------------------------------------------【计算歌词滚动】
function lrcMove(timeall,currenttime){
    //歌曲总时间 timeall
    //当前时间 currenttime
    var lrcBox = document.getElementById("lrcBox"),
        domList = lrcBox.getElementsByTagName("p"),
        timer,
        index,
        s,
        m = parseInt(lrcBox.style.marginTop.split("-")[1]) || 0;

    for(var i=0;i<domList.length;i++){
        //如果当前时间等于遍历的歌词的时间
        var dataTimeLine = parseInt(domList[i].attributes["data-timeLine"].nodeValue);

        //等到唱第一句歌词的时候再滚动
        if(dataTimeLine > 0 && dataTimeLine === parseInt(currenttime)){

            //当前歌词的下标
            index = i;

            //当前下标值和上次记录的下标值不同才滚动，一个下标值只滚动一次
            if(s != i){
                //记录下标值
                s = i;

                //歌词颜色变化
                for(var j=0;j<domList.length;j++){
                    removeClass(domList[j],"color");
                }
                if(index > 0){
                    addClass(domList[index],"color");
                }

                //歌词滚动
                clearInterval(timer);
                timer = setInterval(function(){
                    m += 1;
                    if(m >= index * 30){
                        clearInterval(timer);
                    }else{
                        lrcBox.style.marginTop = "-" + m + "px";
                    }
                },10);
            }
        }
    }
}

//---------------------------------------------------【调整歌曲播放进度后，歌词自动到位】
function lrcAtuoMove(time){
    var lrcBox = document.getElementById("lrcBox"),
        domList = lrcBox.getElementsByTagName("p"),
        songTime = parseInt(time),
        dataArr = [],
        MoveTime,
        e;

    //获取歌词时间数组
    for(var i=0;i<domList.length;i++){
        dataArr.push(domList[i].attributes["data-timeLine"].nodeValue);
    }

    //找到应该跳转的时间
    for(var j=0;j<dataArr.length;j++){
        //时间为数组里最后一个小于或等于它的数
        if(dataArr[j] > songTime){
            MoveTime = dataArr[j - 1];
            break;
        }
    }

    //找到下标index,跳转
    e = MoveTime ? dataArr.indexOf(MoveTime) : domList.length - 1;
    lrcBox.style.marginTop = "-" + parseInt(e) * 30 + "px";

    //歌曲颜色
    for(var k=0;k<domList.length;k++){
        removeClass(domList[k],"color");
    }
    if(e > 0){
        addClass(domList[e],"color");
    }
}

/**
 *  播放器公用功能
 */

//---------------------------------------------------【计算进度条的百分比】
function progressBarPercentage(totalLength,actLage){
    //传入总长度totalLength和当前点击的坐标actLage
    var Result = (parseInt(actLage) / parseInt(totalLength)) * 100;
    return Math.ceil(Result);
}

//---------------------------------------------------【控制播放器打开隐藏】
function musicPlayerSwitch(){
    var musicPlayer = document.getElementById("musicPlayerWrap"),
        playerSwitch = document.getElementById("musicPlayerSwitch"),
        musicList = document.getElementById("musicList"),
        timer = 0,
        n = -550,
        m = 0;

    //打开播放器
    if(hasClass(playerSwitch,"on")){
        //替换类，用于判断播放器是否打开或隐藏
        replaceClass(playerSwitch,"on","off");
        clearInterval(timer);
        //播放器打开动画
        timer = setInterval(function(){
            n += 50;
            musicPlayer.style.left = n + "px";
            if(musicList){
                musicList.style.left = n + "px";
            }
            if(n >= 0){
                clearInterval(timer);
                //替换类，用于显示播放器打开或隐藏的三角按钮
                replaceClass(document.getElementById("playerSwitchBtn"),"switch-on","switch-off");
                playerSwitch.title = "隐藏播放器";
            }
        },10);
    }

    //隐藏播放器
    else if(hasClass(playerSwitch,"off")){
        replaceClass(playerSwitch,"off","on");
        clearInterval(timer);
        timer = setInterval(function(){
            m += 50;
            musicPlayer.style.left = "-" + m + "px";
            if(musicList){
                musicList.style.left = "-" + m + "px";
            }
            if(m >= 550){
                clearInterval(timer);
                replaceClass(document.getElementById("playerSwitchBtn"),"switch-off","switch-on");
                playerSwitch.title = "打开播放器";
            }
        },10);
    }
}

//---------------------------------------------------【控制歌词打开隐藏】
function lrcBoxSwitch(){
    var lyrics = document.getElementById("lyrics"),
        lrcWrap = document.getElementById("lrcWrap");

    //打开
    if(!hasClass(lyrics,"lyrics-hover")){
        lyrics.title = "关闭歌词";
        addClass(lyrics,"lyrics-hover");
        removeClass(lrcWrap,"hidden");
    }else{
        //隐藏
        lyrics.title = "打开歌词";
        removeClass(lyrics,"lyrics-hover");
        addClass(lrcWrap,"hidden");
    }
}

/**
 * 一些基础功能
 */

//---------------------------------------------------【检查元素是否含有某个特定的类，如果有，则返回true】
function hasClass(element,className){
    var classNum = element.className.split(" "),
        result;
    for(var i=0;i<classNum.length;i++){
        if(classNum[i] === className){
            result = true;
            break;
        }else{
            result = false;
        }
    }
    return result;
}

//---------------------------------------------------【为匹配的元素添加指定的类名】
function addClass(element,className){
    if(!hasClass(element,className)){
        element.className += " " + className;
    }
}

//---------------------------------------------------【为匹配的元素删除指定的类名】
function removeClass(element,className){
    if(hasClass(element,className)){
        var classNum = element.className.split(" ");
        for(var i=0;i<classNum.length;i++){
            if(classNum[i] === className){
                classNum.splice(i,1);
                element.className = classNum.join(" ");
                break;
            }
        }
    }
}

//---------------------------------------------------【为匹配的元素添加替换指定的类名】
function replaceClass(element,hasClassName,replaceClassName){
    if(hasClass(element,hasClassName)){
        var classNum = element.className.split(" ");
        for(var i=0;i<classNum.length;i++){
            if(classNum[i] === hasClassName){
                classNum[i] = replaceClassName;
                element.className = classNum.join(" ");
                break;
            }
        }
    }
}

//---------------------------------------------------【控制匹配的元素显示隐藏】
function show(element){
    element.style.display = "block";
}
function hide(element){
    element.style.display = "none";
}

//---------------------------------------------------【控制匹配的元素渐入渐出】
function fadeIn(element){
    var timer,
        opacity = 0;
    element.style.opacity = opacity;
    show(element);
    timer = setInterval(function(){
        opacity += 0.1;
        element.style.opacity = opacity;
        if(opacity === 10){
            clearInterval(timer);
        }
    },30);
}
function fadeOut(element){
    var timer,
        opacity = 1;
    element.style.opacity = opacity;
    timer = setInterval(function(){
        opacity -= 0.1;
        element.style.opacity = opacity;
        if(opacity === 0){
            clearInterval(timer);
        }
    },30);
    hide(element);
}

//---------------------------------------------------【让Firefox支持offsetX、offsetY】
//计算光标相对于第一个定位的父元素的坐标
function coordinate(e){
  var o = window.event || e,
      coord,
      coord_X,
      coord_Y;

  coord_X = (o.offsetX === undefined) ? getOffset(o).X : o.offsetX;
  coord_Y = (o.offsetY === undefined) ? getOffset(o).Y : o.offsetY;
  coord = { "coord_X" : coord_X , "coord_Y" : coord_Y };
  return coord;
}
function getOffset(e){
  var target = e.target, // 当前触发的目标对象
      eventCoord,
      pageCoord,
      offsetCoord;

  // 计算当前触发元素到文档的距离
  pageCoord = getPageCoord(target);

  // 计算光标到文档的距离
  eventCoord = {
    X : window.pageXOffset + e.clientX,
    Y : window.pageYOffset + e.clientY
  };

  // 相减获取光标到第一个定位的父元素的坐标
  offsetCoord = {
    X : eventCoord.X - pageCoord.X,
    Y : eventCoord.Y - pageCoord.Y
  };
  return offsetCoord;
}
function getPageCoord(element){
  var coord = { X : 0, Y : 0 };
  // 计算从当前触发元素到根节点为止，
  // 各级 offsetParent 元素的 offsetLeft 或 offsetTop 值之和
  while (element){
    coord.X += element.offsetLeft;
    coord.Y += element.offsetTop;
    element = element.offsetParent;
  }
  return coord;
}
</script>
