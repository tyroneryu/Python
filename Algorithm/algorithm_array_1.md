# Array
## 과정 소개
- 학습 내용
    - 자료구조와 알고리즘
- 학습 목표
    - 논리적 사고력 향상
    - 문제 해결 능력 향상
    - 최종 목표는 연습 문제가 아닌 **현실 세계 문제**
- 학습 도구
    - Python

## 알고리즘
- 유한한 단계를 통해 **문제를 해결하기 위한 절차나 방법**임. 주로 컴퓨터 용어로 쓰이며, 컴퓨터가 어떤 일을 수행하기 위한 단계적 방법을 말함
- 간단하게 다시 말해 어떠한 문제를 해결하기 위한 절차라고 볼 수 있음
- 컴퓨터 분야에서 알고리즘을 표현하는 방법은 크게 두 가지
    - 의사코드(슈도 코드, Pseudocode)
    ```python
    Calsum(n)
        sum = 0
        for i in n
            sum += i
        return sum
    ```

### 알고리즘의 성능
- APS 과정의 목표 중 하나는 보다 좋은 알고리즘을 이해하고 횔용하는 것
- 좋은 알고리즘
    1. 정확성: 얼마나 정확하게 동작하는가
    2. 작업량: 얼마나 적은 연산으로 원하는 결과를 얻어내는가
    3. 메모리 사용량: 얼마나 적은 메모리를 사용하는가
    4. 단순성: 얼마나 단순한가
    5. 최적성: 더 이상 개선할 여지없이 최적화되었는가
- 주저진 문제를 해결하기 위해 여러 개의 다양한 알고리즘이 가능
    어떤 알고리즘을 사용해야 하는가
- 알고리즘의 성눙 분석 필요
    - 많은 문제에서 성능 분석의 기준으로 알고리즘의 작업량을 비교함
- 알고리즘의 작업량을 표현할 때 시간복잡도로 표현함

### 시간 복잡도 (Time Complexity)
- 실제 걸리는 시간을 측정
- 실행되는 명령문의 개수를 계산
- 알고리즘 1
```python
def CalSum(n):
    sum = 0
    for i in range(1, n + 1):
        sum += i
    return sum              # 1 + n * 2 = 2 * n + 1
```
- 알고리즘 2
```python
def CalSum(n):
    return n * (n + 1) // 2 # 3번의 연상
```

#### 빅-오(O) 표기법
- Big-O Notation
- 시간 복잡도 함수 중에서 가장 큰 영향력을 주는 n에 대한 항만을 표시
- 계수 (Coefficient)는 생략하여 표시
- 예시
    - O(3n + 2) = O(3n) = O(n)
    - 최고차항 (3n)만 선택, 계수 3제거
    - O(2n^2 + 10n + 100) = O(n^2)
    - O(4) = O(1)
- n개의 데이터를 입력받아 저장한 후 각 데이터에 1씩 증가시킨 후 각 데이터를 화면에 출력하는 알고리즘의 시간복잡도는?
    - O(n)
- 요소 수가 증가함에 따라 각기 다른 시간복잡도의 알고리즘은 연산 수가 다름

## 배열
- 일정한 자료형의 변수들을 하나의 이름으로 열거하여 사용하는 자료구조
- 6개의 변수를 사용해야 하는 경우, 이를 배열로 바꾸어 사용하는 예
```python
num0 = 0
num1 = 1
num2 = 2
num3 = 3
num4 = 4
num5 = 5

num = [0, 1, 2, 3, 4, 5]
```
### 배열의 필요성
- 프로그램 내에서 여러 개의 변수가 필요할 때, 일일이 다른 변수명을 이용하여 자료에 접근하는 것은 매우 비효율적일 수 있음
- 배열을 사용하면 하나의 선언을 통해서 둘 이상의 변수를 선언할 수 있음
- 단순히 다수의 변수 선언을 의미하는 것이 아니라, 다수의 변수로는 하기 힘든 작업을 배열을 활용해 쉽게 할 수 있음

### 1차원 배열
- 1차원 배열의 선언
    - 별도의 선언 방법이 없으면 변수에 처음 값을 할당할 때 생성
    - 이름: 프로그램에서 사용할 배열의 이름
    - 예시
    ```python
    Arr = list()
    Arr = []
    Arr = [1, 2, 3]
    Arr = [0] * 10
    ```
- 1차원 배열의 접근
    - Arr[0] = 10       # 배열 Arr의 0번 원소에 10을 저장하라
    - Arr[idx] = 20     # 배열 Arr의 idx번 원소에 20을 저장하라

### 연습 문제
- Gravity
- 상자들이 쌓여있는 방이 있다. 방이 오른쪽으로 90도 회전하여 상자들이 중력의 영향을 받아 낙하한다고 할 때, 낙차가 가장 큰 상자를 구하여 그 낙차를 리턴하는 프로그램을 작성하시오.
- 중력은 회전이 완료된 후 적용된다.
- 상자들은 모두 한쪽 벽면에 붙어진 상태로 쌓여 2차원의 형태를 이루며 벽에서 떨어져서 쌓인 상자는 없다.
- 상자의 가로, 세로 길이는 각각 1이다.
- 방의 가로길이는 100이며, 세로 길이도 항상 100이다.
- 즉, 상자는 최소 0, 최대 10 높이로 쌓을 수 있다.
- 상자가 놓인 가로 칸의 수 N, 다음 줄에 각 칸의 상자 높이가 주어진다.    
![사진1](./asset/Algo01.PNG)
- 그림 설명
    - 입력 예시
    ```python
    9
    7 4 2 0 0 6 0 7 0
    ```
    - 총 26개의 상자가 회전 후, 오른쪽 방 그림의 상태가 된다. A 상자의 낙차가 7로 가장 크므로 7을 리턴하면 된다.
    - 회전 결과, B상자의 낙차는 6, C상자의 낙차는 1이다.
- 답
```python
N = int(input())    # 상자가 쌓여 있는 가로 길이
arr = list(map(int, input().split()))

max_v = 0           # 가장 큰 낙차
for i in range(N - 1):  # 낙차를 구할 위치
    cnt = 0         # 오른쪽에 있는 더 낮은 높이
    for j in range(i + 1, N):    # for j: 
        if arr[i] > arr[j]:
            cnt += 1
    if max_v < cnt: # 최대 낙차보다 크면
        max_v = cnt
print(max_v)
```

## 정렬
- 2개 이상의 자료를 특정 기준에 의해 작은 값부터 큰 값(오름차순: ascending), 혹은 그 반대의 순서대로(내림차순: descending) 재배열하는 것
- 키
    - 자료를 정렬하는 기준이 되는 특정 값
- 대표적인 정렬 방식의 종류
    - 버블 정렬 (Bubble Sort)
    - 카운팅 정렬 (Counting Sort)
    - 선택 정렬 (Selection Sort)
    - 퀵 정렬 (Quick Sort)
    - 삽입 정렬 (Insertion Sort)
    - 병합 정렬 (Merge Sort)
- APS 과정을 통해 자료구조와 알고리즘을 학습하면서 다양한 형태의 정렬을 학습하게 됨

### 버블 정렬
- 인접한 두 개의 원소를 비교하며 자리를 계속 교환하는 방식
- 정렬 과정
    - 첫번째 원소부터 인접한 원소끼리 계속 자리를 교환하면서 맨 마지막 자리까지 이동함
    - 한 단계가 끝나면 가장 큰 원소가 마지막 자리로 정렬됨
    - 교환하며 자리를 이동하는 모습이 물 위에 올라오는 거품 모양과 같다고 하여 버블 정렬이라고 함
- 시간 복잡도
    - O(n^2)
- 배열을 활용한 버블 정렬
- 오름차순
```python
def BubbleSort(a, N)                # 정렬할 배열과 배열의 크기
    for i in range(N - 1, 0, -1):   # 정렬될 구간의 끝
        for j in range(0, i):       # 비교할 원소 중 왼쪽 원소의 인덱스
            if a[j] > a[j + 1]:     # 왼쪽 원소가 더 크면
                a[j], a[j + 1] = a[j +1], a[j]
```
- 내림차순
```python
def dec(arr, N)                     # 정렬할 배열과 배열의 크기
    for i in range(N - 1, 0, -1):   # 정렬될 구간의 끝
        for j in range(i):          # 비교할 원소 중 왼쪽 원소의 인덱스
            if arr[j] < arr[j + 1]: # 왼쪽 원소가 더 작으면
                arr[j], arr[j + 1] = arr[j +1], arr[j]
```
