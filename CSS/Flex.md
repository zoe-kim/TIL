# Flex

Flex는 레이아웃 배치 전용 기능으로 고안되었다. 그래서 레이아웃을 만들 때 쓰던 float나 inline-block 등을 이용한 기존 방식보다 훨씬 강력하고 편리한 기능들이 많다.

<br>

## 💡 컨테이너에 적용하는 속성
 
* **flex-wrap** : 줄넘김 처리 설정  
	* **nowrap (기본값)** : 줄바꿈을 하지 않는다. 넘치면 그냥 삐져 나감
	* **wrap** : 줄바꿈 한다. float이나 inline-block으로 배치한 요소들과 비슷하게 동작.
	* **wrap-reverse** : 줄바꿈을 하는데, 아이템을 역순으로 배치한다.

```scss
.container {
	flex-wrap: nowrap;
	// flex-wrap: wrap;
	// flex-wrap: wrap-reverse;
}
```