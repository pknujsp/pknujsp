## Applications(Android)

### <img src="https://github.com/pknujsp/pknujsp/assets/48265129/8aa9c017-182b-4396-a027-1a1b17f026c7" width="32px" height="auto"/>  에브리웨더 - 날씨 정보 여기에서 모두 온에어!
---

(https://play.google.com/store/apps/details?id=io.github.pknujsp.everyweather)

> 날씨 정보를 Ai로 요약받고, 여러 개의 날씨 제공사의 예보를 비교할 수 있는 안드로이드 날씨 애플리케이션


**출시 예정**

| | | |
| --- | --- | --- |
| ![KakaoTalk_20240309_022637982](https://github.com/pknujsp/pknujsp/assets/48265129/1395395b-491c-4ce6-b921-88eb0485698c) | ![KakaoTalk_20240309_022637982_03](https://github.com/pknujsp/pknujsp/assets/48265129/2f0da063-3ffa-48cc-9c51-fd68672feec3) | ![KakaoTalk_20240309_022637982_04](https://github.com/pknujsp/pknujsp/assets/48265129/80972092-fa46-4aac-9674-35215c61114e) |
| ![KakaoTalk_20240309_022637982_05](https://github.com/pknujsp/pknujsp/assets/48265129/0850ae05-28fa-40c6-98a9-95ee1336ebc8) | ![KakaoTalk_20240309_022637982_10](https://github.com/pknujsp/pknujsp/assets/48265129/fa8b7825-2468-4c54-85c8-520f04e1d692) | ![KakaoTalk_20240309_022637982_08](https://github.com/pknujsp/pknujsp/assets/48265129/2b2eda2f-544e-4073-afa9-95e608b0c0be) |
| ![시간별예보비교위젯](https://github.com/pknujsp/pknujsp/assets/48265129/a0cc162b-0c12-4b2e-8b1a-2f30d35f7d65) | ![일별예보비교위젯](https://github.com/pknujsp/pknujsp/assets/48265129/ae60c2f5-8f5e-4f57-9211-2395aa7faefa) | ![상시 알림](https://github.com/pknujsp/pknujsp/assets/48265129/790541eb-556f-4566-84be-dad94113bfa2) |


### <img src="https://github.com/pknujsp/pknujsp/assets/48265129/e2c89bd0-ef8d-4c7e-be80-dd47712b2030" width="32px" height="auto"/>  Medilenz
---

> 의약품 정보를 찾고 다른 사람들과 의견을 나눌 수 있는 의약품 정보 커뮤니티 서비스.
>
> 의약품을 카메라로 찍으면 인공지능이 분석하여 의약품을 찾아주기도 합니다.

**출시 예정**

| | | | |
| --- | --- | --- | --- |
| ![메인](https://github.com/pknujsp/pknujsp/assets/48265129/86923b95-2cac-4cdd-a2e0-6b2a7cfe9f78) | ![ai카메라](https://github.com/pknujsp/pknujsp/assets/48265129/c021901c-8399-4408-bef4-f6dc466fd814) | ![약 검색](https://github.com/pknujsp/pknujsp/assets/48265129/0214da7f-4518-4f8d-ae0d-698eb307d651) | ![댓글](https://github.com/pknujsp/pknujsp/assets/48265129/5dc2fb73-37e7-4781-b482-2b0995fa2f6c) |


### <img src="https://github.com/pknujsp/pknujsp/assets/48265129/e90bd2a3-1378-4735-80bd-e963d50877cd" width="32px" height="auto"/> 캘린더 플랫폼

---

> 캘린더와 지도를 결합하여 약속 장소 주변의 정보와 날씨 정보를 표시합니다.

(https://play.google.com/store/apps/details?id=com.zerodsoft.calendarplatform)

| | | | |
| --- | --- | --- | --- |
| ![image](https://github.com/pknujsp/pknujsp/assets/48265129/daf42280-d993-4ce4-8f6f-2910c08149a6) | ![image](https://github.com/pknujsp/pknujsp/assets/48265129/9a84a735-9f0d-4138-87ca-c2dcee35edc0) | ![image](https://github.com/pknujsp/pknujsp/assets/48265129/6560b81e-b27e-48e8-9c5b-449dda11d494) | ![캘린더플랫폼1](https://github.com/pknujsp/pknujsp/assets/48265129/a01d56de-6480-4151-807e-ebc86287acfd) |


## Libraries(Android)

### KSealedBinding

**안정화 버전 배포 중**
(https://github.com/pknujsp/KSealedBinding)

> Kotlin의 sealed 클래스, 인터페이스에 대한 바인딩 함수를 자동으로 생성하는 라이브러리

Use **@KBindFunc**

```kotlin
@KBindFunc
sealed interface UiState<out T> {
  data class Success<out T>(val data: T) : UiState<T>
  data class Error(val exception: Throwable) : UiState<Nothing>
  object Loading : UiState<Nothing>
}
```

```kotlin
public inline fun <T> UiState<T>.onError(block: (Throwable) -> Unit): UiState<T> {
  if (this is UiState.Error)
    block(exception)
  return this
}

public inline fun <T> UiState<T>.onLoading(block: () -> Unit): UiState<T> {
  if (this is UiState.Loading)
    block()
  return this
}

public inline fun <T> UiState<T>.onSuccess(block: (T) -> Unit): UiState<T> {
  if (this is UiState.Success)
    block(data)
  return this
}
```

### SmartDeeplink

**리팩토링 예정, 개발 버전 배포 중**
(https://github.com/pknujsp/android-smartdeeplink)

> Android Navigation Deeplink 사용 시 데이터를 좀 더 편하게 주고 받을 수 있도록 도와주는 라이브러리


### Blurring

**갤럭시S9이하 스펙의 기기에서 발생하는 성능 문제로 보류, 추후 배포 예정**
(https://github.com/pknujsp/android-blur)

> Android 12 미만에서도 Window에 흐림 효과를 적용할 수 있게 해주는 라이브러리





<div style="margin: 24px;">
<div align="center" style="margin-bottom: 20px;">
  <img src="https://github-readme-streak-stats.herokuapp.com?user=pknujsp&theme=transparent&hide_border=true&border_radius=5.0&date_format=%5BY.%5Dn.j&fire=EB1571"/>
</div>
 
<div align="center" style="margin-bottom: 20px;">
  <img style="margin-right: 10px;" src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=pknujsp&theme=github&utcOffset=9"/>
   <img style="margin-left: 10px;" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=pknujsp&theme=github"/>
</div>
<div align="center">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=pknujsp&langs_count=6&layout=compact"/>
</div>
</div>
