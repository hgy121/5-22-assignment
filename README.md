# 백준 문제 풀이

### 1번 초콜릿 자르기
```
a,b = map(int,input().split())
if a>=b:
  n = a
  m = b
else:
  n = b
  m = a
print(m-1+(n-1)*m)
```
가로,세로 값을 입력받는다. 더 큰 열방향으로 자르는 것이 자르는 횟수를 최소화 할 수 있기 때문에 가로a와 세로b를 비교하여 작은 값에 1을 뺀 값과 큰 값에 1을 뺀 값에 작은 값을 곱한 값을 더한다.

### 2번 손가락 게임
```
a,b = map(int,input().split())

if a==b: print('=')
else:
  if a==0:
    if b==2: print('>')
    elif b==5: print('<')
    else:print('>')
  elif a==2:
    if b==0: print('<')
    elif b==5: print('>')
    else:print('>')
  elif a==5:
    if b==0: print('>')
    elif b==2: print('<')
    else:print('>')
  else:
    if b==1 or b==3 or b==4: print('=')
    else: print('<')
```
a가 가위,바위,보,이외의 것인 경우로 나누고 또다시 b의 경우를 나눠 그에 맞는 결과를 출력한다.

### 3번 2024년에는 혼자가 아니길
```
x,y = map(int,input().split())
if 2*x<y:
    print(-1)
else:
    print(int(2024*(x/2-y/4)))
```
x와 y를 이용하여 w를 구하면 x/2-y/4가 되고 불가능한 수치가 되려면 2*x<y 이므로 2*x<y일 경우 -1을, 아닌 경우 w에 2024를 곱하여 정수로 바꾸고 출력한다.

### 4번 과민성 대장 증후군
```
n,m = map(int, input().split())
t,d = 0,0
s = list(map(int,input().split()))
for i in range(n):
  t += s[i]
  if t<0: t=0
  if t>=m: d += 1
print(d)
```
스트레스 양의 변화들를 입력받고 총 스트레스 양에 계속 더하다가 0보다 작아지면 0으로 바꾸고 복통을 격게되는 스트레스 양보다 크거나 같으면 복통을 격게된 일 수에 1을 더해서 복통을 격게되는 일수를 구하고 출력한다.

### 5번 버블버블
```

```
오름차순 정렬 방식인 버블정렬을 이용하여 정렬한다. i번째와 i+1번째 수를 비교하여 큰 수를 뒤로가게 한다. 맨 끝에 가장 큰 수가 있게 되므로 끝에는 비교할 필요가 없다. 때문에 이 과정을 1번씩 줄여서 반복한다. 한번 수의 순서를 뒤집을수 있기 때문에 오름차순으로 만드는데 필요한 최소한의 횟수를 구하기 위해 맨 처음에 뒤집었을때와 안 뒤집었을때의 횟수를 비교하고 작은 수를 출력한다.

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
딸기 개수는 a리스트에, 샤인머스캣 개수는 b리스트에 입력받는다. 그리고 a[i]에 딸기 추가 개수 p를 더하고 b[i]에도 q를 더하는 것을 a[i]의 수와 b[i]의 수가 같을때까지 최대 10000번 반복한다. 반복할 때마다 추가한 횟수도 세준다.모든 탕후루의 딸기와 샤인머스캣의 개수가 똑같아질수 있는지 알기 위해 check를 이용하여 탕후루 개수 n과 같다면 yes와 추가한 횟수를 출력, 아니라면 no를 출력한다.

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
