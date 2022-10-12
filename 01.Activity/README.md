# 액티비티
- 사용자가 직접 보고 입력하는 화면을 담당하는 컴포넌트
- 액티비티 컴포넌트를 구성하는 핵심 요소는 컨텍스트

## 컨텍스트
- 액티비티, 서비스등의 컴포넌트와 스피너, 리사이클러뷰와 같은 화면 요소를 사용하기 위해서는 컨텍스트가 필요
- 시스템을 사용하기 위한 정보 (Property)와 도구(Method)가 담겨 있는 클래스
- 컨텍스트는 컴포넌트 실행 시 함께 생성되며, 생성된 컴포넌트가 가지고 있는 메서드를 호출해서 각각의 도구를 사용할 수 있다.
- 안드로이드에서의 컨텍스트는 앱을 실행하기 위해 잘 짜여진 설계도의 개념으로 앱에서 사용하는 기본 기능이 담겨있는 기본 클래스이다.
- 액티비티는 컨텍스트를 상속받아 구현된다.
``` 
public abstract class Context {} 
public class ContextWrapper extends Context {}
public class ContextThemeWrapper extends ContextWrapper {}
public class Activity extends ContextThemeWrapper{}
public class ComponentActivity extends Activity{}
public class ComponentActivity extends androidx.core.app.ComponentActivity{}
public class FragmentActivity extends ComponentActivity{}
public class AppCompatActivity extends FragmentActivity{}
class MainActivity : AppCompatActivity() {}
``` 
- 액티비티 처럼 컨텍스트를 상속받은 컴포넌트들은 코드상에서 baseCOntext를 호출하는 것만으로 안드로이드의 기본 기능을 사용할 수 있다.


## 컨텍스트 종류
- Appication context 
  - 애플리케이션과 관련된 핵심 기능을 담고 이쓴ㄴ 클래스
  - 앱을 통틀어서 하나의 인스턴스만 생성
  - 액티비티나 서비스 같은 컴포넌트에서 applicationContext를 직접 호출해서 사용할 수 있는데 호출 하는 지점과 관계없이 모두 동일한 컨텍스트를 호출
- Base Context
  - 4대 컴포넌트인 액티비티, 서비스, 컨텐트 프로바이더, 브로드캐스트 리시버의 기반 클래스
  - 각각의 컴포넌트에서 baseContext 또는 this로 컨텍스트를 사용할 수 있다
  - 컴포넌트의 개수만큼 컨텍스트도 함께 생성되기 때문에 호출되는 지점에 따라 서로 다른 컨텍스트가 호출
