
## 필요 라이브러리

* Protobuf
* Tensorflow
* Opencv

## 실행 전 설정 (tensorflow/models를 설치하지 않았을 경우만)
1. 환경 변수의 시스템 변수에 **PYTHONPATH** 추가
2. **PYTHONPATH**의 값에 **hands_detection**이 위치한 디렉터리 2개 추가
    - 예시
    ```buildoutcfg
    C:\workspace\hands_detection
    C:\workspace 
    ```
3. `utils/label_map_util.py`에서 line 26을 다음과 같이 수정
    - 수정 전 : from object_detection.protos import string_int_label_map_pb2
    - 수정 후 : from hands_detection.protos import string_int_label_map_pb2

## 이미지 데이터 생성 방법

1. `detect_webcam.py` 실행
2. 단축키 **c**를 누르면 같은 디렉터리에 사진파일이 생김
3. 손이 초록색 박스안에 다 들어오지 않았을 때 잘려서 저장이 되니 알아서 잘 캡쳐하셈

## 해상도 변경 방법

#### 프롬프트에서 실행 시
```buildoutcfg
# From hands_detection/
python detect_webcam.py \
    --width=${WIDTH_VALUE} \
    --height=${HEIGHT_VALUE}
```

#### 파이참에서 실행 시
##### 1. width
```buildoutcfg
parser.add_argument(
        '-wd',
        '--width',
        dest='width',
        type=int,
        default=640,
        help='Width of the frames in the video stream.')
```
- `default` 값을 수정
##### 2. height
```buildoutcfg
parser.add_argument(
        '-ht',
        '--height',
        dest='height',
        type=int,
        default=480,
        help='Height of the frames in the video stream.')
```
- `default` 값을 수정
