## Processing large JSON files in Python without running out of memory

[https://pythonspeed.com/articles/json-memory-streaming/](https://pythonspeed.com/articles/json-memory-streaming/)

- 큰 JSON 파일을 파이썬에서 다룰 때 용량이 모자라기 쉬움.
- raw data가 메모리에 적절하다고 하더라도, python representation이 용량을 증가시킬 가능성이 존재
- 디스크로 스왑될 때 속도가 느려지거나 메모리에서 충돌이 발생할 수 있음.

## 해결방법 : treaming parsing, aka lazy parsing, iterative parsing, or chunked processing

문제 : 파이썬의 비효율적인 로딩

- 파이썬 내의 내장된 json 모듈은 json.load() 가 파일 전체를 파싱 전에 메모리에 로딩한다
    - 이것이 문제가 됨 => 메모리를 많이 차지해서
    - 파일 로드 이후 바이트에서 유니코드로 디코딩하는 과정에서 메모리를 가장 많이 사용
        - 따라서 프로파일링 하는 것이 메모리 사용량을 줄이고 속도를 높이는 것에 기여
- 파이썬의 문자열 메모리 표현
    - 적은 메모리를 쓰는 것에 최적화 되어 있음

##### 추후 업데이트.. . . . . .
