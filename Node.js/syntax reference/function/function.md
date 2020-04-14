# function
  
코드 내에서 반복적으로 등장하는 코드이나 반복되는 구간이 명확하게 지정되어 있지 않아 임의의 장소에 등장할 수 있는 반복되는 코드는 함수로 만들어 사용하는 것이 좋다.  
  
함수를 만들기 위해서는 우선 맨 앞에 `function`이라는 키워드를 입력해야 한다. 이 키워드는 이 다음에 나오는 구문이 함수라는 것을 컴파일러에게 알려주는 역할을 한다. 가장 기본적인 틀은 다음과 같다.  
  
	// Example
	function f()
	{
		코드;
	}
  
function 키워드 뒤에 나온 f는 해당 함수의 이름이 된다. 그래서 이 함수를 호출할 때는 이 함수의 이름인 f를 활용하여 `f();`와 같이 호출한다.  
  
함수를 만들면 같은 이름의 함수는 반드시 같은 코드임을 확신할 수 있어 가독성이 좋아지고, 해당 구문을 고치기 위해서 함수의 원형 부분만 고쳐주면 고쳐진 원형으로 함수가 실행되기 때문에 유지, 보수가 편리해진다.  
  
## 내장 함수
  
JavaScript가 기본적으로 내장하고 있는 함수를 말한다. 내장 객체에 저장되어 있는 경우도 있다. 내장 함수는 제약 없이 조건만 맞추면 해당 함수를 호출할 수 있다.  
  
	// Example
	Math.round(1.6); // 2
	Math.round(1.4); // 1
  
Math는 내장 객체이며 round는 인수로 전달된 값을 반올림하여 반환해주는 함수이다.  
  
## 인수를 가지는 함수
  
내장 함수 round와 같이 함수에는 인수를 전달할 수 있다. 두 값을 인수로 전달받아 두 인수의 합을 출력하는 sum이라는 함수를 만들어보면서 설명한다.  
  
	function sum(first, second)
	{
		console.log(first + second);
	}
  
다음고 같이 정의하면 sum이라는 함수를 호출할 때 처음으로 준 값이 first에, 두 번째로 준 값이 second에 전달되어 변수로써 활용할 수 있게 된다. 이렇게 함수 안으로 값을 전달하는 변수를 매개변수라고 한다.  
  
참고로, `sum(1, 2);`에서 1과 2는 인자라고 한다.  
  
## 값 반환하기
  
함수 내에서 출력하는 것보다는 값을 반환하는 것이 더 다양한 상황에서 자유롭게 사용할 수 있다. 위에서 만든 함수 sum이 만약 값을 반환하는 함수라면, 해당 값을 콘솔에 출력하기 위해서는 `console.log(sum(2, 4));`라고 입력해야 하는 번거로움이 있지만, 다음과 같은 상황에서는 더 큰 이득을 볼 수 있다.  
  
1. 변수에 값을 초기화하기 위해 활용할 수 있다. (예 : `var num = sum(2, 4);`)  
2. 조건식으로 활용할 수 있다. (예 : `if(sum(3, 5)){}`)  
3. 다른 곳으로의 출력에도 활용할 수 있다. (예 : `email("aaa@naver.com", sum(1, 0));`)  
  
함수에서 값을 반환하기 위해서는 `return` 키워드를 사용하면 된다.  
  
	// Example
	function sum(first, second)
	{
		return first + second;
	}
  
함수가 `return` 키워드에 의해 반환되면 함수가 종료되기 때문에 `return`문 이후로 작성되어 있는 코드는 실행되지 않는다.  