#TTS源的研究筆記：

「Legado」
id：必須填寫（最好使用10位數以上）
lastupdatetime：最後更新時間（格式最好是YYYYMMDDHHMMSS，但隨機生成也行）
paragraphpause：換段停頓（0-10000毫秒，250=微、500=小、750=中、1000=大）

「搜狗」→毫無反應，研究中。

「谷歌」→機味較重，備用，不跳段。

「訊飛」→質量參差不齊，備用，研究中。
voice：音色
speedDelta：語速
pitchDelta：音調
volumeDelta：音量

{
  "concurrentRate": "0",
  "contentType": "",
  "enabledCookieJar": false,
  "header": "",
  "id": 1629944057248,
  "jsLib": "",
  "lastUpdateTime": 1788028090934,
  "loginCheckJs": "",
  "loginUi": "",
  "loginUrl": "",
  "name": "讯飞——小梅（半转广粤）",
  "pauseDuration": 0,
  "url": "http://120.24.87.124/cgi-bin/ekho2.pl?cmd=SPEAK&voice=iflytekXiaomei&speedDelta=0&pitchDelta=0&volumeDelta=0&text={{java.encodeURI(java.encodeURI(speakText))}}"
}

「思必馳」→機味較輕，可用，會跳段。
voiceId：音色
speed：語速（0.0-1.0）→有人說0-10
volume：音量（0-100）
audioType：編碼（mp3/wav）

{
  "concurrentRate": "0",
  "contentType": "",
  "enabledCookieJar": false,
  "header": "",
  "id": 0000000000000,
  "jsLib": "",
  "lastUpdateTime": 1788027962246,
  "loginCheckJs": "",
  "loginUi": "",
  "loginUrl": "",
  "name": "思必馳-sample",
  "pauseDuration": 0,
  "url": "https://dds.dui.ai/runtime/v1/synthesize?voiceId=音色&text={{java.encodeURI(java.encodeURI(speakText))}}&speed=語速&volume=音量&audioType=格式"
}

「百度」→比較自然，好用，會跳段。
(tex)t：文字（最好一次不超過200字；JavaScript中可用encodeURIComponent()編碼，一次就行）
cuid：標識（預設baike，可以隨便生成，失效或限流就換一個）
lan：語言（zh=普通話、cte=粵語、en=美式英語、uk=英式英語）
spd：語速（0-15，預設5）→有人說1-9
vol：音量（基礎0-9，精品0-15，預設5，最小0）
pit：音調（0-15，預設5）
le：字集編碼（UTF-8）
url：接口（出錯可換 tsn↔tts 或者 http↔https）
pdt：（出錯可換11/12/30/31/160/211/220/232/301/505）
aue：音頻編碼（3=mp3-16k/24k格式、 4=pcm-16k/24k、5=pcm-8k、6=wav（內容同pcm-16k/24k）; 出錯可以確認content-type是否填寫了音頻編碼， 必須和aue數值對應的內容格式一致，最好直接把content-type刪掉留空。）
emo：情緒（neutral=中性、開心=happy、down=悲傷、angry=憤怒、surprise=驚訝、fear=恐懼，留空預設中性語氣；僅限指定音色支援情感合成，而且『超拟人多情感音色』能自動匹配情感無需人手設定，但不同音色支持的情感範圍存在不同。意思是，emo數值可以不調。）
per：音色（詳情：ai.baidu.com/ai-doc/SPEECH/Rluv3uq3d ）
↓
音色編號
基礎：度小宇=1、度小美=0、度逍遥=3、度丫丫=4。
精品：度小娇=5、度教授=6、度葛平=8、度播音=9、度京腔=10、度大叔=11、度逍遥=5003、度小鹿=5118、度博文=106、度小童=110、度小萌=111、度米朵=103。
臻品：度逍遥=4003、度博文=4106、度小贤=4115、度小鹿=4119、度灵儿=4105、度小乔=4117、度小雯=4100、度米朵=4103、度姗姗=4144、度小贝=4278、度清风=4143、度小新=4140、度小彦=4129、度星河=4149、度小清=4254、度博文=4206、南方=4226。
其他（大模型）：度涵竹*=4189、度嫣然=4194*、度泽言*=4193、度怀安*=4195、度清影*=4196、度沁遥*=4197、度小粤=20100、度晓芸=20101、四川小哥=4257、度阿闽=4132、度小蓉=4139、台媒女声=5977、度小台=4007、度湘玉=4150、度阿锦=4134、度筱林=4172。

{
  "concurrentRate": "",
  "contentType": "",
  "enabledCookieJar": false,
  "header": "",
  "id": 88880000,
  "jsLib": "",
  "lastUpdateTime": 20260830000000,
  "loginCheckJs": "",
  "loginUi": "",
  "loginUrl": "",
  "name": "百度-sample",
  "pauseDuration": 0,
  "url": " ​http://tts.baidu.com/text2audio,{\n    \"method\": \"POST\",\n    \"body\": \"tex={{java.encodeURI(java.encodeURI(speakText))}}&spd={{(speakSpeed + 5) / 10 + 語速}}&per=音色編號&cuid=baidu_speech_demo&idx=1&cod=2&lan=zh&ctp=1&pdt=505&vol=音量&aue=6&pit=音調&_res_tag_=audio\"\n}"
}

<hr>

「Edge」→大致自然，好用，不跳段。
(t)ext：文字
(v)oice：音色
(r)ate：語速（預設0，-100至100）
(p)itch：音調（預設0，-100至100）
volume：音量（最好不用這個）
style：情緒（很多沒有這個）
dialect：方言（很多沒有這個）

https://tts.zwei.de.eu.org/api/tts
https://libretts.is-an.org/api/tts
https://tts.okraworks.cn/api/text-to-speech