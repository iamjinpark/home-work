# 3주차 :넷플릭스 - 컴포넌트로 반응형 구현하기


## 1. Preview

용량이 너무 커 첨부가 안되는 문제로 링크 대신 첨부합니다 <br>
(https://youtu.be/SVcRt4rjV4k)

- 모바일 (max-width:768px) <br>
  &ensp; : 로고, 버튼 크기 작고 이메일 주소칸 모양 다름, footer 부분 2단으로 배열

- 데스크탑 (min-width:768px) <br>
&ensp; : 로고, 버튼 크기 좀 더 커짐, 배경화면과 이메일 주소칸 모양 변경, footer 부분 4단 배열 변환

## 2. HTML
### 2-1. 모바일
![readme-layout (1)](https://github.com/iamjinpark/home-work/assets/146078235/60afd6b7-ba17-49d2-9e76-f594fa2ab775)
![readme-layout (2)](https://github.com/iamjinpark/home-work/assets/146078235/c5f6efbd-cdc7-48b4-b63f-787ac605e66a)

- 전체적으로 header / main / footer 로 구성
- 빨간색 컨테이너는 컴포넌트를 의미 -> 컴포넌트 먼저 구성 후 합치는 방법으로 진행
#### mark up
- header : display: flex로 배치 뒤 gap과 padding으로 구조 배치
- main : display : 컴포넌트 외 p로 마크업, 전체를 wrapper로 묶어 레이아웃 배치 용이하게 구성
- footer : 전화번호에 바로 전화로 연결되게 마크업, guide 부분은 링크로 구성


### 2-2. 데스크탑
![readme-layout (3)](https://github.com/iamjinpark/home-work/assets/146078235/1fa6f16c-55f9-4963-b559-a22457f257e6)
![readme-layout (4)](https://github.com/iamjinpark/home-work/assets/146078235/3da60749-19a1-464f-9557-f389496f56d2)

- header : 배경화면 이미지 메인까지 확대, 언어설정 및 로그인 버튼 크기 확대
- main : 글자 크기 변경 및 이메일 주소 입력칸 변경 (flex:row로 변경)
- footer : 가이드 부분 2단에서 4단으로 확대, 언어설정 버튼 크기 확대

## 3. 반응형을 위한 컴포넌트 설계
- viewport 768px 기준으로 모바일과 데스크탑 분리
- media{}를 이용해 유연하게 변경 가능한 컴포넌트로 구성

### 3-1. logo

모바일 코드
```.logo-link {
  display: block;
  width: 5em;
  height: 1.38em;
}
```
데스크탑 코드
```
@media (min-width:768px) {
  .logo-link {
    width: 8.75em;
    height: 2.38em;
  }
}
```
### 3-2. input
#### 언어 변경 버튼
header 부분을 top, footer 부분을 bottom으로 설정 <br>
header만 크기 변경이 있었음 <br>
모바일 코드
```
.language-top select {
  width: 113px;
  height: 30px;
  text-align: center;
  padding: 0 10px;
  border: 1px solid #757575;
  border-radius: 2px;
  color: #757575;
}
```

데스크탑 코드
```
 .language-top select {
    height: 40px;
  }
```

#### 이메일 박스
모바일에선 둥근 모양과 떨어져 있는 버튼으로 구성 <br>
데스크탑으로 바뀔 시 크고 각진 모양의 이메일 입력칸과 붙어있는 버튼으로 변경 <br>
모바일 코드
```
.emailbox input {
  width: 14.64em;
  height: 1.43em;
  border-radius: 30px;
  font-size: 14px;
}
.emailbox-button {
  width: 11.43em;
  height: 2.86em;
  border-radius: 30px;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  justify-content: center;
}
```
데스크탑 코드
```
  .emailbox input {
    width: 500px;
    height: 22px;
    font-size: 16px;
    border-radius: 0;
  }

  .emailbox-button {
    width: 210px;
    height: 60px;
    border-radius: 0;
  }
```

### 3-3. footer
가이드 부분 flex로 배치하여 유연하게 단 변경 가능하게 구성<br>
모든 요소를 감싸는 wrapper에 width:80% 지정하여 가운데 배치 및 유연하게 움직일 수 있게 구성<br>
개인적으로 address 부분에서 모바일 인 경우 길이가 자꾸 어긋나 조금 헤맸지만,<br>
address에 max-width 지정하여 크기 고정으로 해결


## 4. 결과
2주차 과제에 완성하지 못했던 반응형을 드디어 구현할 수 있게 되었다!<br>
겹치는 부분들은 컴포넌트로 구성하여 재사용 하는 방식을 택했고,
처음 기준과 레이아웃 배치는 모두 모바일 부터 시작해서 데스크탑으로 커지는 방향으로 진행했다. 유연하게 커질 수 있도록 em과 고정되었으면 하는 부분은 px를 적절히 섞어 완성된 반응형 페이지를 구현할 수 있었다. <br>또한, 수업시간에 배운 절대경로를 사용해보았으며 중간중간 꼬인 코드들은 크롬 개발자 도구로 체크하면서 풀어나가는 시간을 가졌다. 전에는 코드를 싹 지우고 다시 설계했다면 이제는 어디가 잘못됐는지 찾아 그 부분만 수정하는 능력을 키우는 시간을 가질 수 있었다.
