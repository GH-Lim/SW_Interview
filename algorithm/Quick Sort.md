# Quick Sort

## 퀵소트 란?

불안정 정렬 ( 같은 값을 가진 원소들의 순서가 바뀔 수 있다. )

비교 정렬 ( 다른 원소와의 비교만으로 정렬을 수행한다. )

분할 정복 알고리즘

- 문제를 작은 2개의 문제로 분리하고 각각을 해결한 뒤 결과를 모아 원래의 문제를 해결
- Merge sort 와 달리 리스트를 비균등하게 분할

과정 요약

1. 리스트 안에 있는 요소를 선택한다. 이 요소를 피벗(pivot) 으로 설정한다.

2. 오름차순의 경우 피벗을 기준으로 피벗보다 작은 값은 왼쪽, 큰 값은 오른쪽으로 이동시킨다.

3. 피벗을 제외한 왼쪽 리스트와 오른쪽 리스트를 다시 정렬한다.

4. 분할 된 부분 리스트들에 대해서 1 ~ 3 과정을 부분 리스트의 크기가 0 또는 1이 될 때까지 반복한다.

   <img src="https://gmlwjd9405.github.io/images/algorithm-quick-sort/quick-sort-concepts.png" alt="정렬 과정" width="250;" />

시간 복잡도

- 최선의 경우

  - 순환 호출의 깊이

    레코드의 개수 n이 2의 거듭제곱이라면 순환호출 횟수 k= log₂n 이다.

  - 각 순환 호출 단계의 비교 연산 횟수는 평균 n 번이다.

  - 따라서 k * n = n log₂n

  <img src="https://gmlwjd9405.github.io/images/algorithm-quick-sort/sort-time-complexity-etc1.png" alt="최선의 경우" width="600;" />

  이동횟수는 무시할 수 있으므로 O(n logn)

- 최악의 경우

  - 리스트가 계속 불균형하게 나뉘어지는 경우 순환 깊이가 n 이 된다.

    ex) 오름차순의 경우 피봇이 항상 최소값 (혹은 이미 정렬 된 경우)

  - 각 순환 호출 단계에서 비교 연산의 횟수도 평균 n 번이다.

  - 따라서 k * 비교연산 횟수 = n^2

    <img src="https://gmlwjd9405.github.io/images/algorithm-quick-sort/sort-time-complexity-etc2.png" alt="최악의경우" width="350;" />

  O(n^2)

- 평균

  O(nlogn)

  시간 복잡도가 같은 nlogn인 다른 정렬 알고리즘보다도 빠르다.

  퀵 정렬은 불필요한 데이터의 이동을 줄일 수 있고 먼 거리의 데이터도 교환 가능하며 한번 결정된 피벗들은 추후 연산에서 제외시키기 때문이다.



## 분할 방법

호어 파티션 방법과 로무토 파티션 방법 등이 있다.

참고 링크 https://ldgeao99.tistory.com/376 



