# 백준 문제 풀이

### 6번 마라탕후루
```
n,p,q = map(int,input().split())
a = list(map(int,input().split()))
b = list(map(int,input().split()))
result = []
check = 0
for i in range(n):
    num = 0
    for j in range(10000):
        if a[i] == b[i]:
            check += 1 
            break
        a[i] += p
        b[i] += q
        num += 1
    result.append(num)

if check == n:
    print("YES")
    print(*result)
else: print("NO")
```
딸기 개수는 a리스트에, 샤인머스캣 개수는 b리스트에 입력받는다. 그리고 a[i]에 딸기 추가 개수 p를 더하고 b[i]에도 q를 더하는 것을 a[i]의 수와 b[i]의 수가 같을때까지 최대 10000번 반복한다. 모든 탕후루의 딸기와 샤인머스캣의 개수가 똑같아질수 있는지 알기 위해 check를 이용하여 

### 7번 밤양갱
```
n = int(input())
a,count = 1,1
while a < n+1:
    a += a
    count += 1
print(8+count)
```
daldidalgo의 횟수 n을 입력받고 daldidalgo의 개수를 두배씩 증가시켜서 그 값이 n+1보다 크거나 같을때까지 계속 반복한다. 마지막에 daldidan에 daldida또한 복사받아야 하므로 n에 1을 더한것이다. 그리고 두배를 할 때마다 count에 1씩 증가시켜 시간을 잰다. 맨 처음의 daldidalg와 마지막 n을 쓰기위한 시간 8초와 이외의 것들을 쓰기위한 시간 count를 더하여 출력한다.
