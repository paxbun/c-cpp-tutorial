# 포인터와 배열

포인터와 배열에 대해 알아보고, 변수를 입력받는 방법에 대해 배웁니다.

## 메모리 주소(memory address)

[2장](../2-structure-of-computers)에서 메모리는 책장처럼 생긴 장치라는 것을 설명했습니다. 책장의 각 공간엔 밑에서부터 차례대로 번호가 붙어있다고 했었죠. 이 번호를 실제로는 `메모리 주소(memory address)`라고 합니다. C에선 이 메모리 주소에 대해 덧셈과 뺄셈을 할 수 있는 기능을 제공하는데요, 이 때 `포인터(pointer)`라고 하는 자료형이 사용됩니다. 포인터는 메모리 주소를 담고 있는 자료형입니다. 즉, 일단 수학적으로 봤을 때 들어있는 형태는 정수입니다. 예를 들어 `int a`가 주소 36\~39를 차지하고 있다고 해봅시다. 그럼 포인터를 하나 만들고, 거기에 `int a`를 저장하는 공간의 가장 밑부분인 `36`을 그 포인터에 저장할 수 있습니다. 이 메모리 주소에 원하는 정수를 더하거나 빼는 것도 가능합니다.

## 포인터 선언하기

포인터 변수는 변수를 선언할 때, 변수 앞에 `*`를 붙여서 선언할 수 있습니다.
> 별표`*`는 사실 `애스터리스크(asterisk)`라는 이름이 있는데요, 다들 별표나 star라고 부릅니다.
```c
int main()
{
    int *i, *j, k = 15;
}
```
변수 `k`에 `15`가 대입될 수 있다는 점에 주목해주세요. `k`에는 `*`가 붙지 않았기 때문에, `k`는 포인터가 아니라, 그냥 자료형이 `int`인 변수입니다. 반대로, `i`와 `j`는 포인터입니다. 포인터를 사용할 때 자료형을 함께 사용해야 하는 이유는 이제 차차 다루고자 합니다.