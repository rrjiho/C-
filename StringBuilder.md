## String

### String (Immutable - 불변 객체)
- 불변성: `String` 객체는 **불변**으로 한 번 생성된 문자열은 변경할 수 없다. 수정하려고 하면 새로운 `String` 객체가 생성되고 기존의 객체는 변경되지 않고 남아있다.
- `new String` 사용해서 문자열을 만들면 명시적으로 새로운 `String` 객체를 생성한다. 하지만 일반적으로 문자열 리터럴을 사용할 때는 **컴파일러**가 `String Pool`을 사용하여 동일한 문자열을 공유하도록 최적화 한다.

```C#
string s1 = "hello";
string s2 = "hello";
// s1과 s2는 같은 문자열 리터럴을 가리킴 (String Pool 덕분에)

string s3 = new String("hello");
// s3는 새로운 객체로 생성됨, String Pool에 상관없이 다른 참조를 가짐
```

- 성능: `String`은 `불변성`으로 인해 문자열을 수정할 때 새로운 객체를 매번 생성하므로 반복적인 수정이 필요할 때 성능이 저하될 수 있다.
- 주요 용도: `String`은 변하지 않는 문자열 데이터를 처리할 때 주로 사용함. 예) 텍스트 메시지, 파일 경로, 고정된 데이터를 저장할 때 적합하다.



### StringBuilder (Mutable - 가변 객체)
- 가변성: `StringBuilder`는 **가변** 객체로 문자열을 효율적으로 수정할 수 있도록 설계. 문자열을 추가, 수정, 삭제할 때 새로운 객체를 생성하지 않고 내부적으로 동일한 버퍼에서 작업을 수행한다.

```C#
StringBuilder sb = new StringBuilder();
sb.Append("hello");
sb.Append(" ");
sb.Append("world");
string result = sb.ToString();
// 새로운 객체를 만들지 않고 수정함
```

- 성능: `StringBuilder`는 여러 번 문자열을 수정하거나 연결할 때 유리하다. 새로운 객체를 계속 생성하지 않고 내부 버퍼에서 작업을 하므로, 특히 많은 문자열 조작이 필요할 때 메모리와 성능 면에서 효율적이다.
- 주요 용도: `StringBuilde`r는 문자열을 반복적으로 조작하거나 연결하는 경우에 적합하다. 예) 대량의 데이터를 처리하거나 루프 내에서 문자열을 계속 수정하는 경우 StringBuilder를 사용하면 성능을 크게 개선할 수 있다.


#### 이를 통해 작은 문자열 작업에는 String이 적합하고 대규모 또는 반복적인 작업에는 StringBuilder가 더 효율적임을 알 수 있다.

