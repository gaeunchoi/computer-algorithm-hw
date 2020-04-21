# 컴퓨터 알고리즘 팀프로젝트 - 자판기 만들기

~~사실 자판기라기보다 피시방 음식 주문 생각했다^^~~

0. 결과창
<img width="692" alt="결과창" src="https://user-images.githubusercontent.com/56152020/79856518-6c031400-8407-11ea-9d92-5c996276c481.png">

1. Swing을 이용한 GUI 구성
- JFrame, JLabel, JButton, ImageIcon, JTextfield, JOptionPane 등을 사용하여 사용자 인터페이스 구현

2. Event 구현  

    1. -/+ 버튼 클릭
    - JTextfield인 total_out에 총액 표시해주기
    - 수량이 0일때 (-)버튼을 누르면 **setEnabled false**로 바꿔주기  
    
    2. 계산 버튼 클릭
    - 입력한 금액이 계산해야할 총액보다 작을 시 잔액부족 팝업 띄워주기
    - 그게 아니면 계산(그리디 알고리즘 사용)시작. 
      1. JTextfield인 money_in에서 입력값 받아와서(String) int로 형변환해주기
      2. 거슬러줄 돈 배열 생성 -> coin[] -> 10000, 5000, 1000, 500, 100, 50, 10
      3. 돈 개수 셀 배열 생성 -> coin_cnt[] -> 0으로 다 초기화
      4. for문으로 coin.length만큼 돌리면서 계산
      - ex) coin[0] = 10000이고 거슬러줘야 할 돈이 35000이면,  
      coin_cnt[0] = 거슬러줄돈 / 10000; 이렇게 카운트 올리고 거슬러줄돈 - coin_cnt[0] * coin[0] 으로 해서 쭉쭉 반복문으로 구현함
     
3. 여기서 사용한 Greedy Algorithm ?  
거스름돈을 최대한 적게 주기위해(돈을 조금준다는게 아님.. 동전의 개수를 적게준다던가 그런의미 ㅠ_ㅠ, 큰돈먼저 최대한 줄 수 있는만큼 주기) 사용하였다.  
배열을 이용해 쉽게 구현하였으며 구현법은 2번 Event 구현에서 자세히 설명해놨음

