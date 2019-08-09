
## 필요 라이브러리

* Protobuf
* Tensorflow
* Opencv

## 이미지 데이터 생성 방법

1. `detect_webcam.py` 실행
2. 단축키 **'c'** 를 누르면 같은 디렉터리에 사진파일이 생김
3. 손 모양이 잘 안잡힐 수 있는데, 알아서 잘 캡쳐하셈

## 해상도 변경 방법
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