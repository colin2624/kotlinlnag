# kotlinlnag
kotlinlang

코틀린의 기본 문법은 아래와 같다.
```
package com.survivalcoding.kotlinbasic

func main() {
    print("Hello World")
}
```

변수를 선언할땐 var이라는 키워드를 사용해주면 된다. 예를들면

```
package com.survivalcoding.kotlinbasic

func main() {
    var i = 10
    var name = "준석"
    var point = 3.3
}
```
코틀린은 기본적으로 타입을 지정해주지 않아도 된다. 만약 타입을 지정해 주어야한다면
 
var (변수명) : (타입) = (값)

이렇게 작성해주면 된다. 그리고 타입을 작성할땐 대문자로 시작해야한다 (Int,String, Double)

그 다음으로 상수는 val이라는 키워드를 사용한다. 상수와 변수의 차이점은 변수는 값을 지정하고 값을 바꿀수 있지만 상수는 값을 바꿀수없다.

코틀린 같은 경우는 메인함수 밖에서도 변수나 상수를 선언하고 초기화 할수있다.
이것을 탑레벨 상수라고 한다. 예를 들어

```
package surviavalcoding.kotlinbasic

val num = 20

fucn main() {
    (대충 코드)
}
```
이렇게 작성할수 있다. 여기서 val앞에 const를 덧 붙여주게 된다면 main함수보다 
num이 먼저 컴파일이 된다.

형변환을 설명하기전에 예를 들어

```
package com.survivalcoding.kotlinbasic

func main() {
    var i = 10
    var l = 20L
}
```
라는 코드가 있는데 보통 자바에선 l안에 i를 넣을수 있지만 코틀린에선 같은 타입이
아니라면 l안에 i가 들어가지 않는다 그렇기 때문에 i뒤에 .toLong()을 붙여줘야한다.

이번에도 max,min을 설명하기전에 예를들면

```
package com.suviavalcoding.kotlinbasic

func main() {
    var i = 10
    var j = 20
}
```
위와 같은 코드가 있을때 가장 큰 값, 작은값을 출력하는 방법은
print(max(i, j)) 이렇게 작성해주면 끝난다 작은 값은
print(min(i, j)) 이렇게 작성해주면 된다

그리고 알고리즘을 풀때 유용하게 사용되는 random을 알아보도록 하겠다 예를 들어

```
package com.suviavalcoding.kotlinbasic

import kotlin.random.Random

func main() {
    val randomNumber = Random.nextInt()
    print(randomNumber)
}
```
위와 같은 코드를 작성할수 있는데 Random.nextInt()에서 랜덤 숫자를 뽑아서 randomNumber에 저잘하고 출력한다.
만약에 범위를 지정해주고 싶다면  Random.nextInt(0, 100) 이렇게 작성해주면 된다
0 ~ 99까지 숫자중 랜덤으로 숫자를 골라준다.

이번에도 알고리즘을 풀때 유용한 스캐너이다. 이번에도 예시를 들어보자

```
package com.suviavalcoding.kotlinbasic

import java.utill.*

func main() {
    val reader = Scanner(System.'in')
    reader.nextInt()
}
```
이렇게 작성해주면된다!

이번엔 조건문인데 예를들면

```
package com.suviavalcoding.kotlinbasic

func main() {
    val i = 5

    if (i > 10) {
        print("10보다 크다")
    } 
    else if (i > 5) {
        printf("5보다 크다)
    }
    else {
        printf("5보다 작다)
    }
}
```
이렇게 작성해줄수있고 if문은 아래 코드와같이 when으로 치환이 가능하다

```
package com.suviavalcoding.kotlinbasic

func main() {
    var i = 5

    when {
        i > 10 -> {
            print("10보다 크다")
        }
        i > 5 -> {
            print("5보다 크다)
        }
        else -> {
            print("5보다 작다")
        }
    }
}
```
이렇게 작성해줄수 있다. 그리고

func main() {
    val i = 5

    if (i > 10) {
        print("10보다 크다")
    } 
    else if (i > 5) {
        printf("5보다 크다)
    }
    else {
        printf("5보다 작다)
    }
}
```
이 코드에서 문자열을 반환하려면 

func main() {
    val i = 5

    if result = (i > 10) {
        "10보다 크다"
    } 
    else if (i > 5) {
        "5보다 크다"
    }
    else {
        "5보다 작다"
    }
    print(result)
}
```
이렇게 작성할수 있다.

코틀린에서도 반복문을 사용할 수 있는데 일단 예를 들어

```
package com.suviavalcoding.kotlinbasic

func main() {
    val items = listOf(1, 2, 3, 4, 5)

    for(item in items) {
        print(item)
    }
}
```
이렇게 작성해주게 되면 자바의 forEach문과 동일하게 사용해줄수 있다.
코틀린에서도 forEach를 사용할수 있는데

```
package com.suviavalcoding.kotlinbasic

func main() {
    val items = listOf(1, 2, 3, 4, 5)

    items.forEach { item ->
        print(item)
    }
}
```
이렇게 작성해주면 된다. 이 코드가 방금 코드와 동일한 코드이다.
일반적인 for문도 사용할수있는데

```
package com.suviavalcoding.kotlinbasic

func main() {
    val items = listOf(1, 2, 3, 4, 5)

    for(i in 0..items.size - 1) {
        print(items[i])
    }
}
```
위와같이 작성해줄수 있다. 0 부터 items까지 반복하게 된다. 
이 방식은 아주 귀찮기 때문에 처음에 작성했던것처럼 작성하면된다.

list는 for문에서 선언한것과 같이 작성하면 나중에 리스트에 추가 또는 삭제를 할수 없기때문에 추가 또는 삭제를 할수 있는 리스트를 만들때에는 아래와 같이 작성해야한다.

```
package com.suviavalcoding.kotlinbasic

func main() {
    val items = mutableListOf(1, 2, 3, 4, 5)
}
```
이렇게 작성해줘야하고 리스트에 추가할떄는 items.add(6) 삭제할때는 items.remove(3) 이렇게 작성해주면된다. 그리고 예외처리를 보도록 하겠다.

```
package com.suviavalcoding.kotlinbasic

func main() {
    val items = listOf(1, 2, 3)

    try {
        dal item = items[4]
    } catch(e: Excption) {
        print(e.message)
    }
}
```
위와 같이 작성해주게 되면 에러가 출력된다.

코틀린에는 널 세이프티라는 개념이 있다. 예를 들면

```
package com.survivalcoding.kotlinbasic

func main() {
    var name: String? = null
    name = "준석"
}
```
null에 타입을 지정해줄때는 타입뒤에 꼭 물음표를 붙여줘야한다.  

함수는 그냥 메인 함수밑에 작성해주면된다. 예를 들어 a와 b의 값을 더하는 함수를 만들고싶다면

```
package com.survivalcoding.kotlinbasic

fun main() {
    print(sum(10, 20))
}

fun sum(a: Int, b: Int) : Int {
    return a + b
}
```
이렇게 작성해주면된다. 그리고 메인함수같이 가장 바깥에 작성한 함수는 탑레벵 함수이기때문에 모든 파일에서 사용이 가능하다. 코틀린에섲 함수가 한줄밖에 없는 간단한 함수는 더 간단하게 작성할수 있다.

fun sum(a: Int, b: Int) : Int = a + b 이렇게 작성해주면된다. 

class도 알아보도록 하자. 예를 들어

```
package com.survivalcoding.kotlinbasic

fun main() {
    
}

class Person(val naem: String, var age: Int){
    

}
```
이렇게 작성해줄수 있는데 너무 길어진다면

```
package com.survivalcoding.kotlinbasic

fun main() {

}

class Person(
    val name: String,
    var age: Int
)
```
이렇게 작성할수 있다.

getter와 setter를 알아보도록 하자. 예를 들면

```
package com.survivalcoding.kotlinbasic

fun main() {
    val john = Person("John", 20)
    val john2 = Person("john", 20)

    john.age = 23
}

class Person(
    val name: String,
    var age: Int,
)
```
john과 john2는 같은 이름,나이를 가졌지만 전혀 다른 사람이다. 그렇기 때문에
println(john == john2)이렇게 비교를 해주면 false라는 값이 나온다.
근데 여기서 같은 이름,나이를 가졌다면 똑같은 사람으로 보겠다는 규칙을 만들고싶으면

```
package com.survivalcoding.kotlinbasic

fun main() {
    val john = Person("John", 20)
    val john2 = Person("john", 20)

    println(john)
    println(john2)
    println(john == john2)
}

class Person(
    val name: String,
    var age: Int,
) 
```
이렇게 작성해주면된다.

상속을 배워보도록 하자. 예를 들면

```
package com.survivalcoding.kotlinbasic

fun main() {
    val dog: Anumal = Dog()
    val cat = Cat()

    if (dog is Dog) {
        println("멍멍이")
    }
}

interface Drawable {
    fun draw()
}

abstract class Animal {
    open fun move() {
        print("이동")
    }
}

class Dog : Animal(), Drawable  {
    override fun move() {
        println("껑충")
    }
    override fun draw() {
        TODO("Not yet implemented")
    }
}

class Cat : Animal(), Drawable {
    override fun move() {
        println("살금")
    }

}
```
상속을 받았다면 꼭 함수앞에 open을 작성해주어야 오버라이드를 할수있다.
강제로 타일 캐스팅할 경우에는 is대신 as를 사용하면 된다.ㅣ

제네릭을 알아보도록하자

```
package com.survivalcoding.kotlinbasic

fun main() {
    val box = Box(10)
    val box2 = Box("dsfsd)

    print(box.va)
}
class Box<T>(val value: T) {

}
```
제네릭은 이렇게 사용화면 된다.

이제 콜백함수를 알아보도록하자.

```
package com.survivalcoding.kotlinbasic

fun main() {
    MyFunc({
        println("함수 호출")
    })
}

fun myFunc(callBack : () -> Unit) {
    println("함수 시작!!!")
    callBack()
    println("함수 끝!!!")
}
```
메인함수 쪽에서 myFunc의 소괄호롸 중괄호는 따로따로 써도 상관없다.
던달하는 매개변수가 하나밖에 없을경우엔 소괄호를 생략할수있다.

이제 서스펜드 함수를 알아보도록하자 서스펜드 함수는 함수앞에 suspend를 적어주면되고
서스펜드함수는 함수가 실행되고 나서 끝날때까지 정지하는 함수이다.