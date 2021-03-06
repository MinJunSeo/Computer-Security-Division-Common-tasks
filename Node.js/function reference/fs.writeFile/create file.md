# 파일 생성하기
  
자신이 가지고 있는 데이터를 토대로 파일을 만들고 싶을 때는 fs에 있는 writeFile 함수를 사용하여 파일을 생성할 수 있다.  
  
    fs.writeFile(file, data[, options], callback)
  
인자 `file`은 파일 이름을 지정한다. 확장자를 같이 지정하면 해당 확장자로 파일을 만들 수 있지만 생략하면 txt 파일로 생성된다. 저장 위치를 지정할 수도 있다.  
  
    // Example
    fs.writeFile("data/Nodejs.txt", ...)
  
위 경우 현재 코드를 작성 중인 js 파일의 디렉토리 안에 있는 data 폴더 안에 Nodejs.txt 라는 이름의 파일을 생성한다는 뜻이다.  
  
인자 `data`는 해당 파일에 저장될 내용을 지정하면 된다. 문자열을 바로 넣을 수도 있지만, 변수를 지정할 수도 있다. 변수를 지정하면 변수에 저장되어 있는 값이 들어가게 된다.  
  
인자 `options`는 필수적으로 해야 하는 것은 아니지만, 기본적으로 **"utf8"**로 지정하는 것이 호환성면에서 굉장히 유리하다. 필수적으로 하는 것을 권고하고 싶다.  
  
인자 `callback`은 당연히 콜백 함수를 지정하는 곳이다. 이 콜백 함수는 인자로 err를 가지며, 에러가 발생했을 때 이 인자에 에러가 전달되는 것 같다.  
  
이 콜백 함수가 실행된다는 것은 파일을 읽는 것이 모두 종료되었다는 뜻이므로 오류 검사나 혹은 정상 종료를 처리하는 코드를 넣으면 적절하다.  
  
# 리다이렉션
  
사용자를 현재 작업하던 페이지에서 강제로 다른 페이지로 전송시키는 기법을 리다이렉션이라고 한다.  
  
보통 로그인 화면에서 로그인에 성공하면 메인 페이지로 이동하는 것과 같은 원리라고 볼 수 있다.  
  
사용자가 파일을 생성하면 생성된 파일 페이지로 이동하도록 하는 코드를 작성해 보자.  
  
    fs.writeFile(`data/${title}`, description, "utf8", function(err)
    {
        response.writeHead(302, {Location: `/?id=${title}`});
        response.end();
    });
  
`response.writeHead`에서 302라는 뜻은 사용자를 다른 페이지로 일시적으로 이동시키라는 뜻이다. 즉, 리다이렉션 시키라는 것을 의미한다.  
  
뒤에 오는 배열 형태의 데이터는 이동시킬 페이지를 의미하는데 쿼리 스트링을 주면 해당 페이지로 이동할 수 있다.(title은 생성된 파일 이름을 저장하고 있다고 하면 굉장히 편리하게 할 수 있다.)