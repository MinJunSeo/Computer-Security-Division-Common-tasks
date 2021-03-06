# input
  
## 문자열 입력받기
  
파이썬에서 사용자에게 입력을 받는 함수로 가장 대표적인 함수는 바로 input 함수이다.  
  
	input()
  
이 함수 호출 시 사용자에게 문자열이 입력되고 Enter 키가 눌려질 때까지 사용자의 입력을 기다리는 함수이다. 기본적으로 자료를 저장하지 않으면 입력한 데이터는 사라지게 된다.  
  
저장을 위해 변수를 사용하는데 변수를 만들고 초기화하는 과정에서 바로 input 함수를 호출해도 된다.  
  
	str = input()
  
이렇게 되면 사용자가 입력한 문자열이 str에 저장된다.  
  
## 문자열 연결하기
  
문자열을 동시에 연결해야 할 때가 생길 때가 있다.(특수한 조건에 따라 추가로 도움말이 제공된다 등의 상황) 이럴 때 문자열을 연결하기 위해서 C언어는 strcat 같은 함수를 사용하겠지만 파이썬은 + 연산자만 사용해서 간단하게 연결할 수 있다.  
  
	str = "Student number : "
	studentNum = "2409"
	
	print(str + studentNum)
  
이렇게 하면 실행 결과로 Student number : 2409 가 출력된다.  
  
## 입력 시 문자열 출력하기
  
보통 C언어에서 scanf 함수 등의 입력 함수를 활용하면 화면에 아무런 문자가 출력되지 않고 입력 대기를 위해 커서만 깜박거리는 현상이 발생한다. 처음에 이런 현상을 보면 입력하라고 알 수도 있지만 프로그램이 멈춰버린 것 같이 보일 수도 있다. 그래서 보통은 printf 등의 출력 함수를 통해 문자열로 안내를 해 주는 코드를 짜게 된다.  
  
	printf("문자열을 입력하세요. : ");
	scnaf("%s", str);
  
파이썬은 이러한 두 줄의 코드를 한 줄로 작성할 수 있다. input 함수의 인자로 문자열을 주면 해당 문자열이 화면에 출력된 뒤, 입력을 받을 수 있다.  
	str = input("문자열을 입력하세요. : ")
  
## 두 개의 문자열 동시에 입력받기
  
프로그램을 작성하다 보면 사용자에게서 문자열 두 개를 동시에 입력받아야 하는 상황이 올 때가 있다. 그럴 때 파이썬은 split 함수를 사용하여 문자열을 동시에 입력받을 수 있다.  
  
	input("두 개의 문자열을 입력하세요. : ").split()
  
이렇게 되면 문자열이 공백을 기준으로 나누어지게 된다. 무슨 말이냐면 사용자가 "코딩 도장"으로 문자열을 입력하였을 때 공백을 기준으로 두 개의 문자열로 분할한다. 그래서 input에서는 "코딩"과 "도장"으로 나뉘어 문자열이 반환된다.  
  
그렇다면, 저렇게 나누어진 두 개의 문자열을 어떻게 저장할 수 있을까? 그냥 놔두면 사라지는 데이터이니 활용하기 위해서는 변수에 저장하는 것은 필수적이다. 방법은 변수 두 개를 생성하고 초기화하면 된다.  
  
	str1, str2 = input("두 개의 문자열을 입력하세요. : ").split()
  
사용자가 "코딩 도장"이라는 문자열을 입력하였을 때 split 함수에 의해 문자열은 "코딩"과 "도장"으로 나누어진다. 그럼 먼저 만들어진 변수인 str1에 먼저 나누어진 문자열인 "코딩"이 들어가게 되고, str2에는 "도장"이 들어가게 된다.  
  
## ,로 문자열 구분하기
  
그런데 문자열을 입력받을 때 공백을 기준으로 두 개의 문자열로 구분해버리면 꽤나 큰 불편함이 있다. 보통 문자열이라는 것은 문장을 표현하고 싶을 때도 많은데 공백 문자로 구분해버리면 띄어쓰기를 포함한 문자열을 얻을 수 없게 되어버린다. 이러한 점을 해결하기 위해 split에 인자로 구분의 기준이 되는 문자열을 전달하면 해당 문자열로 두 개의 문자열을 구분할 수 있다.  
  
	str1, str2 = input("두 개의 문자열을 입력하세요. : ").split(',')
  
저렇게 작성된 코드는 입력 시 ,가 있는 위치를 기준으로 두 개의 문자열로 나누게 된다. 예를 들어 사용자가 "파이썬,코딩 도장"이라고 문자열을 입력하였다면 str1에는 "파이썬"이, str2에는 "코딩 도장"이 들어가게 된다.  
  
## 정수나 실수 입력 받기
  
input 함수가 사용자에게서 입력을 받을 수 있는 함수지만 단점이 하나 있다면 입력받는 데이터는 모두 str 클래스, 즉 문자열로 반환된다는 점이다. 즉, 내가 숫자를 입력받고 싶어서 다음과 같은 코드를 작성하고,  
  
	num = input("숫자를 입력하세요.")
  
입력 시 2409를 입력했다. 그 뒤, 해당 데이터의 type을 출력해보면,  
  
	print(type(num))
  
출력 결과로 <class 'str'>가 출력된다. 즉, 입력된 2409라는 숫자가 "2409"라는 문자열로 저장되었다는 것이다. 프로그램을 짜다 보면 문자열 입력뿐만이 아니라 정수나 실수의 데이터 그 자체를 받고 싶은 경우도 상당히 많다. 하지만 input 함수를 그냥 사용하면 정수나 실수 데이터를 얻을 수 없다. 이러한 문제점을 해결할 수 있는 방법은 두 가지가 있다.  
  
1. 사용 시 형변환을 한다.  
  
파이썬은 문자열을 형변환할 때 만약 해당 문자열이 정수로만 이루어져있거나 실수로만 이루어져 있다면 해당 데이터로 형 변환이 가능하다. 무슨 말이냐 하면,  
  
	num = "2409"
	print(int(num) + 1)
  
을 하면 2410이 출력된다는 것이다. 즉, 문자열을 정수형 데이터로 형변환이 가능하다는 것이다. 하지만, 이러한 방법은 사용할 때마다 형변환을 해줘야 하는 불편함이 있다.  
  
2. map 함수를 이용한다.  
  
map 함수를 이용하면 input 함수로 입력을 받을 때 어떠한 자료형으로 저장할 지를 결정할 수 있다. 여기서 자료형을 int로 지정하면 정수형으로 저장할 수 있고 float로 지정하면 실수 형으로 저장할 수 있다.  
  
	num = map(int, input("숫자를 입력하세요. : "))
  
이렇게 코드를 작성하면 input에서 입력받는 값을 모두 int 형으로 num에 저장한다.
