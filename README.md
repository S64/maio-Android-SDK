![](https://github.com/imobile-maio/maio-iOS-SDK/blob/wiki/doc/images/logo.png)

# maio Android SDK
- SDK Version: 1.0.7
- Released: 2017/12/15
- 対応 Android Version: 4.1 以降
- Supported Formats: Rewarded/Interstitial

## Quickstart

### maio SDKの取得・Getting maio SDK

- maioを導入したいプロジェクトの`build.gradle`に、以下のmavenリポジトリを追加します。
- Add maio Maven repository to your Project build.gradle:

<pre><code>allprojects {
    repositories {        
        maven{
            url "https://imobile-maio.github.io/maven"
        }
    }
}
</pre></code>

- maioSDKとGoogle Play Servicesをモジュールの`build.gradle`に追加します：
- Add the maio SDK and Google Play Services to your project by adding the following implementations inside your Module build.grade:

<pre><code>dependencies {
  implementation 'com.google.android.gms:play-services-ads:+'
  implementation 'com.maio:android-sdk:1.0.7'
}
</code></pre>

- maioアクティビティをマニフェストに追加します：
- Add the maio activity to your manifest:

<pre><code>&lt;activity
  android:name="jp.maio.sdk.android.AdFullscreenActivity"
  android:configChanges="orientation|screenLayout|screenSize|smallestScreenSize"
  android:hardwareAccelerated="true"
  android:label="maiosdk"
  android:theme="@android:style/Theme.NoTitleBar.Fullscreen" &gt;
  &lt;intent-filter&gt;
                &lt;data android:scheme="jp.maio.sdk.android"/&gt;
                &lt;action android:name="android.intent.action.VIEW" /&gt;
                &lt;category android:name="android.intent.category.DEFAULT" /&gt;
                &lt;category android:name="android.intent.category.BROWSABLE" /&gt;
            &lt;/intent-filter&gt;
&lt;/activity&gt;
</code></pre> 

### maio SDKの準備・maio SDK setup


<pre><code>private final String MEDIA_EID = "DemoPublisherMediaForAndroid";
protected void onCreate(Bundle savedInstanceState) {
 
   //初期化
   MaioAds.init(this, MEDIA_EID, new MaioAdsListener() {      
      &commat;Override
      public void onFinishedAd(int playtime, boolean skipped, int duration, String zoneEid) {
      }
      &commat;Override
      public void onClosedAd(String zoneEid) {          
      }
   });
}
</code></pre>

### maioの表示・Show maio Ads

<pre><code>//再生
if(MaioAds.canShow()){
  MaioAds.show();
}
</code></pre>

For more detailed samples and details on all of maio SDKs functions check out the API reference

- 日本語　https://github.com/imobile-maio/maio-Android-SDK/wiki/API-Reference
- English https://github.com/imobile-maio/maio-Android-SDK/wiki/API-Reference-(EN)

## Manual Download
[releases](https://github.com/imobile-maio/maio-Android-SDK/releases) から最新のリリースバージョンをダウンロードして下さい。

## Get Started
Android Studio (日本語） https://github.com/imobile-maio/maio-Android-SDK/wiki/Project-Setup---Android-Studio  

Android Studio (English) https://github.com/imobile-maio/maio-Android-SDK/wiki/Project-Setup-Android-Studio-(EN)  

Eclipse https://github.com/imobile-maio/maio-Android-SDK/wiki/Project-Setup---Eclipse

## API Reference
日本語　https://github.com/imobile-maio/maio-Android-SDK/wiki/API-Reference

English https://github.com/imobile-maio/maio-Android-SDK/wiki/API-Reference-(EN)

## FAQ
日本語　https://github.com/imobile-maio/maio-Android-SDK/wiki/FAQ

English https://github.com/imobile-maio/maio-Android-SDK/wiki/FAQ-(EN)


## What is maio?
[maio](https://maio.jp/) はこれまでのバナー広告に加え、新たな広告収益の機会を得ることが可能な動画広告プラットフォームです。  
バナー広告と違い、デベロッパーの設定したタイミングで、動画広告をコンテンツの一部として配信することができます。

また、動画広告再生後にアプリ内通貨やライフ等の報酬（リワード）をユーザーに還元する事で、動画広告の再生数が増加し、収益の最大化が見込めます。  
今までユーザーが離脱していたポイントに `動画広告 + リワード` を入れる事で、ユーザーのストレスを解消しアクティブ率を向上させる事も可能です。  

## Contact Us
- General
  + https://maio.jp/#contactWrap
- Technical Trouble Shooting
  + https://maio.jp/techsupport/index.html
