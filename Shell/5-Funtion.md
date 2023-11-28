# Funtion
코드를 통해 개발하는 과정 중 중요한 요점이 있다면 중복성 제거일 것이다. 반복적이거나 모듈화 시킬 필요가 있는 변수, 로직들을 묶어 사용하는 Funtion 사용법에 대해 알아보자.

## Function 구조
쉘 스크립트에서 Funciton을 사용하는 방법에는 다음과 같다.
```bash
functionName() {
    Logic......
}
```
## Function Returning
다른 프로그래밍 언어를 사용하다보면 함수에서 ``return``을 많이 봤을것이다. 잠시 검색을 통해 알아보면 ``return``이라는 단어를 쉘 스크립트에서 볼수가 없다.
따라서 ``return`` 대신 함수에서 ``echo``를 통해 출력되는 내용을 반환받을 곳에서 변수에 대입해주는 형태로 만들어주도록 한다.
```bash
functionName(){
    echo "Hello World";
}

res=$(functionName)
echo $res;
```
## Function Import

모든 코드를 직접 작성할수는 있지만 많은 시간과 지식이 필요로 한다. 따라서 대부분의 개발자들을 타인이 미리 작성해놓은 함수, 변수 등이 담긴 라이브러리를 포함시켜 개발을 하게된다.
Shell Script에서는 파일을 포함시켜 사용한다.

./testutil.sh
```bash
#!/bin/bash
functionName(){
    echo "Hello World";
}

```
./test.sh
```bash
#!/bin/bash
. ./test_util.sh --source-only

echo $(functionName)
```