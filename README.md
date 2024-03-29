# 파이썬 코딩 테스트 팁 모음
## 유용한 사이트
- https://pythontutor.com/ 어떻게 동작하는지 시각적으로 확인할 수 있음
## Basic
### `defaultdict`
`defaultdict`는 `dict`와 거의 유사하지만 `KeyError`를 발생시키지 않습니다. Key가 없는 경우 default 값을 제공하기 때문입니다. 아래와 같이 default가 `list`가 되도록 하면 코드를 간소화할 수 있습니다.
#### AS-IS
```python
categorized_music = {}
music_album = [['music1', 'jazz'], ['music2', 'classic'], ['music3', 'jazz']]

for music in music_album:
  if music[1] not in categorized_music:
    categorized_music[music[1]] = [music[0]]
  else:
    categorized_music[music[1]].append(music[0])
```
#### TO-BE
```python
from collections import defaultdict

categorized_music = defaultdict(list)
music_album = [['music1', 'jazz'], ['music2', 'classic'], ['music3', 'jazz']]

for music in music_album:
  categorized_music[music[1]].append(music[0])
```

### `map`
`map(fun, iter)`은 주어진 `iter`의 각 개체에 `fun`을 적용하여 `map` 오브젝트를 반환합니다.
특히 초기 입력을 적절한 타입의 변수들로 바꾸는데 유용합니다.

#### Example
```
time = "12:00:00"
hh, mm, ss = map(int, time.split(":"))
```

### `2D array initialize`
2D array를 만들어야 하는 경우 아래와 같은 코드로 만들 수 있습니다.
```
n = 5
map = [[0] * n for i in range(n)]
```

### 리스트 중 가장 짧은 단어의 길이 구하기
```
shortest = min(strs,key=len)
```
