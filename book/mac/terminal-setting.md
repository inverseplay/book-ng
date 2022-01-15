## 터미널 설정 가이드
```md
터미널은 bash 라고 처보면, 현재의 터미널이 나타난다.
기본 쉘이 zsh 로 변경된 경우, 아래와 같은 코드를
.zshrc 에 넣어주면 커스텀 함수를 사용할수 있다.


```
## 터미널 설정

```bash

# Reset
NC='\033[0m'       # Text Reset

# Regular Colors
Black='\033[0;30m'        # Black
Red='\033[0;31m'          # Red
Green='\033[0;32m'        # Green
Yellow='\033[0;33m'       # Yellow
Blue='\033[0;34m'         # Blue
Purple='\033[0;35m'       # Purple
Cyan='\033[0;36m'         # Cyan
White='\033[0;37m'        # White

lets_code () {
   echo "${Blue}let's code!${NC}"
}

lets_code

g0 () {
    x=$1
    if [ $# -eq 0 ]; then
        x='i'
    fi
    echo "${Green}=== git init === ${NC}"
    git init
    echo "${Green}=== git add . === ${NC}"
    git add .
    git status 
    echo "${Green} === git commit -m $x ===${NC} "
    git commit -m $x
}

g1 () {
    x=$1
    if [ $# -eq 0 ]; then
        x='i'
    fi
    echo "${Yellow} === git commit $x ===${NC} "
    git add .
    git commit -m $x
    echo " "
    
    echo "${Green} === git push origin main ===${NC} "
    git push origin main
    echo " "
}

```