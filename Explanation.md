Explanation
===

## statefulwidget, statelesswidget
- Stateful Widget  
-위젯이 동작하는 동안 Data 변경이 필요한 경우  
화면을 다시 그려서 변경된 부분을 위젯에 반영하는 동적인 위젯  
-이벤트 또는 사용자 상호 작용에 의해 동작  
-setState가 발생 시 다시 Build하는 과정이 일어나며, 동적 화면 구현  

- Stateless Widget  
-화면이 로드될 때 한 번만 그려지는. State가 없는 위젯으로, 변경이 필요한 Data가 없는 것  
-이벤트 또는 사용자 상호 작용에 의해 동작하지 않음  
-한 번만 Build 과정 발생, 한 번 그려진 화면은 계속 유지됨. 성능 좋음  


## 바디: 컬럼, 차일드 로우
-column은 수직(세로), Row는 수평(가로) 방향으로 배치하는 위젯  
 column은 열 안에서 어떻게 배치할 지 결정  
 Row는 행 안에서 어떻게 배치할 지 결정  
-main은 위젯이 배치되는 방향 의미하고,  
 cross는 main의 반대 방향 의미  
-Row 위젯에서 main은 수평이고 cross는 수직  
 Column 위젯에서 main은 수직이고 cross는 수평  


## 버튼 만드는 방식, 버튼 테마, 레이즈드 버튼
- FlatButton, RaisedButton, OutlineButton  
  -> 각각 TextButton, ElevatedButton, OutlinedButton 으로 변화됨  
TextButton: 그냥 글씨!  
ElevatedButton: 버튼 강조하고 싶을 때! (그림자 효과처럼)  
OutlinedButton: 테두리!  


## answers 리스트. 초기값 -1 왜 -1?



## itemcount, itembuilder
-ListView.Builder를 만드는 방법에 필수적인 속성  
-플러터에서 ListView는 어느 정해진 공간안에 컨텐츠가 들어가고,  
그 컨텐츠의 사이즈가 부모(ListView)의 사이즈보다 커지면 자동으로 스크롤이 생기는 위젯 의미  
-ListView.Builder는 위젯  
안에 내용물이 많아지면 스크롤이 생긴다는 점은 같지만 내용물을 보여주는 내부 원리는 다름  
ListView.Builder 매우 많은 양의 리스트를 보여줄 때 유리  
동적으로 필요한 부분만, 보여줄 부분만 생성  
스크롤이 내려가면 그때서야 필요한 부분들 생성  
-ListView는 build 메소드가 실행될 때 한 번에 다 만들기 때문에 퍼포먼스 측면에서도 안좋고 실사용자가 많은 양의 리스트를 다 보지 않을 확률도 커져서 비효율적  
  -> ListView.Builder는 이런 부분들을 해결해줌  

- itembuilder  
-itembuilder에는 콜백함수를 지정해주어야 하고 그 콜백함수는 인수를 BuildContext와 Int를 갖고 있어야 함  
그리고 해당 콜백함수는 return으로 위젯을 해야함  
이 위젯이 ListView에 들어가게 됨  

- itemcount  
-itembuilder에 지정된 위젯 생성 콜백함수를 몇 번 실행할 것인지 정하는 역할  


## on tap //Handle your callback
touch action(InkWell 위젯)에 대한 옵션  
누르고 나서 뭘 할 건지?(글자를 보여준다거나 네비게이션 사용해서 페이지 넘긴다거나...)  


## setstate()
-플러터는 statefulwidget과 statelesswidget을 가지며  
statefulwidget만이 상태 가질 수 있음  
상태 정보 새로 반영하기 위해서는 setState가 실행되면서 build method가 재 실행돼서 화면이 rebuild 되어야 함  
 setstate의 원리  
setstate 안에 정의된 함수에 의해 값이 변경되는 변수 A,  
setState가 실행되면 해당 build method에서 A가 사용되는 모든 곳을 표시함  
  -> setstate에 의해 build method가 재실행되면 표시된 곳만을 찾아 UI 업데이트함  


## 컨테이너 edgeinsets
- 여백 지정 클래스  
-all 함수는 모든 방향에 대해 같은 값을 준다는 뜻,  
 only 함수는 방향 개별적으로 지정 가능  


## whitenoise
-Python 웹앱을 위한 매우 단순화된 정적 파일 제공  
-몇 줄의 구성으로 whitenoise를 사용하면 웹앱이 자체 정적 파일을 제공할 수 있으므로 아마존S3 등의 기타 외부 서비스에 의존하지 않고 어디서나 배포할 수 있는 독립형 단위가 됨  


## 시크릿키
Django 앱에는 암호화 서명이 필요한 것들이 많이 있으며  
시크릿키 설정은 이를 위해 사용되는 것  
암호화적으로 강력한 양의 엔트로피(컴퓨터가 추적하기 어려운)가 있어야 하고  
모든 Django 인스턴스 간에 고유해야 함  


## children
위젯 하위에 다수의 위젯 추가할 때 사용  


## scaffold
-기본 Material Design visual layout 구조 구현하는 데 사용  
-범용 모바일 애플리케이션을 만들기에 충분하며  
기능적이고 응답성이 뛰어난 앱을 만드는 데 필요한 거의 모든 것을 포함하고 있음  
일반적으로 앱 화면을 구성하기 위한 뼈대라고 생각하면 됨  
-Scaffold 생성 할 때 생성자 parameter에 Widget을 넘겨 줌으로써 기능 하나씩 추가  


## onPressed
버튼안에서 쓰여짐. 누르고 뭐할 건지!  
