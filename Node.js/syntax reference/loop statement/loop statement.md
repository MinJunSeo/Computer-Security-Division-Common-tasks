# loop statement
  
프로그램 상에서 반복되는 일을 손쉽게 할 수 있도록 도와주는 제어문의 일종이다.  
  
## while
  
	while(조건식)
	{
			코드;
	}
  
if 제어문과 키워드만 달라지고 형식은 동일하다. () 안의 조건식의 값이 `true`일 때에 한해 {} 안에 있는 코드를 반복해서 실행한다. {} 안의 코드를 한 번 모두 실행하고 나면 () 안의 조건식을 검사해 값이 `true`인지 계속 검사한다. 이때 값이 `true`가 아니라면 반복문을 나가게 된다.  
  
## for
  
	for(변수 초기화; 조건식; 변수 증감식)
	{
		코드;
	}
  
for는 다른 반복문과 달리 () 안에 쓰는 식이 총 3개나 된다. 처음에는 제어 변수의 초기화를 할 수 있다. 물론 여기서 새로운 제어 변수를 선언함과 동시에 초기화할 수 있다. 반드시 초기화를 끝낸 뒤, `;`을 찍어야 한다.  
  
두 번째로는 조건식을 제시해야 한다. 조건식의 값이 `true`일 때만 반복문이 실행된다. 조건식을 제시한 후 반드시 `;`을 찍어야 한다.  
  
마지막으로 제어 변수의 증감식을 설정할 수 있다. 제어 변수가 루프를 한 번 돌고 나면 얼마만큼 증가하거나 감소할지 결정함으로써 반복 횟수를 제어할 수 있다.  
  
## do ~ while
  
	do
	{
		코드;
	}while(조건식)
  
C언어와는 달리 while의 뒤에 `;`을 붙이지 않는다는 점이 특징이다. while의 조건식이 `true`일 때 반복문을 계속 반복한다.  
  
do ~ while문은 다른 반복문과 다르게 **무조건 1번은 실행된다.** while의 조건식으로 `false`를 줘도 {} 안의 반복문이 한 번은 실행된다는 뜻이다. 그래서 어떠한 상황에서도 한 번은 실행되어야 하는 구문을 do ~ while로 사용하는 것이 좋다.  
  
## 무한 루프
  
	while(true)
	{
		코드;
	}
  
다음과 같이 반복문의 조건식이 항상 참이어서 계속 반복문을 반복하는 구문을 무한 루프라고 한다. 그냥 두면 반복문이 끝나지 않기 때문에 CPU 독점 문제로 이어지게 된다. 그래서 반드시 {} 안에 반복문의 탈출 조건을 명시하여야 한다.