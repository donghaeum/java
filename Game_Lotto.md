# java

## Lotto 번호 생성기


### 로또 만들어 보기

1 ~ 45까지의 수 중에서 서로다른 6개의 수를 추출하기

 
```
public class Lotto {
	private int[] ball;
	

	
	public Lotto() {
		ball = new int[6];		
	}
	
	// 로또를 만든다.
	public void make() {
		// 1~45까지의 수를 랜덤으로 가져오는 것을 처리
		// Math.random() 0.00000012022 ~ 0.99999999까지의 난수를 가져온다.
		// 1~45까지의 난수를 가져온다.
		int count = 0;
		while(true) {
			int num = (int)(Math.random()*45)+1;
			if (!isSame(ball,num)) {
				ball[count++]=num;// 0
			}
			if(count==6) {
				break;
			}
		}
	}

	// 랜덤으로 추출한 수가 지금 배열안에 들어있는지를 확인하는 메소드
	private boolean isSame(int[] ball, int num) {
		boolean isT = false;
		for (int i = 0; i < ball.length; i++) {
			if (ball[i]==num) {
				isT = true;
				break;
			}
		}
		return isT;
	}
	
	public int[] getBall() {
		return ball;
	}
	
	public void print() {
		for (int i : ball) {
			System.out.print(i+",");
		}
	}
}
```
