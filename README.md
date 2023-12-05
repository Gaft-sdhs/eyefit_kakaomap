# eyefit_kakaomap
카카오맵 부분

## 기본 셋팅 참고 링크
https://apis.map.kakao.com/android/guide/

## 권한
AndroidMainfest.xml에 추가하기
````xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
    ...
</manifest>
````

## gradle
kakaomap를 사용하기 위해 gradle에 추가해야하는것
- implementation files('libs/libDaumMapAndroid.jar')
- 만일 .kts일 시 implementation(files("libs/libDaumMapAndroid.jar"))
 
## 카카오맵이 검정으로 보일 시
먼저 AndroidMainfest.xml에 밑 코드 <application>에 추가하기
````xml
android:usesCleartextTraffic="true"
````
그래도 안될 시
xml에 network_security_config.xml 를 추가 및 AndroidMainfest.xml에 밑 코드 <application>에 추가하기

````xml
android:networkSecurityConfig="@xml/network_security_config"
````

network_security_config.xml
````xml
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <domain-config cleartextTrafficPermitted="true">
        <domain includeSubdomains="true">maps.daum-img.net</domain>
    </domain-config>
</network-security-config>
````


  
        
        
