
# 브랜치란: 브랜치를 나누어 관리하는 이유

## 브랜치(branch)
  * 영어로 나뭇가지
  * 브랜치는 버전을 여러 개의 흐름으로 관리하는 방법
  * 브랜치는 `버전의 분기`

## 브랜치를 사용하는 이유 : 브랜치가 없다면?
  * 서로의 작업과 전혀 관련 없는 부분, 같은 코드를 다르게 수정한 부분 혼재
  * 일일이 수작업으로 합쳐야 함
  * 때로는 서로의 코드를 합치다 실수가 생길 수도

## 브랜치로 문제 해결하기
  * 브랜치는 버전의 분기
  * 브랜치로 버전의 분기를 관리하는 방법
    * 1.브랜치를 `나눈다`.
    * 2.각자의 브랜치에서 `작업한다`.
    * 3.(필요하다면) 나눈 브랜치를 `합친다`.

<a href='https://ifh.cc/v-swP7Mw' target='_blank'><img src='https://ifh.cc/g/swP7Mw.png' border='0'></a>

<a href='https://ifh.cc/v-7MtW8G' target='_blank'><img src='https://ifh.cc/g/7MtW8G.png' border='0'></a>

<a href='https://ifh.cc/v-N4Wkhh' target='_blank'><img src='https://ifh.cc/g/N4Wkhh.png' border='0'></a>

<br>

# 브랜치 나누기

## 브랜치의 이름
  * 최초의 브랜치, master 브랜치
    * 지금까지 여러분이 만든 커밋들은 모두 기본적으로 master 브랜치에 속해있다.

<a href='https://ifh.cc/v-27MpoQ' target='_blank'><img src='https://ifh.cc/g/27MpoQ.png' border='0'></a>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
＊ master 브랜치 : 커밋 네 개 , foo 브랜치 : 커밋 다섯 개, bar 브랜치 : 커밋 여섯 개

  * 브랜치 이름을 마음대로 지어도 되나?
    * 실무에서는 브랜치의 이름을 암묵적으로 정한다. → 브랜치가 무엇을 위해 만들어졌는지 알 수 없기 때문.
    * 목적에 따라 브랜치 이름 관리
      * 새로운 기능을 개발하기 위한 브랜치 : feature/<새 기능>
      * 릴리즈를 준비하기 위한 브랜치 : release/<릴리즈 번호>
      * 급하게 수정해야 하기 위한 브랜치 이름 : hotfix/<수정 사항>

<a href='https://ifh.cc/v-PmPbpG' target='_blank'><img src='https://ifh.cc/g/PmPbpG.png' border='0'></a>

## 특정 브랜치에서 작업하기 : HEAD와 체크아웃
  * HEAD
    * 현재 작업 중인 브랜치의 커밋을 가리킨다.
    * 일반적으로 현재 작업 중인 브랜치의 `최신 커밋`을 가리킨다.
    * 한 마디로 “내가 지금 어디에서 작업 중인가”를 가리킨다.
    * 브랜치를 나누고 합치는 과정에서 HEAD의 위치를 자유자재로 바꿀 수 있음.
  * 체크아웃
    * 특정 브랜치에서 작업할 수 있도록 작업 환경을 바꾸는 것
    * HEAD의 위치를 특정 브랜치의 최신 커밋으로 옮김
    * 작업 디렉터리는 체크아웃한 브랜치의 모습으로 바뀜

<a href='https://ifh.cc/v-HlWjPM' target='_blank'><img src='https://ifh.cc/g/HlWjPM.png' border='0'></a>

<br>

# 브랜치 합치기

* 브랜치를 합친다. = 브랜치를 `병합(merge)`한다.
* 빨리 감기 병합(fast-forward merge)

<a href='https://ifh.cc/v-Xt5yKb' target='_blank'><img src='https://ifh.cc/g/Xt5yKb.png' border='0'></a>

  * foo 브랜치가 뻗어 나오고, foo 브랜치에 커밋이 쌓이고, 병합되는 순간까지 `master 브랜치에 어떤 변화도 없었다.` 그래서 master 브랜치는 `마치 빨리감기`하듯 그저 foo 브랜치에서 추가된 커밋을 반영하기만 하면 된다.
  * 변화가 없었던 브랜치가 `마치 빨리 감기 하듯` 업데이트되는 병합 기법을 `빨리 감기 병합(fast-forward merge)`이라고 한다.


* 새로운 커밋 생성
  * 그럼, 빨리감기 병합이 아닌 병합은?
    * bar 브랜치에는 없는 커밋이 master 브랜치에 있고,
master 브랜치에는 없는 커밋이 bar 브랜치에 있는 상태
→ 두 브랜치를 병합한 `새로운 커밋`이 생성된다.

<a href='https://ifh.cc/v-V6LTWy' target='_blank'><img src='https://ifh.cc/g/V6LTWy.png' border='0'></a>

```
TIP!
브랜치를 삭제하려면 삭제하려는 브랜치가 아닌 다른 브랜치에 체크아웃되어 있어야 한다.
즉, foo 브랜치를 삭제하려면 foo브랜치가 아닌 master브랜치 또는 bar브랜치로 체크아웃되어 있어야 한다.
```

<br>

# 브랜치 충돌

* 충돌
  * 병합하려는 두 브랜치가 서로 같은 내용을 다르게 수정한 상황

<a href='https://ifh.cc/v-jN2BFZ' target='_blank'><img src='https://ifh.cc/g/jN2BFZ.png' border='0'></a>

  1. master 브랜치는 a.txt 파일의 첫 번째 줄을 B로 수정한 후 커밋
  2. foo 브랜치는 a.txt 파일의 첫 번째 줄을 C로 수정한 다음 커밋
  3. 충돌 발생

```
TIP!
1.충돌을 해결한다(어떤 브랜치의 내용을 반영할지 직접 선별한다).
2.다시 커밋한다.
```

* 충돌 해결하기
  * 충돌 발생 시, 충돌이 발생한 파일의 `충돌을 해결한 뒤 다시 커밋` 해야만 브랜치가 올바로 병합됨.
  * 충돌을 해결한다. = `같은 내용을 다르게 수정한 브랜치 중 어떤 브랜치 내용을 최종적으로 반영할지를 직접 선택하는 것.` 

<a href='https://ifh.cc/v-8TcpWv' target='_blank'><img src='https://ifh.cc/g/8TcpWv.png' border='0'></a>

<br>

# 브랜치 재배치

* rebase : 브랜치가 뻗어나온 기준점을 변경하는 것

<a href='https://ifh.cc/v-pHZ7bJ' target='_blank'><img src='https://ifh.cc/g/pHZ7bJ.png' border='0'></a>

```
TIP!
브랜치를 재배치하는 과정에서도 충돌 발생 할 수 있음. 충돌 해결 방법 동일.
```

