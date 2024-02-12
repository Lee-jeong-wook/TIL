# 퀵 정렬(Quick Sort)
분할정복(문제를 작은 문제 2개로 분리하고 해결한 다음 결과를 모아 원래의 문제 해결)
***
### Process
> 1. 배열 가운데서 하나의 원소를 고른다(피벗)
> 2. 그 원소를 기준으로 작은 것은 왼쪽, 큰 것은 오른쪽으로 보낸다
> 3. 재귀적으로 반복
***
### Code
```
public void quickSort(int[] array, int left, int right) {
    if(left >= right) return;
    
    // 분할 
    int pivot = partition(array, left, right); 
    
    // 피벗은 제외한 2개의 부분 배열을 대상으로 순환 호출
    quickSort(array, left, pivot-1);  // 정복(Conquer)
    quickSort(array, pivot+1, right); // 정복(Conquer)
}
public int partition(int[] array, int left, int right) {
    
    int pivot = array[left]; // 가장 왼쪽값을 피벗으로 설정
    int i = left, j = right;
    
    while(i < j) {
        while(pivot < array[j]) {
            j--;
        }
        while(i < j && pivot >= array[i]){
            i++;
        }
        swap(array, i, j);
    }
    array[left] = array[i];
    array[i] = pivot;
    
    return i;//pivot의 최종 위치 리턴
}
```