# 파이썬 코딩 테스트 팁 모음
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
