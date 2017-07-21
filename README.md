# 리니지M 변신카드 습득 시뮬레이션


## 설치

``` julia
Pkg.clone("https://github.com/YongHee-Kim/LineageM_TransformCard")
```


## 시뮬레이션 실행

전체 소스를 다운받은 후 아래의 파일의 스크립트를 순차적으로 실행하면 됩니다/

`..\\run\\montecarlo_transformcard.jl`


62째 줄에 있는 `n=10000` 정도로 해주면 평균으로 수렴하게 됩니다.


시뮬레이션 결과는 `..\\output\\montecarlo_card.csv`로 저장됩니다.

**※ 더블클릭해서 엑셀에서 열면 인코딩 문제로 문자열이 깨지는데, 엑셀을 실행하여 상단 탭의 `데이터->텍스트(외부데이터 가져오기)`로 데이터를 가져오면 제대로 볼 수 있습니다. **


## 시뮬레이션 결과
### 기반 데이터
1. 변신카드 DB는 인벤 [데이터베이스 사용](http://lineagem.inven.co.kr/dataninfo/polymorph/)
2. 유료뽑기 확률은 [공식 홈페이지](https://lineagem.plaync.com/board/rules/view?articleId=773442) 공개 확률표 참조
3. 합성시 상위 카드 등장확률은 [게임 유저의 연구자료를](http://qing.one/1133) 사용
    - 합성확률: 일반(33%), 고급(25%), 희귀(10%), 영웅(1%)-> 데이터 없음  
    - 합성시 같은 등급의 카드는 동일한 확률로 습득한다고 가정


[표-상급 변신 뽑기 시뮬레이션 10만회 결과]

| 목표     | 합성횟수_일반 | 합성횟수_고급 | 합성횟수_희귀 | 합성횟수_영웅 |     가챠횟수 |       다이아 |       현금구매액 |
| ------ | ------: | ------: | ------: | ------: | -------: | --------: | ----------: |
| 첫고급    |     0.0 |       - |       - |       - |      4.9 |       538 |     ₩13,456 |
| 첫희귀    |    10.9 |     2.3 |       - |       - |     75.7 |     8,253 |    ₩206,330 |
| 모든고급수집 |    59.3 |    17.6 |     0.1 |       - |    286.0 |    31,195 |    ₩779,881 |
| 첫영웅    |   187.1 |    64.4 |     2.5 |       - |    824.1 |    89,899 |  ₩2,247,467 |
| 모든희귀수집 |   719.9 |   257.8 |    17.7 |     0.0 |  3,066.2 |   334,500 |  ₩8,362,497 |
| 모든영웅수집 | 5,288.5 | 1,917.1 |   186.9 |     8.0 | 22,284.8 | 2,431,066 | ₩60,776,648 |
