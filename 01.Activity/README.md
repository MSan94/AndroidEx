# 액티비티
- 사용자가 직접 보고 입력하는 화면을 담당하는 컴포넌트
- 액티비티 컴포넌트를 구성하는 핵심 요소는 컨텍스트

## 컨텍스트
- 액티비티, 서비스등의 컴포넌트와 스피너, 리사이클러뷰와 같은 화면 요소를 사용하기 위해서는 컨텍스트가 필요
- 시스템을 사용하기 위한 정보 (Property)와 도구(Method)가 담겨 있는 클래스
- 컨텍스트는 컴포넌트 실행 시 함께 생성되며, 생성된 컴포넌트가 가지고 있는 메서드를 호출해서 각각의 도구를 사용할 수 있다.
- 안드로이드에서의 컨텍스트는 앱을 실행하기 위해 잘 짜여진 설계도의 개념으로 앱에서 사용하는 기본 기능이 담겨있는 기본 클래스이다.
- 액티비티는 컨텍스트를 상속받아 구현된다.


'''
public abstract class Context {} 
public class ContextWrapper extends Context {}
public class ContextThemeWrapper extends ContextWrapper {}
public class Activity extends ContextThemeWrapper{}
public class ComponentActivity extends Activity{}
public class ComponentActivity extends androidx.core.app.ComponentActivity{}
public class FragmentActivity extends ComponentActivity{}
public class AppCompatActivity extends FragmentActivity{}
class MainActivity : AppCompatActivity() {}
'''
