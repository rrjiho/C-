## System.String 중 자주 사용되는 메서드

#### `Length`	문자열의 길이를 반환한다.  
#### `ToUpper()`	문자열을 대문자로 변환한 새 문자열을 반환한다.  
#### `ToLower()`	문자열을 소문자로 변환한 새 문자열을 반환한다.
#### `Contains(string value)`	문자열에 특정 문자열이 포함되어 있는지 여부를 반환한다.
#### `IndexOf(string value)`	문자열 내에서 특정 문자열의 첫 번째 위치를 반환한다.
#### `LastIndexOf(string value)`	문자열 내에서 특정 문자열의 마지막 위치를 반환한다.
#### `Substring(int startIndex)`	지정된 위치부터 끝까지의 부분 문자열을 반환한다.
#### `Substring(int startIndex, int length)`	지정된 위치에서 시작해 주어진 길이만큼의 부분 문자열을 반환한다.
#### `Replace(string oldValue, string newValue`)	문자열 내의 특정 문자열을 다른 문자열로 대체한 새 문자열을 반환한다.
#### `Split(char separator)`	지정된 구분자를 기준으로 문자열을 분할하여 문자열 배열을 반환한다.
#### `Trim()`	문자열의 시작과 끝에 있는 공백을 제거한 새 문자열을 반환한다.
#### `IsNullOrEmpty(string value)`	문자열이 null 또는 비어 있는지 반환한다.
#### `Equals(string value)`	두 문자열이 같은지 비교한다.
#### `Insert(int startIndex, string value)`	지정된 위치에 문자열을 삽입한 새 문자열을 반환한다.
#### `Remove(int startIndex)`	지정된 위치부터 끝까지의 문자열을 삭제한 새 문자열을 반환한다.
#### `Remove(int startIndex, int count)`	지정된 위치부터 주어진 길이만큼의 문자열을 삭제한 새 문자열을 반환한다.
#### `Format(string format, params object[] args)` 서식 문자열을 지정하여 문자열을 형식화한다.
#### `Clone()`	현재 인스턴스의 복사본을 반환한다.
#### `CompareTo(string value)`	현재 인스턴스와 다른 문자열의 정렬 순서를 비교한다.
#### `ToString()`	현재 인스턴스를 문자열로 반환한다.

#### 실제 지금까지 서버를 다루면서 String 문자열을 이런 메서드로 다루는 경우는 적었지만 문자열을 효과적으로 다룰 수 있으므로 알아두는 것이 편리함.

### 성능 차이

- 만약 문자열을 단순히 순회하면서 읽기만 하는 경우에는 `for`문을 직접 사용해도 `System.String` 메서드를 사용하는 것과 큰 성능 차이는 없다.
- 하지만 문자열을 여러 번 수정하는 경우
   - `String` 메서드를 반복적으로 호출하면 메모리 할당과 GC 부하로 인해 성능이 떨어질 수 있다.
   - 반면 `for`문과 `StringBuilder`를 사용하면 메모리 할당 횟수를 줄여 성능이 크게 향상될 수 있다.
 
#### 즉, `읽기` 위주의 작업에서는 `String` 메서드를 사용하는 것이 간결하고 성능 저하도 적다.
#### `수정` 작업이 빈번할 때는 `for`문과 `StringBuilder`를 사용하는 것이 성능상 더 유리하다.
