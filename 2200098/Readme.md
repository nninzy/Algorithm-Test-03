# 2200098 김민지 모의고사 후기

## 전체 총평

문제가 생각해야하는 과정이 많은 문제들이 대부분이었다. 순서대로 과정을 분리해도 각각의 과정을 코드로 구현하는 과정에서 헷갈리는 경우가 많았다. 앞으로 이와 같은 과정이 많은 문제들을 실수없이 푸는 방법에 대해서 고민해봐야겠다.

---

## [5432. 민석이의 과제 체크하기 (D3)](5431.py)

메모리 (65,948KB), 실행시간(380ms), 코드길이(354B)

- 풀이 방식 및 접근방법 관련 아이디어 :

  ![](5431.jpg)

  1. 전체 학생 수만큼의 0을 가진 list `students` 세팅

  2. 제출한 학생의 번호를 입력받은 list `submits` 세팅

  3. 각각의 학생 번호는 students 인덱스에서 1씩 추가한 값이므로, students 내 제출한 학생의 번호 - 1의 인덱스에 해당하는 값을 1로 변환

  4. students 내 값이 0인 인덱스값 + 1은 제출하지 않은 학생의 번호인 점을 이용해, 미제출자 list `answers`에 해당 학생의 인덱스를 입력 후 unpacking 출력

- 후기 :

  다른 풀이 방법은 생각나지 않았다. 인덱스와 번호의 관계를 생각해서 출력하는 부분에서 실수가 발생할 수 있을 것 같은데 이 부분을 보완할 방법을 생각해봐야겠다.

---

## [2001. 파리 퇴치 (D2)](2001.py)

메모리 (61,212KB), 실행시간(174ms), 코드길이(452B)

- 풀이 방식 및 접근방법 관련 아이디어 :

  ![](2001.jpg)

  1. 이중 리스트 `matrix`안에 각각의 행마다의 숫자를 입력 받음
  2. start_point는 행, 열마다 0 이상 N-M+1 미만이므로 range setting에 주의하면서 3중 for문을 짠다. 가장 안쪽에 있는 for문은 파리퇴치가 M \* M 이므로 파리퇴치 구간 내 있는 모든 수의 합을 구하기 위해 해당하는 각 행을 더하기 위한 장치다.
  3. 정답이 될 수 있는 후보들의 리스트 `answers` 중 우리가 원하는 정답은 파리퇴치 구간의 합 중 최대 이기에 `max()` 내장함수를 활용해서 answer를 구한다.

- 후기 :

  파리퇴치와 같은 이중 리스트 문제의 포인트는 구간의 시작지점과 끝지점, 그 범위를 설정하는 것 같다. 아직은 이 문제가 바로 생각나지 않기 때문에 연습이 필요한 것 같다.

---

## [1983. 조교의 성적 매기기 (D2)](1938.py)

메모리 (58,780KB), 실행시간(166ms), 코드길이(586B)

- 풀이 방식 및 접근방법 관련 아이디어 :

  ![](1983.jpg)

  1. 입력받은 각각의 학생의 중간, 기말, 과제 점수를 `mid`, `last`, `task`로 입력을 받고 각각에 해당하는 비율을 곱해서 총합을 구한다.
  2. 총합과 학생의 번호 (입력 순서에 따른 것이기에 for문의 n에 해당)을 리스트로 묶어서 학생들의 총점과 번호를 담은 list `students`에 담는다.
  3. students를 내부 인덱스 0의 값에 따른 순서대로 두기 위해 sort를 한다. sort를 할 경우 인덱스 0에 해당하는 사람은 총점 최저이기에 sort 내부 argument `reverse = True`로 설정한다.
  4. 알고자하는 학생 번호 k를 인덱스 1 위치에 가진 값의 인덱스 0 위치의 등수 i를 구한다 (단 여기서 등수는 0등부터 시작한다.)
  5. 학생의 평점은 학생의 등수를 평점 당 인원 수로 나눈 몫의 인덱스를 가진 평점이다.

- 후기 :

  가장 고민이었던 부분은 등수에 따라서 평점을 어떻게 할당하는가였다. 이를 위해서 예시 등수를 생각해서 평점 어디에 해당하는지 확인하는 작업을 먼저 했다.
  또한 과정 중 sort를 하면서 1등이 가장 앞에 올 것이라고 착각해서 한번 틀린 답을 냈었다. 설계를 할 때 내가 쓴 내장 함수, 메서드가 어떤 return값을 가질지 생각하는 연습이 필요할 것 같다.

---

## [1979. 어디에 단어가 들어갈 수 있을까 (D2)](1979.py)

메모리 (58,524KB), 실행시간(157ms), 코드길이(827B)

- 풀이 방식 및 접근방법 관련 아이디어 :

  ![](1979.jpg)

- 후기 :

  이 문제 역시 풀이 과정이 여러가지가 나올 것이라고 생각한다. 내가 가장 잘하는 접근 방식이 하나씩 count한 후 그 값을 정답 후보군 list에 담는 것이라고 생각해서 위와 같은 접근 방법을 선택했지만 count 하는 과정은 초기값을 어느 지점에서 setting 하는 것이 중요한지 아는 것이 중요하다고 생각한다. 아마 이 문제는 수업 중 선생님께서 말씀해주신 for문을 무의식적으로만 풀이하는 경우 발생하는 문제와 같다고 생각한다. for문을 중첩할 경우 각각의 과정에서 어떻게 진행될지, 반복 순서가 특정 수일 때는 for문 반복이 어떻게 진행되는지를 생각해보는 연습이 필요한 것 같다.

---

## [1218. [S/W 문제해결 기본] 4일차 - 괄호 짝짓기 (D4)](1218.py)

메모리 (58,760KB), 실행시간(186ms), 코드길이(942B)

- 풀이 방식 및 접근방법 관련 아이디어 :

  ![](1218.jpg)

- 후기 :

  괄호 짝짓기 문제 역시 접근하는 방법이 많다고 생각한다. 각각의 괄호가 제대로 열고 닫힌 것인지 고민하는 문제가 아니라 쌍이 맞는지만 확인하는 문제이기에 접근 방식이 다양할 수 있었던 것 같다. 하지만 각각의 과정 역시 추가적으로 조건이 생긴다면 해결할 수 없는 문제가 생긴다. 시간이 부족해서 내가 가장 자신있는 방법으로 풀었지만 오늘 문제들을 리팩토링하는 과정에서 다른 풀이 방법들도 생각해봐야겠다.

## [1225. [S/W 문제해결 기본] 7일차 - 암호생성기 (D3)](1225.py)

메모리 (61,724KB), 실행시간(213ms), 코드길이(425B)

- 풀이 방식 및 접근방법 관련 아이디어 :

- 후기 :
  시간이 부족해서 노트에 작성하고 풀지 않았다. while문과 while문 내 for문에서 반복 과정을 컨트롤하기 위해 같은 조건을 계속 언급해서 코드가 깔끔하지 못했다는 느낌을 받았다. 중복을 피하고 조건을 잘 컨트롤하는 방법을 생각하며 코드를 다시 정리해봐야겠다.

---