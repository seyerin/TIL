## static

"고정된" 이라는 의미로 클래스에 고정되어 있는 변수나 메서드

Static 키워드를 통해 생성된 정적멤버들은 heep 영역이 아닌 Static 영역에 할당 됨

특징

1. 메모리에 고정적으로 할당된다.

2. 객체 생성 없이 사용할 수 있다.

3. 프로그램이 시작되면 메모리의 static 영역에 적재되고, 프로그램이 종료될 때 해제된다.

4. Static 메서드 내에서는 인스턴스 변수를 사용할 수 없다.

장점

static 영역에 할당된 메모리는 모든 객체가 공유하여 하나의 멤버를
어디서든 참조할 수 있음

단점

garbage collection의 관리영역 밖에 존재하기 때문에 static 영역에 있는 멤버들은 프로그램을 종료할 때까지 메모리가 할당된 채로 존재하게 됨

---

class Number{
static int num = 0;
int num2 = 0;
}

public class Temp {
public static void main(String [] args){
Number a1 = new Number();
Number a2 = new Number();

    a1.num++;
    a1.num2++;

    System.out.println(a2.num +" " + a2.num2);

}
}

출력: 1 0

**static 변수는 모든 인스턴스가 하나의 저장 공간을 공유**하기 때문에 a2.num에 숫자를 더하지 않고 a1.num에 숫자를 더해 주어도 동일한 값이 나온다

그러나 인스턴스 변수는 각기 다른 저장공간을 가지기 때문에 a2.num2++라고 직접적으로 값을 더해주는게 아니라면 a2.num2의 값은 변하진 않는다
