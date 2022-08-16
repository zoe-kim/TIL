# video 태그 관련 이슈

video 태그 사용 시 난감했던 이슈들 정리

<br>

## 💡 여러 개의 video 연속 재생하기

같은 영역에 3개의 비디오(+ 하단 설명 이미지)를 연속으로 반복 재생하고자 함.<br>
구글링해서 찾은 내용들은 나랑 케이스가 다르거나, 첫번째 영상이 재생되지 않는 문제가 있어서 약간 변형했다. 지저분함 주의..!!

* **스크립트** <br>
하나의 비디오가 끝나면 서서히 사라지고, 다음 비디오가 디졸브로 나타나면서 재생되도록
  ```javascript
	$(document).ready(function () {

		$('#video1').on('ended', function () {
			$('#video1').fadeTo(400, 0).next().fadeTo(400, 1, function() {
				$('#video2').get(0).play();
			});
			$('#sub-tit-1').fadeTo(300, 0).next().fadeTo(600, 1);
		});

		$('#video2').on('ended', function () {
			$('#video2').fadeTo(400, 0).next().fadeTo(400, 1, function() {
				$('#video3').get(0).play();
			});
			$('#sub-tit-2').fadeTo(300, 0).next().fadeTo(600, 1);
		});

		$('#video3').on('ended', function () {
			$('#video3').fadeTo(400, 0).siblings('#video1').fadeTo(400, 1, function() {
				$('#video1').get(0).play();
			});
			$('#sub-tit-3').fadeTo(300, 0).siblings('#sub-tit-1').fadeTo(600, 1);
		});

	});
  ```

* **마크업** <br>
모든 요소에 디폴트로 `opacity: 0` 넣고, 스크립트 실행 전 상황을 위해 각 첫번째 요소에만 `opacity: 1`, 비디오는 `autoplay` 설정
  ```html
	<style>
		video {position: absolute; top: 316px; left: 50%; transform:translateX(-50%); opacity: 0;}
		.sub-tit {position: absolute; top: 1052px; left: 50%; transform:translateX(-50%); opacity: 0;}
	</style>

	<main>
		<video id="video1" muted playsinline preload="auto" autoplay style="opacity: 1;">
			<source src="#" type="video/mp4">
		</video>
		<video id="video2" muted playsinline preload="auto">
			<source src="#" type="video/mp4">
		</video>
		<video id="video3" muted playsinline preload="auto">
			<source src="#" type="video/mp4">
		</video>

		<div id="sub-tit-1" class="sub-tit" style="opacity: 1;">
			<img src="#" alt="">
		</div>
		<div id="sub-tit-2" class="sub-tit">
			<img src="#" alt="">
		</div>
		<div id="sub-tit-3" class="sub-tit">
			<img src="#" alt="">
		</div>
	</main>
  ```

<br>

## 💡 아이폰 저전력 모드 이슈

video 작업 페이지 배포 후, `muted`에 `playsinline` 설정을 하였는데도 특정 아이폰에서 재생이 되지 않는 문제 발생.

찾아보니 아이폰이 저전력 모드일때는 `autoplay muted playsinline` 속성이 동작하지 않는다는 사실을 알게 되었다... 해결방안을 아무리 찾아봐도 저전력 모드 관련 편법에 대해 최근 iOS가 업데이트 되는 등 너무나 철통방어라, 현재로서는 딱히 방법이 없어 재생 버튼을 한번만 누르면 자동재생이 실행되도록 조치했다.

* **마크업** <br>
사실 큰 변화는 없고ㅎㅎ 기존 마크업에서 첫번째 비디오에 `z-index: 1`만 추가로 넣어줬다. <br>
첫번째 비디오 위에 `opacity: 0`인 비디오 2개가 겹쳐있었기 때문에 재생 버튼을 눌러도 액션이 없었던 것!!
  ```html
	<main>
		<video id="video1" muted playsinline preload="auto" autoplay style="opacity: 1; z-index: 1">
			<source src="#" type="video/mp4">
		</video>
	</main>
  ```
