# home-work

[HTML/CSS] 상품구매탭

1.HTML Mark up
<section class="mission">
    <!-- 꿀생강차 -->
    <div class="ginger-tea">
      <div class="gt-logo">로고</div>
      <h1 class="gt-title gt-font">타이틀</h1>
      <div class="gt-img">이미지</div>
      <button class="button1" type="button">
        <img class="bt-img1" src="./images/angle-right1.png" alt="버튼" />
      </button>
    </div>
    <!-- 핸드크림, 보리차 똑같이 반복-->
</section>

explain -> 큰 그룹 'misson-01'안에 3개의 상품 그룹으로 묶어준 뒤 각자 다른 클래스명의 같은 요소로 마크업 제작
상품 그룹은 로고(div.logo), 타이틀(h1.title), 이미지(div.img), 버튼 요소로 구성


2. css summary
   - 전체 body 에 Noto Sans KR 폰트 적용
   - margin 30px auto값으로 중앙 배열
   - 핸드크림, 보리차 / 꿀생강차 / 버튼 요소로 나눠 코드 구성
   - 상품 그룹 내 위치 배열은 'position : relative(부모요소), absolute(이미지,버튼)'으로 진행
   - 총 상품 그룹 배치는 'flex : row, flex-start'로 진행
   - 배열 예시 코드 첨부
    ** .ginger-tea** {
        width: 502px; height: 310px;
        border: 2px solid #C4C4C4; background: white;
        **position: relative;**
        margin: 0px 6px 0px 6px;
        }

    **.gt-logo **{
        width: 112px; height: 67px;
        background: #C4C4C4 50%;
        background-image: url(./images/logo1.png); background-repeat: no-repeat;
        **position: absolute;**
        top: 75px; bottom: 168px; margin: 0 73px 317px;
        }

   - 회색 버튼에서 파란색 구매 버튼으로 바뀌는 효과 적용 -> :hover사용 및 :before요소로 텍스트 적용
     .button1:hover {
        width: 112px;
        background-color: #0074E9;
        border: none;
        }

    .button1:hover:before {
     content: '구매하기';
     font-size: 14px;
     font-weight: 500;
     line-height: 16.8px;
     color: white;
        }

  3. 과제를 통해 얻은 점 :
     position 태그의 relative와 absolute의 기준, 이동 방향, 코드 작성의 기준이 헷갈렸는데 이번 과제를 통해 정확히 어디에 relative를 적용하고 absoltue를 적용해야 하는지 알게 되었다.
     relative는 원래 위치 기준으로 이동, absolute는 부모 영역이 없으면 사용자창 기준, 이때 윗 부모 요소에 relative를 지정해주면 쉽게 위치 조정이 가능하다.
     float 요소를 하나도 사용하지 못해 아쉬운데 따로 연습해 봐야겠다. flex를 사용하면 더 쉽게 할 수 있다는것을 알지만 position에 대해 정확히 알고 넘어가고 싶어서 모든 배치를 position으로 진행하게 되었다.

