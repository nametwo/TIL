# TIL

내가 공부한거 올릴거임

### 2021.07.06  

#1032 백준에서 출력시 공백도 출력하면 오류남

### 2021.07.07

#1011 굳이 모든 케이스 받고 한꺼번에 출력할 필요 없이 하나 받고 하나 출력하고 다음꺼 입력받고 출력하고 해도 상관 없다!


### 2021.07.11

#2178 c에서 scanf()는 놀랍게도 \n도 받는다.
c에서 <string.h>의 strcat에 문자열을 넣을때는 'c'가 아니라 "c" 이렇게 넣어야한다. 당연히 문자상수와 문자열은 다르기 때문이다

### 2021.07.23

#4673 도저히 이해 못하겠다.

#include <stdio.h>

	int result[10036] = { 0, };

	for (int i = 1; i <= 10000; i++) {
  
		a = selfnum(i);
    
		result[a] = 1;
    
	}


	for (int i = 1; i <= 10000; i++) {
  
		if (result[i] == 0) {
    
			printf("%d\n", i);
      
		}
    
	}
  
 대충 요약하면 이런 상황이다. 배열의 크기를 10036 이상으로 잡으면 OutOfBounds 오류가 안나고 10035이하면 오류가 난다.
 
 분명 for문에서는 10000까지만 접근하는데.

### 2021.08.14

#1316 뭘 틀린거지?

int main(void) {

	int alphabet = 0;
	int num, result = 0, b;
	int a[26] = { 0, };

	char word[101] = { "" };

	scanf("%d", &num);

	for (int i = 0; i < num; i++) {
		scanf("%s", word);

		

		for (int k = 0; k < strlen(word); k++) 
		{
			if (alphabet == word[k])
			{
			
			}
			else 
			{
				alphabet = word[k];
				a[alphabet - 97] += 1;
			}
		}

		for (int k = 0; k < 26; k++) {
			if (a[k] >= 2) {
				result++;
				break;
			}
		}

		for (int k = 0; k < 26; k++) {
			a[k] = 0;
		}
	}
	
	printf("%d", num - result);
}

