
# revert, reset, stash



## 작업 되돌리기
  * 만들어진 버전을 되돌리는 두 가지 방법
    * revert : 버전을 되돌린 새로운 버전 만들기
    * reset : 버전을 완전히 되돌리기
      * **soft reset** :  ~~저장소로 커밋하기~~
      * **mixed reset** :  ~~스테이지로 추가하기~~ 
      * **hard reset** :  ~~작업 디렉터리에서 변경 사항 생성하기~~


## revert
<a href='https://ifh.cc/v-qFvn48' target='_blank'><img src='https://ifh.cc/g/qFvn48.png' border='0'></a>


## reset
<a href='https://ifh.cc/v-AK0S2l' target='_blank'><img src='https://ifh.cc/g/AK0S2l.png' border='0'></a>


## reset의 종류

| 종류 | 내용 |
| ---- | --- |
| soft reset |	커밋만 되돌리기 |
| mixed reset |	스테이지까지 되돌리기 |
| hard reset |	작업 디렉터리까지 되돌리기 |

<a href='https://ifh.cc/v-J3SaDl' target='_blank'><img src='https://ifh.cc/g/J3SaDl.png' border='0'></a>

<a href='https://ifh.cc/v-Sxpfqa' target='_blank'><img src='https://ifh.cc/g/Sxpfqa.png' border='0'></a>


## stash
  * 임시 저장 기능
  * 썩 마음에 들지 않지만 버리기는 아까울 때
  * 다른 더 중요한 일을 처리해야 할 때

<a href='https://ifh.cc/v-4HbYms' target='_blank'><img src='https://ifh.cc/g/4HbYms.png' border='0'></a>

  * 임시 저장된 변경 사항들은 언제든 다시 꺼내어 작업 디렉터리에 다시 적용할 수 있다.

<a href='https://ifh.cc/v-o80T6a' target='_blank'><img src='https://ifh.cc/g/o80T6a.png' border='0'></a>

  * 스태시를 사용할 수 있는 파일
    * 깃이 변경 사항을 추적하는(tracked) 파일에만 사용 가능.
    * 스테이지에 이미 올라와 있거나 한 번이라도 커밋한 적이 있는 파일에만 사용할 수 있다.
    * 방금 막 생성한 파일처럼 깃이 기존에 변경 사항을 추적하지 않은(untracked)파일에는 스태시를 사용할 수 없다.
