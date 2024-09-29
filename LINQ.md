## LINQ (Language Integrated Query)

### LINQ 란?
- 데이터를 쿼리하는 통합된 방식으로 다양한 데이터 소스(컬렉션, 데이터베이스, XML, 엔티티 등)에 대해 SQL과 유사한 방식으로 데이터를 처리할 수 있게 해줌.
- `LINQ`는 개발자가 데이터 쿼리 작업을 더 간결하고 가독성 있게 작성할 수 있도록 지원함.
- 주로 Entity로 DB를 연동할 때 C# 내에서 쉽게 사용할 수 있음.

#### 1. 쿼리 구문
```C#
int[] numbers = { 5, 10, 8, 3, 6, 12 };

// LINQ 쿼리 구문
var result = from num in numbers
             where num > 5
             orderby num
             select num;
// SQL 문법과 유사함.
```

#### 2. 메서드 구문
```C#
int[] numbers = { 5, 10, 8, 3, 6, 12 };

// LINQ 메서드 구문
var result = numbers.Where(num => num > 5).OrderBy(num => num);
// 주로 사용하는 방법.
```

### 주요 LINQ 연산자

#### 1. Where: 조건에 맞는 요소를 필터링
```C#
var filtered = numbers.Where(n => n > 5);
```

#### 2. Select: 각 요소를 변환하거나 선택
```C#
var squares = numbers.Select(n => n * n);
```

#### 3. OrderBy / OrderByDescending: 요소를 정렬
```C#
var ordered = numbers.OrderBy(n => n);
// OrderBy 오름차순
// Descend 내림차순
```

#### 4. GroupBy: 요소를 그룹화
```C#
var grouped = numbers.GroupBy(n => n % 2 == 0);
```

#### 5. Aggregate: 요소들을 하나의 결과로 집계
```C#
var sum = numbers.Aggregate((total, next) => total + next);
```

#### 6. First / FirstOrDefault: 첫 번째 요소 또는 기본값 반환
```C#
var first = numbers.First(n => n > 5);
// 값이 최소 하나라도 있는 것을 알 때 First
// 모호할 때 Default 값 반환해주는 FirstOrDefault
```

#### 7. ToList / ToArray: 결과를 리스트나 배열로 변환
```C#
var list = numbers.Where(n => n > 5).ToList();
```

#### LINQ는 코드의 가독성을 높이고 데이터 쿼리 작업을 더 직관적으로 만들어 줌.
#### 따라서 컬렉션이나 데이터 소스를 다루는 작업에서 매우 유용하게 사용됨.

#### 특히 EntityFrameWork 사용에 유용하며 문자열을 다루는데 효과적임.
