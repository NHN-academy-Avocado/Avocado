# 2단원: Objects의 사용과 변수

## 2.1 간단한 자바 프로그램

다음과 같은 자바 프로그램을 고려해보자.

```java
public class MyMessage {
	public static void main(String[] args) {
	//What does this program do?
	/* Do you know it?
	It’s easy. */
	System.out.println("JA");
	System.out.println("VA");
	}
}
```

### 프로그램의 폼

- 자바 프로그램에서 한 단어는 공백으로 구분된다. 예) public class
- 새로운 줄에서 작성하는 것은 빈칸과 같이 두 단어를 구분하는 것과 같은 효과를 냅니다.
- 단어를 분리하기위해 임의의 공백이나 새로운 줄을 여러개 사용할 수 있습니다.(최소 1개)

들여쓰기는 프로그램의 실행에 어떠한 영향도 미치지 않습니다. 그러나 코드의 가독성을 위해서는 적절한 들여쓰기의 사용이 매우 중요합니다.

### 주석

프로그램에 주석을 다는 것은 매우 중요합니다. 자바에서 우리는 두 가지 방식으로 주석을 달 수 있습니다.

- ‘ // ’는 한 줄에서 주석의 시작을 의미하며 그 줄의 끝까지 주석으로 처리합니다.
- ‘ /\* \*/ ‘ 는 몇줄의 주석을 정의합니다.

주석은 프로그램의 실행에 어떠한 영향도 미치지 않습니다. 마찬가지로, 주석의 사용은 프로그램 코드의 가독성을 향상시킵니다.

### 자바의 다른 속성들

- public class MyMessage. 모든 자바 프로그램들은 자바 Class들의 모음입니다.
- public static void main(String[] args). 이것은 프로그램의 실행이 시작되는 곳을 나타내는 표준 main method 입니다.
- System 은 미리 정의된 자바 Class 입니다.
- System.out 은 미리 정의된 자바 클래스인 PrintStream의 instance Object 입니다. 이 Object는 System 클래스에 정의되어 있고, 시스템 출력을 제어하는데 사용됩니다.
- println(…) 은 PrintStream 형식의 Object에 대한 지원 method 입니다. (이것은 PrintStream Class 속성입니다.)
- System.out.println(”…”) 은 호출 Object인 System.out에서 method println(”…”)을 호출하는 것이며, 이때 매개변수로 “…”을 사용합니다.

Note: 일반적으로 자바는 Class 이름이 대문자로 시작하고 method 이름은 소문자로 시작하는 관례를 채택합니다. 프로그램을 이해받고자 한다면 이 관례를 존중하는 것이 좋습니다.

## 2.2 Method 호출

구문:

```java
object.methodName(parameters)
```

- object 는 호출 object를 나타내는 참조입니다.
- methodName(…)은 호출 method 입니다.
- parameters 는 method에 전달된 매개변수 입니다.

의미:

object에 대한 method를 호출하며 추가 parameter를 전달할 수 있습니다. method 호출의 효과는 method와 관련된 작업의 실행히며 때로는 값의 반환도 포함됩니다.

예:

```java
System.out.println(”Ciao!”);
```

- System.out 은 호출 obejct를 나타내는 참조입니다.
- println(…)은 호출 method입니다.
- “Ciao!” 는 method에 전달된 매개변수 입니다.

println method 호출은 parameter로 전달된 문자열, 즉 “Ciao!”를 표준 출력 채널인 모니터에 출력하게 만듭니다. 이 모니터는 System.out으로 나타냅니다. 이 메서드는 결과를 반환하지 않고 System.out으로 표시된 object에 작업을 수행합니다.

## 2.3 method print와 println의 차이

```java
public class MyMessage2 {
	public static void main(String[] args) {
		System.out.print("JA");
		System.out.print("VA");
		System.out.println();
	}
}
```

println(”…”) method는 문자열 “…”을 출력하고 커서를 새로운 줄로 이동합니다. print(”…”) method는 “…”를 출력하고 대신 커서를 새로운 줄로 이동시키지 않습니다. 따라서, 이후의 출력 명령은 동일한 줄에 출력됩니다. println 메서드는 또한 매개변수 없이 사용하여 커서를 다음 줄로 이동하는데 사용할 수 있습니다.

## 2.4 자바에서 Objects와 Classes

- objects 는 프로그램에 의해 조작될 수 있는 엔티티(개체, 실재)들을 나타냅니다.(일반적으론느 그들의 method를 호출하여)
- 각 object는 class에 속하며 우리는 그것이 그 class의 instance 라고 말합니다.
- class는 동일한 속성을 가진 object들의 집합으로 구성됩니다. 이것들을 그 class의 instance 라고 합니다.
- object가 속한 class는 해당 object에 대해 사용 가능한 method를 결정합니다. (즉, 올바르게 적용할 수 있는 메서드를 결정) 예를 들어 :
  ```java
  System.out.print(); //OK
  System.out.foo(); //ERROR
  ```

## 2.5 The class String

사전에 정의되어있는 String class를 분석해보겠습니다. 이 class의 instance인 객체들은 문자열, 즉 문자들로 이루어진 시퀀스를 나타냅니다.

큰따옴표로 둘러싸인 표현식, 예를 들면 “java”는 String class의 obejct를 나타냅니다.(더 정확하게는 String class의 사전에 정의된 객체에 대한 참조) 그리고 이러한 것을 문자열 리터럴(String literals)라고 합니다. 일반적으로 literals는 상수를 나타내므로 String literal은 문자열 유형의 상수를 나타냅니다. String class는 Java 문서에서 다음 표와 같은 여러 메서드를 제공합니다.

![screenshot1](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/bbc51966-a9ac-40d0-bc76-bf313437efd4)

예시:

```java
public class MyMessage3 {
	public static void main(String[] args) {
	System.out.println("java".toUpperCase());
	}
}
```

String class의 method인 toUpperCase()는 문자열을 대문자로 바꾸어줍니다. 이 경우에서 “java”라는 literal을 나타내는 object에서 toUpperCase가 호출되며 이 method는 “JAVA”라는 문자열을 나타내는 String class의 새 object에 대한 참조를 반환합니다. 이 새 object는 프로그램에 의해 출력됩니다.

## 2.6 Method signature 와 method header

method의 signature는 method의 이름과 parameter의 속성(즉, 타입, 개수, 위치)으로 구성됩니다.

예시:

- toUpperCase()
- println(String a)

Note: parameter의 이름은 signature와 관련이 없습니다.

method의 header는 signature에 결과의 타입에 대한 설명을 포함합니다.

예시:

- String toUpperCase()
- void println(String s)

void는 method가 어떠한 결과도 반환하지 않는다는 것을 나타냅니다.(즉, 이 method는 작업을 수행하며 함수가 아닙니다.)

동일한 class의 두 method는 signature가 다르다면 같은 이름을 가질 수 있습니다. signature가 다른 동일한 이름의 두 method를 overlod 되었다고 합니다. 예를 들어 String class의 substring method가 있습니다.

## 2.7 Parameters와 method의 반환

method의 parameters는 호출 블럭이 method에 전달하는 인수를 나타내며, method가 수행해야 하는 작업을 실현하기 위해 필요합니다.

예시: method println(String s)는 명령문 System.out.println(”ciao!”)를 통해 object System.out에서 호출될 수 있습니다. 문자열 “ciao”로 표현된 parameter는 method 내에서 System.out으로 모니터에 표시할 문자열로 사용됩니다.

메서드가 결과를 반환해야 하는 경우(return type이 void가 아닌 경우) 해당 결과는 method에 의해 계산되어 호출 블럭에 반환됩니다.

예시: method String concat(String s)를 생각해봅시다. 문자열 “JA”에 대해 이러한 method를 호출하고 이를 매개변수로 문자열 “VA”로 전달하면 문자열 “JAVA”를 계산하여 반환합니다.

## 2.8 Method 호출 결과 값

method를 호출하려면 호출 object와 해당 parameter를 알아야 합니다.

예시: “xxx”.concat(”yyy”)

return the string “xxxyyy”

- 호출 object: “xxx”
- parameters: “yyy”

호출 object와 parameter가 알려지면 method를 실행하고 결과 값을 계산할 수 있습니다.

예시: “xxx”.concat(”yyy”)

문자열 “xxxyyy”를 반환합니다.

이 경우 호출 object와 parameter의 계산이 즉시 이루어집니다. 일반적으로 호출 object와 parameter로 전달된 인수 모두 다른 메서드를 먼저 호출하여 얻어야 할 수 있습니다.

## 2.9 Method 호출을 나타내는 표현식의 호출 object 결과 값

다음 명령문은 무엇을 표시할까요?

```java
System.out.println("xxx".concat("yyy").concat("zzz"));
```

답을 내기 위해서는 “xxx”.concat(”yyy”).concat(”zzz”) 표현식이 어떻게 계산되는지 이해해야 합니다.

1. 하위 표현식 “xxx”.concat(”yyy”)를 즉시 계산할 수 있습니다.
   - “xxx”는 호출 object를 나타냅니다.
   - “yyy”는 parameter를 나타냅니다.
   - 둘 다 직접 사용할 수 있으므로 “xxxyyy” 문자열을 반환하는 “xxx”.concat(”yyy”)를 계산할 수 있습니다.
2. “xxx”.concat(”yyy”)를 계산한 후 concat(”zzz”)를 계속할 수 있습니다.
   - “xxxyyy”는 호출 object를 나타냅니다.
   - “zzz”는 parameter를 나타냅니다.
   - 이제 둘 다 상용할 수 있으므로 “xxxyyy”.concat(”zzz”)문자열을 반환하는 “xxxyyyzzz”를 계산할 수 있습니다.

따라서 System.out.println(”xxx”.concat(”yyy”).concat(”zzz”)); “xxxyyyzzz”를 표시합니다.

호출 object를 나타내는 식의 평가는 호출 object를 계산하고 method를 호출하여 왼쪽에서 오른쪽으로 수행됩니다.

## 2.10 Method의 parameter를 나타내는 표현식 계산

다음 명령문은 무엇을 표시할까요?

```java
System.out.println("xxx".concat("yyy".concat("zzz")));
```

답변을 제공하려면 “xxx”.concat(”yyy”.concat(”zzz”)) 표현식이 어떻게 계산되는지 이해해야 합니다.

1. 하위 표현식 “yyy”.concat(”zzz”)를 즉시 계산할 수 있습니다.
   - “yyy”는 호출 object를 나타냅니다.
   - “zzz”는 parameter를 나타냅니다.
   - 둘 다 직접 사용할 수 있으므로 “yyy”.concat(”zzz”)를 계산할 수 있으며 “yyyzzz”문자열을 반환합니다.
2. “yyy”.concat(”zzz”)를 계산한 수 “xxx”.concat(…)을 계속할 수 있습니다.
   - “xxx”는 호출 object를 나타냅니다.
   - “yyyzzz”는 항목 1에서 계산된 parameter를 나타냅니다.
   - 이제 둘 다 사용할 수 있으므로 “xxx”.concat(”yyyzzz”) 문자열을 반환하는 “xxxyyyzzz”를 계산할 수 있습니다.

따라서 System.out.println(”xxx”.concat(”yyy”.concat(”zzz”))); 구문은 “xxxyyyzzz”를 표시합니다.

parameter를 나타내는 표현식의 계산은 내부에서 외부로 이루어지며, 호출이 계산되기 전 각 호출의 parameter를 매번 계산합니다.

## 2.11 Static methods

Static mathod는 호출 object가 필요하지 않은 method 입니다. static method 호출 구문은 다음과 같습니다.

```java
ClassName.methodName(parameters)
```

- ClassName은 method가 속한 class 입니다. (즉, method가 정의된 class)
- methodNAme(…)은 호출된 method입니다..
- parameters는 method에 전달되는 매개변수 입니다.

Static method를 호출하는 것은 호출 object를 지정할 필요가 없고 parameter만 지정한다는 점을 제외하면 dynamic method를 호출하는 것과 유사합니다. method 이름 앞에는 해당 method가 속한 class 이름이 옵니다. 이는 Java method의 이름이 class에 local이므로 method를 식별하려면 method의 class를 지정해야 하기 때문입니다.

예시:

```java
JOptionpane.showInputDialog("문자열을 삽입하세요")
```

이는 미리 정의된 JOptionpane class에 정의된 showInputDialog method의 호출입니다. 이 method에는 String 유형의 “문자열을 삽입하세요” parameter가 전달됩니다. 이 method는 사용자 입력이 필요한 대화 상자를 엽니다. 이러한 창에는 “문자열을 삽입하세요”라는 메세지와 method가 반환할 문자열을 입력할 수 있는 입력 필드가 표시됩니다. 이 방법은 나중에 더 자세히 살펴보겠습니다.

Note: class의 기본 method는 반환 유형이 void이고 매개변수로 String 객체의 배열을 갖는 static method 입니다.(나중에 참조)

## 2.12 변수

예시:

```java
public class Java1 {
	public static void main(String[] args) {
		System.out.println("java".toUpperCase());
		System.out.println("java".toUpperCase());
	}
}
```

“java”.toUpperCase() 표현식은 두 번 실행됩니다. 이를 방지하기 위해 이 표현식의 평가 결과를 변수에 저장하고 인쇄에 재사용할 수 있습니다.

```java
public class Java2 {
	public static void main(String[] args) {
		String line;
		line = "java".toUpperCase();
		System.out.println(line);
		System.out.println(line);
	}
}
```

Java2에서 line은 “java”.toUpperCase() 값을 할당받은 String 유형의 변수이며, 이 변수는 두 번 표시됩니다.

변수는 객체에 대한 참조를 저장하는 데 사용할 수 있는 메모리 위치를 나타냅니다.

## 2.13 변수: 주요 속성

변수는 프로그램 내부의 데이터를 나타내는데 사용됩니다.

변수의 특징은 다음과 같습니다.

1. 이름: 변수를 식별하기 위해 필요합니다. 이러한 이름은 Java 식별자여야 합니다. 즉,
   - 문자 또는 ‘_’로 시작하는 일련의 문자, 숫자 또는 ‘_’ 문자
   - 길이는 얼마든지 가능합니다.
   - 소문자와 대문자는 다른 것으로 간주됩니다.
   - 키워드 라고 하는 일부 식별자(class, public, if, while)은 예약되어 있습니다.(사용불가)
2. 유형: 변수가 저장할 수 있는 데이터 타입을 지정합니다. 예를 들어 String 유형의 변수는 문자열에 대한 참조를 저장 할 수 있습니다.
3. 저장된 데이터가 포함된 메모리 위치의 주소:
   - 각 변수에는 연관된 메모리 위치가 있습니다.
   - 메모리 위치의 크기는 변수 유형에 따라 다릅니다.
   - Java에서는 메모리 위치의 주소를 알 수 있는 방법이 없습니다! 이를 통해 바이러스 공격 등 보안과 관련된 여러가지 문제를 해결합니다.
4. 값: 프로그램 실행 중 특정 시점에 변수가 나타내는 데이터. 예: “Java” 객체애 대한 참조

프로그램 실행 중에 변수의 이름, 유형, 주소는 변경할 수 없지만 값은 변경할 수 있습니다.

Note: 변수에 object에 대한 참조가 포함되어 있더라도 우리는 종종 용어를 잘못 사용하여 변수의 “값이 변수가 참조하는 object”라고 말합니다.

## 2.14 변수 및 shoe-boxes

우리는 변수를 찬장에 있는 라벨이 붙은 신발 상자와 비교함으로써 직관적으로 변수의 의미를 이해할 수 있습니다.

1. 이름 - 라벨
2. 타입 - 상자의 형태(상자에 넣을 수 있는 신발 유형을 결정함)
3. 주소 - 찬장 내 위치(위치가 변경되지 않는다는 사실은 신발 상자가 찬장에 못으로 고정되어 있음을 의미함)
4. 값 - 상자 안의 신발

## 2.15 변수 선언

변수는 변수 선언을 통해 프로그램에 도입됩니다.

구문:

```java
type variableName;
```

- type은 변수의 타입입니다.
  - object에 대한 타입 참조 변수의 경우 object가 instance인 calss의 이름입니다.
  - 그렇지 않으면 사전에 정의된 기본 유형입니다. 단원 4를 참조하세요.
- variableName은 선언되는 변수의 이름입니다.

의미:

변수 선언은 변수에 대한 메모리 위치를 예약하고 선언이 나타나는 프로그램(블록) 부분에서 변수를 사용할 수 있게 만듭니다.(자세한 내용은 단원 3 참조). 변수를 사용하려면 먼저 변수를 선언해야 합니다.

예시:

```java
String line;
```

- String 은 변수의 타입입니다.
- line은 변수의 이름입니다.

이러한 선언 이후에는 선언이 나타나는 프로그램 블록에서 변수를 사용할 수 있습니다.(예: 메인 method에 선언이 되어있을 경우)

단일 선언으로 동일한 유형의 여러 변수를 선언할 수 있습니다.

```java
type variableName-1, variableName-2, ..., variableName-n;
```

이러한 선언은 다음과 같습니다.

```java
type variableName-1;
type variableName-2;
...
type variableName-n;
```

## 2.16 할당

할당은 변수에 값을 저장하는 데 사용됩니다.

구문:

```java
variableName = expression;
```

- variableName은 변수의 이름입니다.
- expression은 평가 시 변수 유형의 값을 반환해야 하는 표현식입니다.

의미:

variableName 변수에는 = 기호 오른쪽에 있는 표현식의 값이 할당됩니다. 이러한 값은 object(에 대한 참조) 이거나 다른 타입의 일부 데이터일 수 있습니다.(나중에 참조). 할당 후 변수의 값은 다음 할당까지 변경되지 않은 상태로 유지됩니다.

예:

```java
line = "자바";
```

- line은 String 유형의 변수입니다.
- “자바”는 String 유형의 값, 특히 “자바” 자체를 반환하는 (매우 간단한) 표현식입니다.

할당 실행 결과 “자바”(로 표시되는 object)를 나타냅니다.

예시: 다음의 의미는 무엇일까요?

```java
s = s.concat("yyy");
```

실행의 과정은 다음과 같습니다:

1. 오른쪽의 표현식을 실행합니다. 즉, s의 현재 값(예: “xxx”)에 문자열 “yyy”를 연결하여 결과로 “xxxyyy”를 얻습니다.
2. s의 현재 값(예: “xxx”)을 방금 계산된 값(예: “xxxyyy”)으로 바꿉니다.

할당 실행 전 s의 값이 “xxx”였다면 할당 후 s 값은 “xxxyyy” 입니다.

Note: 과제는 동일성 테스트(단원 4에서 살펴보게 됨)와 다릅니다.

## 2.17 변수 초기화

변수를 초기화한다는 것은 변수에 할당할 초기 값을 지정하는 것을 의미합니다.(즉, 변수가 사용되기 전).

초기화되지 않은 변수에는 정의된 값이 없으므로 해당 값이 할당될 때까지 사용할 수 없습니다. 변수가 선언되었지만 초기화되지 않은 경우 할당문을 사용하여 값을 할당할 수 있습니다.

예시: 다음 프로그램에는 의미 오류가 포함되어 있습니다.

```java
public class Java3 {
	public static void main(String[] args) {
		String line;
		System.out.println(line);
		System.out.println(line);
	}
}
```

변수 line은 인쇄를 요청하기 전에 초기화되지 않습니다.(오류는 컴파일 타임에 감지됩니다.)

변수는 선언되는 순간 다음 명령문을 통해 초기화될 수 있습니다.

```java
type variableName = expression;
```

Java에서 위의 명령문은 다음과 동일합니다.

```java
type variableName;
variableName = expression;
```

예시:

```java
String line = "java".toUpperCase();
```

```java
String line;
line = "java".toUpperCase();
```

## 2.18 Object 참조

Java에서 변수는 Object를 포함할 수 없고 Object에 대한 참조만 포함할 수 있습니다.

Object는 변수 선언과 별도로 메모리에 생성되고 할당됩니다. 구체적으로:

- literal로 표시된 객체(예: String 유형의 literal, 예: “foo”, “ciao” 등)는 컴파일 타임에 메모리에 할당됩니다.
- 다른 모든 object는 명시적 명령문을 통해 생성 및 할당되어야 합니다.(나중에 참조)

유형이 class인 변수에는 class의 object에 대한 참조가 포함됩니다.(즉, object가 할당된 메모리 위치의 주소).

예시:

```java
String s;
s = "xxx";
```

첫 번째 문은 String 유형의 변수 s를 선언합니다. 이러한 변수는 아직 초기화되지 않았습니다. 두 번째 명령문은 “xxx”로 표시된 개체에 대한 참조를 이러한 변수에 할당합니다.

두 변수에는 동일한 개체에 대한 참조가 포함될 수 있습니다.

예시:

```java
String s, t;
s = "xxx";
t = s;
```

이 두 명령문 뒤에는 t와 s 모두 “xxx”로 표시된 object에 대한 참조가 포함되어 있습니다.

object 참조 유형의 변수에는 null이라는 특수 값이 있을 수도 있습니다. 이러한 값은 변수가 어떤 개체도 나타내지 않음을 의미합니다. 값이 null인 변수와 초기화되지 않은 변수를 혼동하지 마세요. 초기화되지 않은 변수에는 값이 없으며 심지어 null도 없습니다.

## 2.19 변수를 표현하기 위한 그래픽 표기법

변수는 object가 저장되는 메모리 위치에 대한 참조입니다. 변수와 해당 값을 나타내기 위해 다음 그래픽 표기법을 사용합니다.

![Untitled](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/0190c06b-cd88-4cab-809a-ef87ab2bd66d)

다이어그램은 변수의 이름, 타입, 주소 및 값을 나타냅니다. 값은 일반적으로 참조된 개체를 가리키는 화살표로 표시됩니다. object의 경우 object가 instance인 class 와 상태, 즉 해당 속성의 값을 나타냅니다. 왼쪽 다이어그램은 object 참조 개념을 명확히 하기 위해 메모리 위치의 실제 주소를 보여줍니다. 실제로 Java에서는 object의 주소가 명시적으로 표현되지 않습니다. 즉, 실제로 object를 저장하는 데 사용되는 메모리 위치가 무엇인지 관심이 없습니다.(오른쪽 다이어그램 참조). 변수의 유형은 일반적으로 참조된 object의 타입과 일치하기 때문에 종종 변수의 타입도 생략합니다.(상속으로 인해 항상 그런 것은 아닙니다. 단원 4 참조).

예: 명령문 실행 후 메모리 상황

```java
String s, t, u;
s = "xxx";
t = "yyy";
u = t;
```

다음 다이어그램에 나와있습니다.

![screenshot2](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/55d23ac8-cad1-49f3-9d0e-b2c31e921e6e)

## 2.20 **예: 문자열에 대한 프로그램**

```java
public class Hamburger {
  public static void main(String[] args) {
    String s,t,u,v,z;
    s = "ham";
    t = "burger";
    u = s.concat(t);
    v = u.substring(0,3);
    z = u.substring(3);
    System.out.println("s = ".concat(s));
    System.out.println("t = ".concat(t));
    System.out.println("u = ".concat(u));
    System.out.println("v = ".concat(v));
    System.out.println("z = ".concat(z));
  }
}
```

## 2.21**예: 문자열 연결**

변수와 할당을 사용하여 문자열 "xxxyyyzzz" 구성:

```java
String x = "xxx", y = "yyy", z = "zzz";
String temp = x.concat(y);
String result = temp.concat(z);
System.out.println(result);
```

각 객제나 각 중간 결과마다 하나의 변수를 사용합니다.

## 2.22 **예: 이름의 이니셜**

```java
public class JFK {
  public static void main(String[] args) {
    String  first = "John";
    String  middle = "Fitzgerald";
    String  last = "Kennedy";
    String  initials;
    String  firstInit, middleInit, lastInit;
    firstInit = first.substring(0,1);
    middleInit = middle.substring(0,1);
    lastInit = last.substring(0,1);
    initials = firstInit.concat(middleInit);
    initials = initials.concat(lastInit);
    System.out.println(initials);
  }
}

// or simply
public class JFK2 {
  public static void main(String[] args) {
    String  first = "John";
    String  middle = "Fitzgerald";
    String  last = "Kennedy";
    System.out.println(first.substring(0,1).
                             concat(middle.substring(0,1)).
                             concat(last.substring(0,1)));
  }
}
```

## 2.23 **문자열 연결을 위해 " + " 사용**

```java
public class JFK {
  public static void main(String[] args) {
    String  first = "John";
    String  middle = "Fitzgerald";
    String  last = "Kennedy";
    String  initials;
    String  firstInit, middleInit, lastInit;
    firstInit = first.substring(0,1);
    middleInit = middle.substring(0,1);
    lastInit = last.substring(0,1);
    initials = firstInit + middleInit + lastInit;
    System.out.println(initials);
  }
}

// or simply
public class JFK2 {
  public static void main(String[] args) {
    String  first = "John";
    String  middle = "Fitzgerald";
    String  last = "Kennedy";
    System.out.println(first.substring(0,1) +
                       middle.substring(0,1) +
                       last.substring(0,1));
  }
}
```

## 2.24**생성자 호출**

새로운 객체의 생성은 **생성자** 라는 특별한 메소드를 호출하여 수행됩니다 .

---

생성자 호출

---

구문(문법):

new className (parameters )

- new 는 미리 정의된 연산자입니다.
- *className* ( *매개변수* ) 은 생성자라는 특수 메서드의 시그니처입니다. 생성자의 이름은 그것이 속한 클래스의 이름과 일치합니다.

특정 클래스에는 매개변수의 수 및/또는 type이 다른 여러 생성자가 있을 수 있습니다(생성자 오버로딩).

의미론:

생성자를 호출하면 생성자가 속한 클래스의 새 개체가 생성되고 생성된 개체에 대한 참조가 반환됩니다. 객체는 생성자에 전달된 매개변수를 사용하여 생성됩니다.

예:

```java
new String("test")
```

- new 는 미리 정의된 연산자입니다.
- String(String s)는 String 클래스의 생성자입니다.

표현식은 "test" 로 표시된 문자열과 동일한 String 클래스의 새 객체를 생성합니다 . 그러한 객체에 대한 참조는 표현식에 의해 반환됩니다.

---

예:

```java
public class Hello {
  public static void main(String[] args) {
    String s = new String("hello world");
    System.out.println(s);
  }
}
```

참고 사항:

- 생성자 new String("hello world")을 호출하면 String 의 인스턴스이고 "hello world" 라는 문자열을 나타내는 새 객체가 생성됩니다.
- 그러한 객체에 대한 참조는 변수 s 에 할당됩니다.
- s 로 표시된 객체의 값 (즉, " hello world ")이 인쇄됩니다.

## 2.25 빈 문자열

빈 문자열은 길이가 0인 문자 시퀀스를 나타내며 literal “” 으로 표시할 수 있습니다.

String class에는 빈 문자열을 생성하는 매개변수가 없는 생성자가 있습니다.

```java
String emptystring = new String();
```

문자열에 대해 본 다른 생성자는 문자열을 parameter로 사용합니다. 따라서 두 생성자는 서로 다른 서명을 갖습니다. overloading이 발생한 경우입니다.

Note: 빈 문자열을 null과 혼동하지 마십시오.

## 2.26 **객체의 접근성**

다음 코드를 봐보세요.

```java
String s1 = new String ("test1");
String s2 = new String ("test2");
s1 = s2;
```

s1 및 s2 에 대한 참조는 처음에는 새로 생성된 두 개체에 대한 두 개의 참조입니다. 대입문은 s1 의 참조를 s2 의 참조 (동일한 개체 "test2" 에 대한 두 개의 참조) 와 동일하게 설정하는 반면, 첫 번째 문에서 생성된 개체 "test1" 에 대한 참조는 손실됩니다. (모르면 질문 하세요)

![Untitled 1](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/ee5c28d1-d01b-4603-aaeb-17a6b7b040c4)

프로그램에 의해 "손실"된 개체가 사용하는 메모리를 복구하는 작업을 **가비지 수집** 이라고 합니다 . Java에서는 이러한 작업이 런타임 시스템(예: Java Virtual Machine)에 의해 자동으로 수행됩니다.

## 2.27 객체에 대한 참조

new 연산자는 object의 새로운 instance를 생성합니다.

예시:

```java
String s1 = new String("test");
String s2 = new String("test");
String t1 = "test";
String t2 = "test";
```

참조 s1과 s2는 서로 다른 object에 대한 참조이고, t1과 t2는 동일한 object에 대한 참조입니다.

![Untitled 2](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/e61f39d3-4a33-4b4f-9ed0-95e41dc9efd8)

## 2.28 불변(Immutable) Object

String 유형의 object는 자신의 상태, 즉 표현하는 문자열을 변경할 방법(method)이 없기 때문에 불변object 입니다.

상태를 변경할 수 없는 object를 불변 object라고 합니다. 그들은 평생동안 정확히 동일한 정보를 나타냅니다.

예시:

```java
public class UpperLowerCase {
	public static void main(String[] args) {
		String s, upper, lower;
		s = new String("Hello");
		upper = s.toUpperCase();
		lower = s.toLowerCase();
		System.out.println(s);
		System.out.print("upper = ");
		System.out.println(upper);
		System.out.print("lower = ");
		System.out.println(lower);
	}
}
```

이 프로그램은 3개의 다른 문자열을 구성합니다.(더 이상 수정되지 않음)

- 문자열 “Hello”, 생성자를 호출하여
- 변수 Upper로 표시되는 문자열 “Hello”, 그리고
- lower 변수로 표시되는 문자열 “hello”.

## 2.29 가변 object: StringBuffer class

Java에는 String과 매우 유사하지만 instance가 변경 가능한 object인 class StringBuffer도 있습니다.

특히 StringBuffer class에는 object가 나타내는 문자열을 수정하는 method가 있습니다.

![screenshot3](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/b04ea382-7685-4c25-9219-218011bb021b)

## 2.30 **가변 객체: 부수 작용이 있는 메소드**

가변 객체는 자신의 상태를 수정할 수 있어야 합니다. **이러한 수정을 부수 작용이라고 합니다.** 이러한 수정을 수행하는 메서드를 부수 작용이 있는 메서드라고 합니다.

```java
public class SideEffect1 {
  public static void main (String[] args) {
    StringBuffer s = new StringBuffer("test");
    StringBuffer t;
    t = s;
    s.append("!");
    System.out.println(s.toString());
    System.out.println(t.toString());
  }
}
```

고려사항:

- 이 프로그램을 실행하면 "test!" 가 두번 인쇄됩니다.
- append이 호출 객체에 부수 작용을 어떻게 하는지 알아보세요. s 에 저장된(보다 정확하게는 참조되는) 객체는 Append 메소드 의 실행으로 수정됩니다
- 명령문 실행 이후 t = s; , s 와 t는 동일한 객체를 참조하고 t는 "test!" 를 나타내는 객체를 나타냅니다.

*참고:* 일반적으로 추가 메소드는 수정된 호출 객체에 대한 참조를 반환하지만 s.append("!"); 문에서는 그러한 참조가 사용되지 않습니다.

![Untitled 3](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/4d8c4c63-5a5b-4c85-b2b9-4e2e1f7a747b)

## 2.31 예시: StringBuffer class를 사용한 이름 이니셜

밑에 표는 병훈의 첨부 파일(책 내용X)

![Untitled 4](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/80ab5e9f-476d-495b-bd98-8dce27b20198)

```java
public class SideEffect2 {
	public static void main (String[] args) {
		String s = "name surname";
		StringBuffer sbuf = new StringBuffer(s);
		sbuf.replace(0,1,s.substring(0,1).toUpperCase());
		sbuf.replace(5,6,s.substring(5,6).toUpperCase());
		System.out.println(sbuf.toString());
}
}
```

## 2.32 키보드 입력

Java에는 입력에서 문자열을 읽는 방법이 많이 있습니다. 가장 간단한 방법은 미리 정의된 showInputDialog method를 사용하는 것입니다. 이 method는 JOptionpane class에 정의되어 있으며 이는 결국 swing 라이브러리의 일부입니다. 이러한 method를 사용하면 다음 스키마에 따라 키보들에서 입력을 읽을 수 있습니다.

```java
import javax.swing.JOptionPane;
public class KeyboardInput {
	public static void main (String[] args) {
		...
		String inputString = JOptionPane.showInputDialog("Insert a string");
		...
		System.out.println(inputString);
		...
		System.exit(0);
	}
}
```

- import javax.swing.JOptionPane; - javax.swing 라이브러리에서 JOptionPane 클래스를 가져옵니다.
- String inputString = JOptionPane.showInputDialog(”문자열을 삽입하세요”);
  1. “문자열 삽입” 메시지를 표시하는 대화 상자 창(그림 참조)을 생성합니다.
  2. 키보드에서 문자열을 읽고
  3. 그러한 문자열을 반환(참조)하고
  4. inputString변수에 대한 참조를 할당합니다.
- System.exit(0); 사전에 정의된 라이브러리 class JOptionPane을 사용할 때 기본 method에 추가해야 합니다. 대화 상자 창은 main에 의해 직접 처리되지 않으므로 대화 상자를 종료하려면 명시적인 명령을 제공해야 하기 때문에 이것이 필요합니다.

![Untitled 5](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/04395610-8c9e-45e6-a5c3-7d0588a70c1a)

## 2.33 **예: 입력에서 읽은 이름의 이니셜**

```java
import javax.swing.JOptionPane;

public class Initials {
  public static void main (String[] args) {
    String fn = JOptionPane.showInputDialog("Insert first name");
    String ln = JOptionPane.showInputDialog("Insert surname");
    String ifn = fn.substring(0,1).toUpperCase();
    String iln = ln.substring(0,1).toUpperCase();
    System.out.println("Name: " + fn + " " + ln);
    System.out.println("Initials: " + ifn + iln);
    System.exit(0);
  }
}
```

## 2.34 창으로 출력

JOptionPane 클래스를 사용하면 출력을 대화 상자 창으로 보내는 것도 가능합니다. 특히 showMessageDialog 메소드를 사용할 수 있습니다. 다음 프로그램은 그 사용법을 보여줍니다.

```java
import javax.swing.JOptionPane;

public class OutputWindow {
  public static void main(String[] args) {
    String name = JOptionPane.showInputDialog("What is your name?");
    name = name.toUpperCase();
    String stringToShow = "Hy " + name + ", how are you?";
    JOptionPane.showMessageDialog(null, stringToShow);
    System.exit(0);
  }
}
```

- JOptionPane.showMessageDialog(null,stringToShow); stringToShow 변수 로 표시된 문자열을 표시하는 대화 상자 창(그림 참조)을 만듭니다 . 첫 번째 매개변수의 값이 null 이면 생성해야 하는 창이 기존 창의 하위 창이 아님을 나타냅니다.

![Untitled 6](https://github.com/NHN-academy-Avocado/Avocado/assets/97264011/92933a93-0486-47e0-b4f2-b3f92e7c7e21)
