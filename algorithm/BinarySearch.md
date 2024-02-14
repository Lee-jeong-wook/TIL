# Binary Search(이분 탐색)
### What?
N개의 수가 정렬되어 있을 때 특정 K가 어디에 위치하는지 찾아내는 것
### How?
중간을 나누고 mid값과 찾는 값을 비교한 다음 작은지 혹은 큰지 비교 후 절반을 날림
시간복잡도 O(log n)
###  Code
```
int binarySearch1(int key, int low, int high) {
	int mid;

	if(low <= high) {
		mid = (low + high) / 2;

		if(key == arr[mid]) { // 탐색 성공 
			return mid;
		} else if(key < arr[mid]) {
			// 왼쪽 부분 arr[0]부터 arr[mid-1]에서의 탐색 
			return binarySearch1(key ,low, mid-1);  
		} else {
			// 오른쪽 부분 - arr[mid+1]부터 arr[high]에서의 탐색 
			return binarySearch1(key, mid+1, high); 
		}
	}

	return -1; // 탐색 실패 
}
```