# 선택 정렬(Selected Sort)
해당 순서에 원소를 넣을 위치는 이미 정해져 있고, 어떤 원소를 넣을지 선택하는 알고리즘
***
### Process
> 1. 주어진 배열에서 최솟값을 찾는다.
> 2. 그 값을 맨 앞에 위치한 값과 교체한다
> 3. 맨 처음 위치를 뺀 나머지 배열을 같은 방법으로 교체한다
***
### Code
```
    public static void selectionSort(int[] arr) {
    int indexMin, temp; //최솟값의 위치
    for (int i = 0; i < arr.length-1; i++) {
        indexMin = i;//i번째 반복할 때 최소값의 위치를 i번째 인덱스로 설정
        for (int j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[indexMin]) {//j번 값이 i번째로 설정한 최솟값보다 작다면 index를 j로 변경
                indexMin = j;
            }
        }
        //j번 반복이 완료되면 설정된 최솟값을 앞으로 이동
        temp = arr[indexMin];
        arr[indexMin] = arr[i];
        arr[i] = temp;
    }
        System.out.println(Arrays.toString(arr));
    }
```

시간복잡도: O(n^2)