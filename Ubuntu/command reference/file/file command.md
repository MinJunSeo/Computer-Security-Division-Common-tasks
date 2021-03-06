# command about file system  
  
## pwd  
  
현재 디렉토리 경로를 화면에 출력하는 명령어입니다.  
  
## ls
  
현재 위치하고 있는 경로가 지니고 있는 디렉토리와 파일을 보여줍니다. ls 뒤에 옵션을 주기도 한다. 가장 많이 주는 옵션은 -l로, 자세히 보기 기능이다.  
  
## cd
  
이후 오는 경로로 현재 경로를 변경합니다. 다음과 같이 이미 정해져 있는 값을 통해 좀 더 경로 지정을 편리하게 할 수 있다.  
  
경로 표현 | 설명
----------|-----
../ | 현재 경로에서 바로 위 부모 경로를 나타냅니다.
./ | 현재 자신의 경로를 의미합니다.
~ | /home/userID(사용자 아이디)의 경로를 나타냅니다.
  
## mkdir
  
해당 경로에 디렉토리(폴더)를 생성합니다. `mkdir 폴더명`과 같은 형식으로 사용합니다.  
  
## mv
  
디렉토리 혹은 파일의 이름을 변경합니다. `mv 변경하고자 하는 디렉토리(또는 파일)명 새로운 이름`의 형식으로 사용합니다.  
  
파일의 경로를 이동할 때도 사용합니다.  
  
## touch
  
해당 경로에 빈 파일을 생성합니다. `touch 파일명`과 같은 형식으로 사용합니다. 파일명을 사용할 때 확장자 명을 지정할 수 있습니다. 물론 지정하지 않아도 파일은 생성됩니다.  
  
## cp
  
지정한 파일과 동일한 내용을 지닌 파일을 같은 경로에 생성합니다. 파일 확장자명이 다를 수 있습니다. `cp 원본 파일 이름 사본 파일 이름`의 형식으로 사용합니다.
  
## rm
  
파일을 삭제하는 명령어입니다. 디렉토리를 대상으로 삭제하기 위해서는 특정한 옵셔을 줘야 하는데 그 중 일부가 다음과 같습니다.  
  
옵션 | 설명
-----|-----
-r | 해당 디렉토리 아래에 있는 모든 데이터들과 해당 디렉토리를 모두 삭제합니다.
-ri | 해당 디렉토리 아래에 있는 모든 데이터들과 해당 디렉토리를 대상으로 삭제할 것인지 묻습니다. 이때 y라 대답하면 삭제하며 n이라 하면 삭제하지 않습니다.
  
## rmdir
  
디렉토리를 삭제하는 명령어입니다. 디렉토리가 비어있지 않으면 삭제하지 않습니다.  
