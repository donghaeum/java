# JAVA


## Bacarrat Card Game 만들기

Java를 이용하여 Bacarrat cardgame을 만들어 봅시다.

----

### Bacarrat Card Game Rule

1) Player와 Banker는 각각 2장의 카드를 받습니다.

2) 각각 2장의 카드의 숫자를 더해 1의자리 숫자가 9에 가까운 쪽이 이깁니다.
    - Ace는 1로 King, Queen, Jack, 10은 각각 0으로 계산합니다.

    - ex) Player의 카드 : Ace, 8 | Banker의 카드 : 7, Jack 일 때 Player의 카드 합 : 9 | Banker의 카드 합 : 7 이므로 Player 승리
    
3) 카드의 합이 5 이하일 경우

    - Player의 카드 합이 5 이하일 경우
      - Player만 카드를 한장 더 뽑습니다.
      
    - Banker의 카드 합이 5 이하일 경우
      - Banker만 카드를 한장 더 뽑습니다.
      
    - Player와 Banker의 카드 합이 5 이하일 경우
      - Player와 Banker 모두 카드를 더 뽑습니다.
      
----
      
#### player와 banker의 카드 생성
```
public class BaccaratGameStart {
	private int[] player_banker = {0, 0, 0};  // player와 banker가 뽑을 수 있는 카드는 최대 3장
	private int sum = 0;
	private int sum2 = 0;
	public static final int[] num = {1,2,3,4,5,6,7,8,9,0,0,0,0};  // Ace는 1로 King, Queen, Jack, 10은 각각 0으로 계산하여 카드를 생성
	
	public BaccaratGameStart() {
		init();
	}
	
  // player와 banker의 카드를 생성
	public void init() {
		for (int i = 0; i < 3; i++) {
			player_banker[i] = num[(int)(Math.random()*num.length)];  // num의 13개의 숫자에서 랜덤 값을 뽑아낸다.
		}
		sum = (player_banker[0]+player_banker[1])%10;  // 1의 자리 숫자만 필요하기 때문에 더한 값에서 10으로 나눠준다.
		sum2 = (sum+player_banker[2])%10;
	}
}
  ```
  
  #### 카드 값
  ```
  // 카드 한 장의 값
	public int Cards(int i) {
		return player_banker[i]; 
	}
  
  // 처음 2장의 카드를 더한 값
	public int getCardSum() {
		return sum;
	}
	
  // 3번째 카드를 더한 값
	public int getCardSum2() {
		return sum2;
	}
```

#### 값을 비교하여 조건에 맞게 결과값 출력
```
public boolean gameStart(int playercard, int playercard2, int bankercard, int bankercard2) {
	boolean isT = true;				
	while(isT) {
    
// player의 카드 합과 banker의 카드 합이  5 이상 일때
      
		if (playercard>5 && bankercard>5) {  
			if (playercard>bankercard) {
				System.out.println("플레이어가 승리하였습니다.");
			}
			else if (playercard<bankercard) {
				System.out.println("딜러가 승리하였습니다.");
			}
			else if (playercard==bankercard) {
				System.out.println("비겼습니다.");
			}
		}
      
// player의 카드 합은 5 이하 banker의 카드 합은 5 이상 일때
      
		else if (playercard<=5 && bankercard>5) {  
			System.out.println("플레이어가 카드를 한 장 더 뽑습니다.");
			System.out.println("\n");
			System.out.println("플레이어가 뽑은 카드는 "+playercard2+" 입니다.");
			System.out.println("\n");
				if (playercard2>bankercard) {
					System.out.println("플레이어가 승리하였습니다.");
				}
				else if (playercard2<bankercard) {
					System.out.println("딜러가 승리하였습니다.");
				}
				else if (playercard2==bankercard) {
					System.out.println("비겼습니다.");
				}
		}
      
// player의 카드 합은 5 이상 banker의 카드 합은 5 이하 일때
      
		else if (playercard>5 && bankercard<=5) {  
			System.out.println("딜러가 카드를 한 장 더 뽑습니다.");
			System.out.println("\n");
			System.out.println("딜러가 뽑은 카드는 "+bankercard2+" 입니다.");
			System.out.println("\n");
				if (playercard>bankercard2) {
					System.out.println("플레이어가 승리하였습니다.");
				}
				else if (playercard<bankercard2) {
					System.out.println("딜러가 승리하였습니다.");
				}
				else if (playercard==bankercard2) {
					System.out.println("비겼습니다.");
				}
		}
      
// player의 카드 합과 banker의 카드 합이 모두 5 이하 일때
      
		else if (playercard<=5 && bankercard<=5) {
			System.out.println("딜러와 플레이어가 카드를 한 장 더 뽑습니다.");
			System.out.println("\n");
			System.out.println("플레이어가 뽑은 카드는 "+playercard2+" 입니다."+"\n"+"딜러가 뽑은 카드는 "+bankercard2+" 입니다.");
			System.out.println("\n");
				if (playercard2>bankercard2) {
					System.out.println("플레이어가 승리하였습니다.");
				}
				else if (playercard2<bankercard2) {
					System.out.println("딜러가 승리하였습니다.");
				}
				else if (playercard2==bankercard2) {
					System.out.println("비겼습니다.");
				}
		}
		isT = false;				
	}
	return isT;	
}
```

#### 게임 시작하기

```
public class BaccaratCardGame {
	public static void main(String[] args) {		
		BaccaratGameStart player = new BaccaratGameStart();
		BaccaratGameStart banker = new BaccaratGameStart();
		int playerFirstSum = 0;
		int playerSecondSum = 0;
		int bankerFirstSum = 0;
		int bankerSecondSum = 0;
		
		System.out.println("-----------------------------------------------------");
		System.out.println("\t \t 바카라 게임을 시작합니다.");
		System.out.println("-----------------------------------------------------");
		
		System.out.println("카드를 뽑습니다 \n");
		
		for (int i = 0; i < 2; i++) {
			if (i == 0) {
				System.out.println("플레이어의 첫 번째 카드는 "+player.Cards(i)+" 입니다.");  // player가 뽑은 첫 번째 카드 출력
			}
			else if (i == 1) {
				System.out.println("플레이어의 두번째 카드는 "+player.Cards(i)+" 입니다.");  // player가 뽑은 두 번째 카드 출력
			}
		}
		System.out.println("\n");
		for (int i = 0; i < 2; i++) {
			if (i == 0) {
				System.out.println("딜러의 첫 번째 카드는 "+banker.Cards(i)+" 입니다.");  // banker가 뽑은 첫 번째 카드 출력
			}
			else if (i == 1) {
				System.out.println("딜러의 두번째 카드는 "+banker.Cards(i)+" 입니다.");  // banker가 뽑은 두 번째 카드 출력
			}
		}
		System.out.println("\n");
		playerFirstSum = player.getCardSum();
		bankerFirstSum = banker.getCardSum();
		playerSecondSum = player.getCardSum2();
		bankerSecondSum = banker.getCardSum2();
		
		System.out.println("플레이어의 카드 합은 "+playerFirstSum+" 입니다.");  // player의 첫 번째와 두 번째 카드값의 합 출력
		System.out.println("딜러의 카드 합은 "+bankerFirstSum+" 입니다. \n");  // banker의 첫 번째와 두 번째 카드값의 합 출력
		System.out.println(player.gameStart(playerFirstSum, playerSecondSum, bankerFirstSum, bankerSecondSum));  // BacarratGameStart의 조건에 맞게 실행
		}
}
```

----

### 결과 출력하기

----

#### 첫 번째 게임

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgame.PNG>

#### 두 번째 게임

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgame02.PNG>
