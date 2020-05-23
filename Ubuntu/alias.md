# 명령어 별칭 만들어 사용하기
  
Linux에서 사용하는 명령어는 기본적으로 명령어 이름과 다양한 옵션들로 이루어져 있다. 그런데 프로그래밍을 하면서 자주 사용하는 명령어가 너무 길다면 매번 타이핑하는데 너무 힘들 것이다.  
  
그럴 때는 명령어에 별칭을 붙여 짧게 사용하는 것도 가능하다. `alias` 명령어를 사용하면 이를 할 수 있다.  
  
	alias 명령어='명령어 형태'
  
alias 뒤에 명령어를 입력한다. 이때 옵션을 모두 포함시켜야 한다. 그 뒤 바꿀 형태를 ''로 감싸주면 바꿀 수 있다. 단, 이 변경 또한 일시적인 변경이기 때문에 재부팅하거나 로그아웃하면 원래대로 돌아온다.  