---
title: 第一次架設Hexo網站
date: 2019-01-19 23:29:33
tags: 
     - 架設Hexo 
---
# 前言
這篇文章前前後後拖了快一個月才生出來，主要是想要紀錄自己是怎麼把這個網站架設出來的。那為什麼要架設這個網站呢?因為我記性很差，就決定架設一個網站幫自己紀錄平常工作中或生活中學的的一些東西，最常會出現的應該會是平常我用Unity開發遊戲的一些紀錄。好像離題滿多的了哈哈，但作為這個網站的第一篇文章就讓我囉嗦一點吧。

有人可能會想為什麼我不用Medium、Google Blog寫文章就好了呢?但我就是想要自己架設一個我可以清楚架構的網站嘛！

這篇文章是參考了很多網站上的大神們的文章才寫出來的，因為對於Jave與網要架設完全是第一次嘗試，如果有錯誤的地方還各位請不吝指教。

# Hexo是什麼
>Hexo 是基於 Node.js 開發的套件，它可以將 Markdown 轉成 HTML，而且提供了豐富的工具。

這是在搜尋時找到解釋Hexo的一段話，因為筆者對於Node.js與Hexo完全是初學，所以就引用過來解釋，感謝友站提供引用。

<!--more-->

# 架設Hexo步驟
* 安裝NPM
	-到Node官網下載NVM安裝NPM
* 安裝Git
	-到Git官站下載
* 安裝Hexo
	-用CMD的指令安裝
* 設定Hexo
	-更換主題與設定檔
* 將Hexo發佈到Github
	-利用CMD發佈到GitHub



# 安裝NPM
使用Hexo架設網站必須要先安裝NPM到電腦環境中，因為Hexo是基於Node.js的開發的套件，所以想要使用Hexo的指令需要使用到NPM的協助。

而NPM是什麼呢?
它全名是「Node Package Manager」，可以理解為一個線上套件庫，用來從線上下載各式各樣的 Javascript 套件。

NPM可以透過NVM(Node Version Manager)來安裝，NVM是服務給 Node.js用的工具，所以我們可以利用它來安裝 Node.js 跟 NPM，但這邊我們只需要安裝NPM即可。

首先，到Node的官網下載安裝包。
[Node官網](https://nodejs.org/en/)
筆者是下載10.14.1LTS的版本。
{% asset_img 01.PNG %}

接著，啟動安裝包，這邊我們只需要安裝npm package manager。

{% asset_img 02.PNG %}

最後，安裝完成後啟動CMD，輸入以下指令碼，有成功出現版號NPM就安裝成功了~
```
npm -v
```

{% asset_img 03.PNG %}

另外再搜尋時也找到一個新的package管理器Yarn，但筆者沒有深加研究就不贅述。

# 安裝Git
接下來要安裝Git到電腦環境，安裝Git是為了能夠在Github上架設網站的伺服器，這個步驟很簡單只需要到Git官網下載Git安裝包。
[Git官網](https://git-scm.com/)

安裝時一路按Next下去，除非有想要特別設定，一般來說使用預設即可。

{% asset_img 04.PNG %}

# 安裝Hexo
這步驟要利用CMD的指令安裝，輸入以下指令，路徑用預設的C:\Users\XXX就行了。
```
npm install hexo-cli -g
```
{% asset_img 05.PNG %}

接下來會開始自動安裝hexo，完成後輸入`hexo v`指令確認使否安裝成功，有出現版本號就完成安裝了。
```
hexo v
```
完成之後可以使用`hexo init`來建置用來存放部落格原始資料的目錄。
```
hexo init XXXX
```
上面的"XXXX"是要想要的資料夾名稱，可以隨意取，筆者是以blog.xxx.xxx的方式命名。

{% asset_img 06.PNG %}

成功後會在路徑下出現對應名稱的資料夾。

{% asset_img 07.PNG %}

接下來要進入剛剛建立好的blog目錄底下，並輸入`npm install`來進行載入套件。

```
npm install
```
{% asset_img 08.PNG %}

接著，可以使用`hexo server`或`hexo s`來啟動 LocalHost 的 Server ，預設會在 localhost:4000 的位置。
(localhost 代表的是只能從本地瀏覽此網站，無法從外部瀏覽)
```
hexo server
```

{% asset_img 09.PNG %}

輸入`http://localhost:4000`到瀏覽器，有出現下圖就代表網站在本地設置成功啦。

{% asset_img 10.PNG %}

# 設定Hexo
在開始設定Hexo之前先讓我們了解一下資料夾的目錄結構
```
  _config.yml            -> 最主要的設定檔
  package.json           -> 相依套件列表
  node_modules/          -> 相依套件
  public/                -> 生成的靜態網站資源
  source/
    _posts               -> 你寫的文章都放在這裡面
      hello-world.md     -> 文章
  themes/                -> 網站主題都放裡面
    landscape/
      _config.yml        -> 主題設定檔
```
接下來我們主要會在`config.yml`與`themes`資料夾進行更動。

### 網站設定
`_config.yml`，可設定：

* 作者名字、標題、描述
* 語系設定
* 是否產生assets資料夾
* 套用主題

### 主題設定
`themes/theme-name/_config.yml`，可設定：

* 頭像
* 社群網路連結
* 新增頁面
* 其他客製化選項(scheme、高亮、動畫等等)

### 更換主題
Hexo的預設主題是landscape，我覺得不是很和我胃口(畢竟是預設)，推薦一款在網路上很多人都在使用的主題:
[NexT](https://github.com/iissnan/hexo-theme-next)

{% asset_img 12.PNG %}

可以選擇用Git安裝或是直接從網站下載下來，筆者是直接從網站下載的。
另外，如果想要看看其他主題可以到這個[網站](https://hexo.io/themes/)看看。

下載後解壓縮，把文件放到`themes`資料夾中，並改名為Next。

{% asset_img 13.PNG %}

接著修改網站設定`_config.yml`，在裡面找到theme，把後面得主題名稱修改成Next。
(筆者是使用Visual studio開，當然使用記事本也是可以開的)

{% asset_img 14.PNG %}

使用`hexo s`，重新啟動server，就可以看到修改過後的主題了！

### 語言設定

在`_config.yml`中找到language欄位，設定為`zh-tw`就會支援繁中。
```
language: zh-tw
```

### Scheme外觀設定

NexT提供多種Scheme選擇，其中Muse是預設的主題。筆者滿喜歡Mist這個主題。

在主題設定`theme/next/_config.yml`裡找到scheme設定，把注釋去掉即可開啟。

```
#scheme: Muse
#scheme: Mist
scheme: Pisces
#scheme: Gemini
```

### 代碼高亮

官方說明
> NexT 使用 Tomorrow Theme 作为代码高亮，共有5款主题供你选择。 NexT 默认使用的是 白色的 normal 主题，可选的值有 normal，night， night blue， night bright， night eighties

```
highlight_theme: normal
```
{% asset_img 15.PNG %}

### 背景動畫效果

在主題設定`themes/next/_config.yml`裡選擇要開啟的動畫效果，要打開就把值設定成true

```
# Canvas-nest
canvas_nest: true
# three_waves
three_waves: false
# canvas_lines
canvas_lines: false
# canvas_sphere
canvas_sphere: false
# Only fit scheme Pisces
# Canvas-ribbon
canvas_ribbon: false
```

***

### 關於作者

接下來開始設定關於自己的資訊吧！

#### 頭像

先在`sourse`裡新增一個`uploads`資料夾，用來存放大頭照。

{% asset_img 16.PNG %}

把自己的大頭照丟進`source/uploads/`這個資料夾裡，然後在主題設定`themes/next/_config.yml`中設定大頭照路徑:

```
avatar: /uploads/avatar.jpg
```
#### 作者

在網站設定`_config.yml`中設定名字、標題和副標題
```
title: <標題>
subtitle: <副標題>
description: <描述>
author: <你的名字>
```
#### 開啟社群帳號連結

在主題設定`themes/next/_config.yml`中新增社群網路連結，記得要把`#social:`跟想要開啟的社群連結前面的`#`刪除。

```
# Social links
social:
  GitHub: https://github.com/your-user-name
  Twitter: https://twitter.com/your-user-name
```

#### About Me Page

輸入以下指令，新建一個about頁面。

```
hexo new page "about"
```
在`themes/next/_config.yml`將about前面的註解去掉。
```
menu:
  home: /
  archives: /archives
  tags: /tags
  about: /about
```

編輯`source/about/index.md`

```
---
title: 關於我
date: 2017-08-10 13:23:37
---
# 哈囉
介紹自己的內容......
```
成品:

{% asset_img 17.PNG %}


***

### 第一篇文章

終於要發表第一篇文章了！

#### 設定

所有的文章都會在`source/_posts`裡。其實一開始裡面就已經有一篇範例文章`hello-world.md`了。

在發表文章以前，先進行一個簡單的設定，在網站設定`_config.yml`中:

```
post_asset_folder: true
```

這樣每當新增一篇文章時，會自動在`source/_posts/`裡新增一個跟文章同名的資料夾用來放置圖片資源。

#### 新增文章

創造一篇名叫”測試”的文章

```
 hexo new post 測試
```

編輯`source/_posts/test.md`

```
---
title: 測試
date: 2018-12-24 12:22:32
tags: test
---
測試發文~~~~~
```
#### Tags分類

文章可以透過標籤來進行分類

記得先將主題設定`theme/next/_config.yml`的tags註解拿掉。

```
menu:
  home: / || home
  about: /about/ || user
  tags: /tags/ || tags
```

新建一個頁面，叫做tags
```
hexo new page "tags"
```

編輯剛新建的頁面`source/_posts/tags/index.md`，將頁面的type設為”tags”(這名稱要跟主題設定`_config.yml`的tags一樣)。

```
---
title: All tags
date: 2018-12-26 22:41:44
type: "tags"
---

```

為剛剛的第一篇新文章加入標籤"架設Hexo"。

```
---
title: 測試
date: 2018-12-10 23:56:33
tags: 架設Hexo
---
```

當一篇文章有多個Tags時就用下面的方式。

```
tags:
  - Tag1
  - Tag2
  - Tag3
```
完成~文章現在可以透過標籤分類了。

{% asset_img 18.PNG %}

另外，如果有想要刪除之前的tag先用以下指令清除hexo。
```
hexo clean
```
再重新登一次hexo server。
```
hexo s
```

# 將Hexo發佈到Github
終於到了最後一步，讓自己的網站能夠被大家看到。
部屬的方式有很多，但筆者目前只會用Github部屬，所以就先這個方法部屬網站。

首先，你要先有GitHub的網站帳號。

{% asset_img 19.PNG %}

然後建立一個Github專案，名稱為`<username>.github.io`。例如說我的名字叫做`MagicDogGuo`，那我就創建一個`MagicDogGuo.github.io`的專案(username這裡一定要打的跟自己的文字一樣，不然會出事網站會部屬失敗)。

{% asset_img 20.PNG %}

再來安裝Git套件:

```
npm add hexo-deployer-git
```

修改網站設定`_config.yml`，找到deploy之後進行以下修改:

```
deploy:
  type: git
  repo: https://github.com/<yourAccount>/<repo>
  branch: <your-branch>
```
yourAccount是你的Github帳號，repo是你剛新建專案的網址(下面那張圖框起來的地方)，branch則是指定分枝，通常是master。

{% asset_img 21.PNG %}

接著用`hexo d`或`hexo deploy`部署到Github Pages

```
hexo deploy
```

接下來在瀏覽器輸入`<username>.github.io`就能看到自己的網站了！

### 更新Github

之後有更新文章輸入以下指令，注意如果只輸入`hexo d`文章是不會更新的喔。(更新之後要等大約3分鐘才會在網站看到)。

```
hexo clean && hexo generate && hexo d
```



<!--
<font face="黑体">我是黑体字</font> 
<font face="微软雅黑">我是微软雅黑</font> 
<font face="STCAIYUN">我是华文彩云</font>
<font color=#0099ff size=3 face="黑体">color=#0099ff size=72 face="黑体"
</font> <font color=#00ffff size=72>color=#00ffff</font> 
<font color=gray size=72>color=gray</font>
-->
