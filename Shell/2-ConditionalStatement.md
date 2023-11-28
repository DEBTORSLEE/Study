# Conditional Statement
가정법, 조건문이라 불리는 if, else, elif에 대해 알아보자.

---
## 구조
기본적인 구조는 ``if 조건; then``로 시작해서 ``fi``로 끝난다.
else나 else에 조건을 주고싶다면 ``elif 조건; then``을 사용하여 조건문을 사용하게돈다.
1) if
```
if 조건; then
    실행문......
fi
```
2) else
if 조건; then
    실행문......
else
    실행문......
fi
3) elif
```
if 조건; then
    실행문......
elif 조건; then
    실행문...... 
else
    실행문......
fi
```
## 조건식
기본적인 조건식은 아래와 같다.
```
값or변수 조건 값or변수
```
Shell Sript에서는 약어를 이용해 비교할 수 있다.
```
if [ 1 -qe 1]; then
    echo "둘다 1입니다."
fi
```
### 비교연산자
1) ``==`` / ``-eq``
```
if [[ ${a} == "ex" ]]; then
    echo "ex입니다."
else
    echo "ex가 아닙니다."
fi
```
```
if [ ${a} -eq "ex"]; then
    echo "ex입니다."
else
    echo "ex가 아닙니다."
fi
```

2) ``!=`` / ``-ne``
```
if [[ ${a} != "ex" ]]; then
    echo "ex가 아닙니다."
else
    echo "ex입니다."
fi
```
```
if [ ${a} -ne "ex" ]; then
    echo "ex가 아닙니다."
else
    echo "ex입니다."
fi
```
3) ``>``/``-gt``
```
if [[ ${a} > 0 ]]; then
    echo "0보다 큽니다."
else
    echo "0보다 크지 않습니다."
fi
```
```
if [ ${a} -gt 0 ]; then
    echo "0보다 큽니다."
else
    echo "0보다 크지 않습니다."
fi
```
4) ``>=``/``-ge``
```
if [[ ${a} >= 0 ]]; then
    echo "0보다 크거나 같습니다."
else
    echo "0보다 크지 않거나 같습니다."
fi
```
```
if [ ${a} -ge 0 ]; then
    echo "0보다 크거나 같습니다."
else
    echo "0보다 크지 않거나 같습니다."
fi
```
5) ``<``/``-lt``
```
if [ ${a} > 0 ]; then
    echo "0보다 작습니다."
else
    echo "0보다 작지 않습니다."
fi
```
```
if [ ${a} -lt 0 ]; then
    echo "0보다 작습니다."
else
    echo "0보다 작지 않습니다."
fi
```
6) ``<=``/``-le``
```
if [[ ${a} > 0 ]]; then
    echo "0보다 작거나 같습니다."
else
    echo "0보다 작지 않거나 같습니다."
fi
```
```
if [ ${a} -le 0 ]; then
    echo "0보다 작거나 같습니다."
else
    echo "0보다 작지 않거나 같습니다."
fi
```
7) ``&&``/``-a``
```
if [[ ${a} == 0 && ${b} == 1 ]]; then
    echo "a==0과 b==1 두 비교값이 모두 참입니다."
else
    echo "a==0과 b==1 두 비교값이 모두 참이 아닙니다."
fi
```
```
if [ ${a} == 0 -a ${b} == 1 ]; then
    echo "a==0과 b==1 두 비교값이 모두 참입니다."
else
    echo "a==0과 b==1 두 비교값이 모두 참이 아닙니다."
fi
```
8) ``||``/``-o``
```
if [[ ${a} == 0 || ${b} == 1 ]]; then
    echo "a==0과 b==1 두 비교값 중 하나라도 참입니다."
else
    echo "a==0과 b==1 두 비교값 모두 참이 아닙니다."
fi
```
```
if [ ${a} == 0 -o ${b} == 1 ]; then
    echo "a==0과 b==1 두 비교값 중 하나라도 참입니다."
else
    echo "a==0과 b==1 두 비교값 모두 참이 아닙니다."
fi
```

### 파일연산자
1) -f
Reguar 파일이면 참 반환
```
if [ -d "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
2) -d
디렉터리면 참 반환
```
if [ -d "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
3) -L
심블릭 링크이면 참 반환
```
if [ -L "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
4) -S
소켓파일이면 아니면 참 반환
```
if [ -S "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
5) -r
본인 권한이 r이면 참 반환
```
if [ -r "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
6) -w
본인 권한이 w이면 참 반환
```
if [ -w "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
7) -x
본인 권한이 x이면 참 반환
```
if [ -x "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
8) -s
크기가 0이 아니면 참 반환
```
if [ -s "Desktop" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
9) 파일1 -nt 파일2
파일1이 파일2보다 최신파일이면 참 반환
```
if [ "Desktop" -nt ".ssh" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
10) 파일1 -ot 파일2
파일1이 파일2보다 오래된파일이면 참 반환
```
if [ "Desktop" -ot ".ssh" ]; then
  echo "참"
else 
  echo "거짓"
fi
```
11) 파일1 -et 파일2
파일1이 파일2와 같은 파일이면 참 반환
```
if [ "Desktop" -ot ".ssh" ]; then
  echo "참"
else 
  echo "거짓"
fi
```