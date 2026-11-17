# 실습과제 #2 : 영화 데이터를 자바스크립트로
- 이름 / 학번 : 채민성 / 2651069
- 사이트 주소 : https://nope1015.github.io/web-hw2/
- 사용한 API : TMDB
https://image.tmdb.org/t/p/w342/5TMyytCI5Pfc9c1eNsljiCdiB05.jpg 극장판 치이카와: 인어 섬의 비밀 / 2026-07-24 / 7.4 
https://image.tmdb.org/t/p/w342/bvVoP1t2gNvmE9ccSrqR1zcGHGM.jpg F1 더 무비 / 2025-06-25 / 7.8 
https://image.tmdb.org/t/p/w342/ehzI1mVcnHqB58NqPyQwpMqcVoz.jpg 분노의 질주: 더 세븐 / 2015-04-01 / 7.2, 
https://image.tmdb.org/t/p/w342/mewjjhpju5JT1wDFJDMdctWcCqd.jpg 그란 투리스모 / 2023-08-09 / 7.7 
https://image.tmdb.org/t/p/w342/9W0XUvNtoJMG6kI4F4Y2mbsS2kt.jpg 라이언 일병 구하기 / 1998-07-24 / 8.2 
https://image.tmdb.org/t/p/w342/c55ijsOdntj6P25vDwHLdgsBpmV.jpg 암살자(들) / 2026-09-30 / 7.4 
https://image.tmdb.org/t/p/w342/wkm9BQLok7U2KihcCspCa663Qse.jpg 실낙원 / 2026-09-23 / 7.2 
https://image.tmdb.org/t/p/w342/ueigb5zra1tj6FTK9yhh2P33P9B.jpg 타짜: 벨제붑의 노래 / 2026-10-21 / 8.0 
https://image.tmdb.org/t/p/w342/LSGpoSAlitss0KOvVakkeUToZo.jpg 클레이페이스 / 2026-09-23 / 7.4, 
KOBIS 일별 박스오피스 (기준일 2026-10-25)
## 구현 항목 체크
1. Part A: data.js에 10칸짜리 배열 4개(titles, ratings, years, audiences). app.js에서 for와 if(또는 switch)로
계산한 A1~A5 다섯 줄이 콘솔에 찍힘. √
2. Part B 함수 7개: movies 10건(키 8개, Part A와 같은 순서). average, best, filterByRating, sortBy, search,
formatNumber, yearsSince가 표의 입력과 출력대로 동작하고 자가 테스트 1~8번 통과. √
3. Part C 응답 구조: tmdb.js에 now_playing 응답 전체가 const TMDB로 들어 있음. getList, averageBy로
C1, C2, 상위 5편 표, C4가 콘솔에 찍힘. √
4. 출력: console-a.png(A1~A5), console-c.png(C1~C4와 표) 2장. 사이트 주소의 <pre id="out">에 Part B
요약 3줄(textContent 한 번). √
5. 코드 품질: 함수마다 "입력 ⇒ 출력" 주석, var 없이 const와 let만, 정렬과 필터 뒤에도 movies 원본
그대로, 같은 계산을 두 번 쓰지 않음(average가 averageBy를 부름), 하는 일이 드러나는 이름. √
6. 제출 형식: 공개 저장소 web-hw2의 루트에 파일, Pages 동작, README에 자가 테스트 표와 생성형 AI
기록, 어느 파일에도 API 키 없음. √
## 자가 테스트 표 (2~8번도 Step 4의 표대로 이어 적기)
| 번호 | 호출 | 기대 결과 | 실제 결과 |
|---|---|---|---|
| 1 | formatNumber("1234567") | '1,234,567' | '1,234,567' |
| 2 | average(movies).toFixed(1) | 손으로 계산한 평균의 소수 1자리(예 '7.0') | '7.6' |
| 3 | best(movies).title | A2와 같은 제목 | '라이언 일병 구하기' |
| 4 | sortBy(movies, "rating", true)[0].title | 3번과 같은 제목 | '라이언 일병 구하기' |
| 5 | filterByRating(movies, 8).length | A3와 같은 개수 | 2 |
| 6 | search(movies, " 인터 ").length | 제목에 "인터"가 든 영화 수 | 0 |
| 7 | yearsSince("2014-11-06") | 올해 연도에서 2014를 뺀 값(2026년이면 12) | 12 |
| 8 | 4번 실행 뒤 movies[0].title | data.js의 첫 영화 제목 그대로 | '극장판 치이카와: 인어 섬의 비밀' |
## 어려웠던 점 3가지와 해결
어려웠던 점: 영화 제목과 평점의 순서를 맞추는 게 헷갈렸다.
해결: 배열의 인덱스를 확인하면서 순서를 맞췄다.
--------------------------------------------
어려웠던 점: 원하는 조건에 맞는 영화만 세는 방법이 어려웠다.
해결: if문을 사용해서 조건에 맞는 경우에만 개수를 증가시켰다.
--------------------------------------------
어려웠던 점: 결과가 콘솔에 제대로 출력되지 않아 당황했다.
해결: 코드를 다시 확인하고 새로고침해서 해결했다.
## 참고한 자료 (교재 절, MDN 페이지 제목, 검색어)
## 생성형 AI 사용 내역 (없으면 "없음")
- 질문 요지 : 실행했는데 콘솔창에 404 에러가 떴어 이거 왜이래?
- 답변 요약 : 니가 요청한 파일을 찾지 못해서 그럼. 새로고침 한번 해보셈 로딩 문제일수 있음.
- 채택 여부 : 채택