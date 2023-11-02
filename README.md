android, kotlin

## Applications(Android)

### 캘린더 플랫폼

> 캘린더와 지도를 결합하여 약속 장소 주변의 정보와 날씨 정보를 표시합니다.

(https://play.google.com/store/apps/details?id=com.zerodsoft.calendarplatform&pcampaignid=web_share)

| | | |
| --- | --- | --- |
| ![image](https://github.com/pknujsp/pknujsp/assets/48265129/daf42280-d993-4ce4-8f6f-2910c08149a6) | ![image](https://github.com/pknujsp/pknujsp/assets/48265129/9a84a735-9f0d-4138-87ca-c2dcee35edc0) | ![image](https://github.com/pknujsp/pknujsp/assets/48265129/6560b81e-b27e-48e8-9c5b-449dda11d494) |

### Medilenz

> 의약품 정보를 찾고 다른 사람들과 의견을 나눌 수 있는 의약품 정보 커뮤니티 서비스.
>
> 의약품을 카메라로 찍으면 인공지능이 분석하여 의약품을 찾아주기도 합니다.

**출시 예정**

| | | | |
| --- | --- | --- | --- |
| ![KakaoTalk_20230901_214556423](https://github.com/pknujsp/pknujsp/assets/48265129/703e51e7-a773-47e1-9ac3-03094b28b706) | ![KakaoTalk_20230901_214556423_03](https://github.com/pknujsp/pknujsp/assets/48265129/8db7c196-2443-4841-8350-31da1e04d051) | ![KakaoTalk_20230901_214556423_02](https://github.com/pknujsp/pknujsp/assets/48265129/7d91741b-48a4-4476-a58d-2d37cd6ea111) | ![KakaoTalk_20230901_214556423_01](https://github.com/pknujsp/pknujsp/assets/48265129/4d3c733e-d9bc-4c61-ab1e-efec2ffe9c78) |

### WeatherWizard
(https://github.com/pknujsp/WeatherWizard)

> 여러 개의 날씨 제공사의 예보 정보를 비교할 수 있는 안드로이드 날씨 애플리케이션

**출시 예정**

| | | | |
| --- | --- | --- | --- |
| ![264584938-8898ceb7-a6a2-4cfb-9004-e68b5024682f](https://github.com/pknujsp/pknujsp/assets/48265129/856bb149-4ccc-4ce5-84f8-f2512bcebf87) | ![KakaoTalk_20230831_172617056](https://github.com/pknujsp/pknujsp/assets/48265129/9261c150-903a-4207-a437-6bc439c1f7ba) | ![image](https://github.com/pknujsp/pknujsp/assets/48265129/3a01d1ff-11aa-456f-a221-0017729aedee) | ![264586332-09b42035-3959-4594-bd7c-2f34ebfd3801](https://github.com/pknujsp/pknujsp/assets/48265129/d90a4e5b-0577-4e87-b837-fc4675000f9a) |


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

**성능 문제로 보류, 추후 배포 예정**
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
