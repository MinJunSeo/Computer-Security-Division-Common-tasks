# Dialog procedure's return value
  
대화상자 프로시저는 BOOL형 값을 통해 메시지 처리 여부를 반환한다. 이 반환값은 시스템의 숨겨진 윈도우 프로시저가 받으며 이 값을 통해 디폴트 처리 여부를 결정한다.  
  
반환값이 BOOL형이기 때문에 반환값을 원하는 메시지에 대해 처리 결과를 반환할 방법이 없다. 숨겨진 윈도우와 반환값을 통해 통신하는 것이지 운영체제와는 통신하지 않기 때문이다.  
  
대화상자 프로시저에서 처리 결과를 운영체제에게 보고하고 싶다면 다음의 방법을 활용하면 된다.  
`SetWindowLongPtr` 함수로 `DWLP_MSGRESULT`에 반환하고자 하는 값을 저장한 뒤, `TRUE`를 반환하면 된다.  
혹은 `DefWindowProc` 함수를 바로 호출해 그 결과값을 반환하는 방법도 활용할 수 있다.  

대표적으로 WM_NCHITTEST, LVN_BEGINLABELDIT 메시지와 같이 반환값에 중요한 의미가 담겨져 있을 경우 이러한 방법을 활용해야 한다.    
또한 일반 윈도우의 차일드와 대화상자의 차일드를 처리하는 방법이 조금 다르기 때문에 이런 처리를 할 때도 주의가 필요하다.
