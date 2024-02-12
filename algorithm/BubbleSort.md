# 버블정렬(BubbleSort)
서로 인접한 두 요소를 비교한 다음 조건에 맞지 않는다면 교환하는 정렬 알고리즘
***
### Process
> 1. 주어진 배열을 도는 중에 인접한 옆 요소와 비교를 한다
> 2. 특정 조건을 만족한다면 교환한다.
***
### Code
```
    public static int[] bubbleSort(int[] input){
        int tmp;
        for(int i = 0; i < input.length; i++){
            for(int j = 1; j < input.length - i; j++){
    			if(input[j-1] > input[j]) {
    				tmp = input[j-1];
    				input[j-1] = input[j];
    				input[j] = tmp;
			}
            }
        }
        
        return input;
    }
```
시간복잡도: O(n^2)
가장 기초적이지만 가장 비효율적인 알고리즘
