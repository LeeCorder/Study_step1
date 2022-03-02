웹스토리보이님의 YOUTUBE 강의 따라하기
==
STEP 1. 웹 표준 사이트 따라만들기
--
--------
## 1. 이미지를 표현하는 방법
   * HTML img태그 이용
      - 의미있는 이미지 사용 시
      - alt속성으로 대체텍스트 제공

   * CSS background속성 이용
      - 의미없는 이미지 사용(단순 꾸미기)
      - 대체텍스트 미제공
     
   * CSS bacgrond속성 이용하되 의미 있는 이미지 사용
      - 웹 표준 준수를 위해 ImageSprite기법, IR(imageReplacement) 이용
      - 이미지스프라이트 사용 시 유지보수 쉬우며, image 용량 많이 줄여짐
### 1-1. IR Method
   * Phark Method
      - 글자 : 배경이미지 설정하고 글자는 'text-indent:-9999px' 내어쓰기하여 안보이게 함
      - 단점으로는 이미지가 안보일 시 대체텍스트도 안보임
```css
.ir_pharkMethod {
    display: block;
    overflow: hidden;
    font-size: 0;
    line-height: 0;
    text-indent: -9999px;
}
```
  * WA IR Method
    - 글자를 span태그로 감싸고 'z-index:-1' 부여
    - 이미지가 안보이더라도 대체텍스트를 제공하고자 할 때 이용
```css
.ir_wa {
    display: block;
    overflow: hidden;
    position: relative;
    z-index: -1;
    width: 100%;
    height: 100%;
}
```
  * Screen Out Method 1
    - 대체텍스트 제공이 아닌 웹접근성을 고려한 숨김 텍스트를 제공하고자 할 때 이용
```css
.ir_screenOut {
    overflow: hidden;
    position: absolute;
    width: 0;
    height: 0;
    line-height: 0;
    text-indent: -9999px;
```
  * Screen Out Method 2
    - 1과 동일한 효과인데 아래와 같이도 사용됨
```css
.blind {
    position: absolute;
    margin: -1px;
    width: 1px;
    height: 1px;
    overflow: hidden;
}
```
--------
