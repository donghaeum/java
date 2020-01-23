# Java

## Bacarrat Card Game 2

Scanner를 추가하여 만들어보기

----

### Bacarrat Card Game Rule
1) Player와 Banker 중 하나를 선택 합니다.

2) Player와 Banker는 각각 2장의 카드를 받습니다.

3) 각각 2장의 카드의 숫자를 더해 1의자리 숫자가 9에 가까운 쪽이 이깁니다.
    - Ace는 1로 King, Queen, Jack, 10은 각각 0으로 계산합니다.

    - ex) Player의 카드 : Ace, 8 | Banker의 카드 : 7, Jack 일 때 Player의 카드 합 : 9 | Banker의 카드 합 : 7 이므로 Player 승리
    
4) 카드의 합이 5 이하일 경우

    - Player의 카드 합이 5 이하일 경우
      - Player만 카드를 한장 더 뽑습니다.
      
    - Banker의 카드 합이 5 이하일 경우
      - Banker만 카드를 한장 더 뽑습니다.
      
    - Player와 Banker의 카드 합이 5 이하일 경우
      - Player와 Banker 모두 카드를 더 뽑습니다.
      
5) 게임이 끝난 후 재경기 또는 경기 종료를 선택 할 수 있습니다.

----
#### Scanner를 import 시켜 입력 값을 줄 수 있게 만든다.
```
import java.util.Scanner;   // Scanner를 import 시켜준다.

public class BacarratCardGame {
	public static void main(String[] args) {		
		BacarratGameStart player = new BacarratGameStart();
		BacarratGameStart banker = new BacarratGameStart();
		
		Scanner scanner = new Scanner(System.in);
		
		int playerFirstSum = 0;
		int playerSecondSum = 0;
		int bankerFirstSum = 0;
		int bankerSecondSum = 0;
		boolean game = true;
		
		System.out.println("-----------------------------------------------------");
		System.out.println("\t \t Bacarrat Game Start");
		System.out.println("-----------------------------------------------------");
		
		while(game) {
			System.out.println("Select Player \n(1) Player \n(2) Banker");    // 1을 입력하면 player, 2를 입력하면 banker를 선택
			int select = scanner.nextInt();   // 값 입력
			
			System.out.println("Draw a card \n");
```

#### time sleep 다음 값 출력 전까지 시간을 준다

```
    try {
			Thread.sleep(1000);
    } catch (InterruptedException e) {
	    System.out.println(e.getMessage());
    }
```

#### player와 banker의 카드 오픈

```
			System.out.println("Open card \n");
			
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				System.out.println(e.getMessage());
			}
  
// player의 첫 번째와 두 번째 카드
			for (int i = 0; i < 2; i++) {
				if (i == 0) {
					System.out.println("Player 1st card : "+player.Cards(i));
				}
				else if (i == 1) {
					System.out.println("Player 2nd card : "+player.Cards(i));
				}
			}
			
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				System.out.println(e.getMessage());
			}
			System.out.println("\n");
// banker의 첫 번째와 두 번째 카드
      for (int i = 0; i < 2; i++) {
				if (i == 0) {
					System.out.println("Banker 1st card : "+banker.Cards(i));
				}
				else if (i == 1) {
					System.out.println("Banker 2nd card : "+banker.Cards(i));
				}
			}
			
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				System.out.println(e.getMessage());
			}
```

#### player와 banker의 카드 합을 가져온다

```
			System.out.println("\n");
			playerFirstSum = player.getCardSum();
			bankerFirstSum = banker.getCardSum();
			playerSecondSum = player.getCardSum2();
			bankerSecondSum = banker.getCardSum2();
			
			System.out.println("Player result : "+playerFirstSum);
			System.out.println("Banker result : "+bankerFirstSum+"\n");
			
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				System.out.println(e.getMessage());
			}
```

#### player와 banker 중 선택한 값에 따라 결과값 출력

```      
// player 선택
			if (select == 1) {			
				player.playerPlay(playerFirstSum, playerSecondSum, bankerFirstSum, bankerSecondSum);
				game = BacarratCardGame.playAgain();
			}
// banker 선택
			else if (select == 2) {
				banker.bankerPlay(playerFirstSum, playerSecondSum, bankerFirstSum, bankerSecondSum);
				game = BacarratCardGame.playAgain();
			}
		}// while
	}
```

#### 게임 종료 후 다시 재경기를 할 것인지 확인

```
	public static boolean playAgain() {
		boolean game = true;
		Scanner scan = new Scanner(System.in);
		
		System.out.println("Play Again? \n(1) Yes \n(2) No");  // 다시 게임을 하고 싶으면 1을 입력 그렇지 않으면 2를 입력
		
		int more = scan.nextInt();
    
// 2를 입력 시 게임 오버 출력 후 종료
		if (more == 2) {
			System.out.println("-----------------------------------------------------");
			System.out.println("\n \t\t      Game Over\n");
			System.out.println("-----------------------------------------------------");
			game = false;
		}
		return game; // 그렇지 않으면 게임 다시 시작
	}

	
}
```

----

### 결과

----

#### player 선택

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgamescanner01.PNG>

#### player로 게임 진행

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgamescanner02.PNG>

#### 재경기

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgamescanner03.PNG>

#### banker로 게임 진행

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgamescanner04.PNG>

#### 게임 종료

<img width=600 src=https://github.com/donghaeum/java/blob/master/image/cardgamescanner05.PNG>
