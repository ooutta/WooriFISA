<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드1.PNG" width="600px">
</div>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드2.PNG" width="600px">
</div>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드3.PNG" width="600px">
</div>
<p>
어떤 개념이든, 프레임워크든 기술의 탄생 배경과 이유를 알게 된다면 그 개념의 핵심을 파악할 수 있었습니다.

또 웹을 개발하면서 웹이 어떻게 지금 형태까지 오게 되었는지 의문을 갖게 되습니다.
그래서 웹의 발전 과정에 대해 정리하게 되었습니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드4.PNG" width="600px">
</div>
<p>
웹이 처음 등장했던 1세대 웹 서비스들은 모두 정적인 웹사이트였습니다.
여기서 정적이라는 건 움직이지 않는, `언제 접속해도 같은 화면을 보여주는 것`을 의미합니다.
아래 회사 소개 페이지도 정적 웹의 대표적인 예시입니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드5.PNG" width="600px">
</div>
<p>
웹 서버는 개발자가 서버에 미리 작성해놓은 HTML, CSS, JS 코드들을 그대로 클라이언트에게 전송합니다. 그렇기에 `모든 유저는 동일한 웹 페이지를 보게` 됩니다.
  
저는 공부하면서 JS로 만들어지는 타이머같은 기능이 동적이라고 생각이 들었는데, JS도 결국은 웹페이지에 접속할 때마다 받게 되는 소스 코드, 이미지 등의 파일들은 변경되지 않고 같기 때문에 정적 웹이라고 합니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드6.PNG" width="600px">
</div>
<p>
하지만, 웹을 이용하는 사람이 많아지면서, 점점 유저들은 로그인 한 내 이름을 보여주는 등의 사용자 요청에 따라 달라져야 하는 동적 페이지를 제공받길 원하게 됩니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드7.PNG" width="600px">
</div>
<p>
이렇게 사람마다 다른 요청을 처리해주기 위해서 `CGI`가 등장했습니다.
  
CGI의 사전적 의미는 `동적 데이터를 처리하는 인터페이스`입니다.
가운데 Web Server는 Apache이고, 오른쪽은  C, Perl과 같은 여러 언어를 사용해서 만든 프로그램입니다.
하지만 프로그램마다 개발된 언어가 다르기 때문에 `웹 서버와 통신하기 위해서는 둘 간의 규약`이 필요했습니다.

CGI 규칙을 지켜서 프로그램을 개발하면, 웹 서버는 클라이언트의 요청이 들어올때 `각각의 프로세스를 만들어서 프로그램을 호출`합니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드8.PNG" width="600px">
</div>
<p>
하지만 `프로세스는 각자의 공간을 지니고 생성되는 시간이 오래 걸려서 서버가 더 많은 리소스를 부담`해야 합니다.
이러한 단점을 개선하기 위한 방법으로 프로세스를 스레드로 변경하게 됩니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드9.PNG" width="600px">
</div>
<p>
`스레드`는 같은 프로세스 내에 있는 다른 스레드와 메모리를 공유하고, 프로세스에 비해 생성 시간도 적게 걸립니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드10.PNG" width="600px">
</div>
<p>
CGI의 두번째 문제점은 `같은 요청이어도 스레드가 다르면 중복된 CGI 프로그램을 생성`한다는 것입니다.

매번 객체를 생성하고 종료하는 작업은 필요 없는 서버 리소스를 불필요하게 낭비하는 구조입니다.
그래서 이렇게 프로그램을 중복되게 생성하는 것이 아닌
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드11.PNG" width="600px">
</div>
<p>
`싱글톤 패턴`을 적용해서 `하나의 동일한 CGI 프로그램을 호출`하는 방식으로 개선하게 됩니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드12.PNG" width="600px">
</div>
<p>
이처럼 첫번째 문제인 CGI의 요청마다 프로세스를 매번 생성하는 문제, 두번째 문제인 동일한 요청이라도 중복된 프로그램을 생성하는 문제를 해결한 프로그래밍 기법을 `Servlet`이라고 합니다.

서블릿을 통해 우리는 서버가 부담해야 할 리소스를 줄이면서, 보다 효율적으로 동적 데이터를 클라이언트에게 제공할 수 있게 되었습니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드13.PNG" width="600px">
</div>
<p>
여기서 Servlet Container는 Web Container와 같은 의미로,
3개의 요청이 들어오면 요청마다 Thread를 생성하고, Thread와 Servlet 구현체를 연결해 주고, Servlet의 메서드를 호출해주는 역할을 합니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드14.PNG" width="600px">
</div>
<p>
하지만 `Java 파일 안에 HTML 코드`를 넣는 건 너무 복잡하고 보기 어렵습니다. 그리고 자바 파일을 수정하는 것이기 때문에, 코드를 수정하면 다시 컴파일하고 다시 배포해야 합니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드15.PNG" width="600px">
</div>
<p>
이러한 배경에서 `JSP`가 등장하게 됩니다. JSP는 Servlet과 반대로, `HTML 태그 안에` 이러한 기호(%)를 사용해서 `자바 코드를 작성`합니다. 또한 코드 수정 후 재배포가 필요한 Servlet과 달리, JSP는 파일 수정 후 재배포할 필요가 없습니다. 그리고 JSP 파일이 실행되면 결국 Servlet으로 변환되어 기능을 수행합니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드16.PNG" width="600px">
</div>
<p>
이제 Servlet과 JSP가 어떤 부분에서 차이점을 갖는지 살펴보겠습니다.
코드 작성 구조를 기준으로는 `Servlet은 HTML이 Java에` 들어있고, `JSP는 Java가 HTML`에 들어있습니다.
유용한 작업 관점에서 보면  `Servlet은DB와 통신하고 비지니스 로직을 처리`하는 등의 기능에 유용합니다. 따라서 MVC 패턴에서 Controller 역할로 사용합니다. `JSP는 tag를 이용한 Presentation Logic 처리`에 적합합니다. 따라서 MVC 패턴에서 View 역할로 사용합니다.
파일을 수정 후 배포하는 과정에서 보면 `Servlet은 전체 코드를 다시 컴파일하고 배포`해야하기 때문에 개발 생산성이 저하됩니다. `JSP는 재배포를 할 필요 없이` WAS가 수정된 부분을 알아서 업데이트 해주기 때문에 쉬운 배포가 가능합니다.
</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드17.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드18.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드19.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드20.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드21.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드22.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드23.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드24.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드25.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드26.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드27.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드28.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드29.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드30.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드31.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드32.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드33.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드34.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드35.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드36.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드37.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드38.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드39.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드40.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드41.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드42.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드43.PNG" width="600px">
</div>
<p>

</p>
<br>

<div align='center'>   
    <img src="../img/tech_seminar_back_end/슬라이드44.PNG" width="600px">
</div>
<p>

</p>
