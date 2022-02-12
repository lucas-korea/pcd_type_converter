# PCD type converter

[blog link](https://cjung.tistory.com/16)

## PCD란
pcd (=point cloud data) 파일은 특정한 포맷으로 정의되어 있으며,
크게 두가지 data type을 가지고 있다.

binary와 ascii 인데, 똑같은 point cloud data ,xyz 좌표 데이터를 가지고 있지만 incoding 하는 방식에 따라 나뉜다.

ascii type은 실제로 파일을 열었을 때 보기 편하지 호환되는 플랫폼이 좀 더 많으나 용량이 크다
binary type은 파일 내용을 알아보기 어렵지만 용량이 작다

## How to convert?

현재 파이썬으로 pcd 파일 data type을 바꿀 수 있는 패키지는 pypcd가 유일한데(내가 조사한 바에 의하면)

python2까지밖에 지원을 안한다. 어떻게든 포팅할 수 있는 방법이 있는지 모르겠지만 본인은 실패했고

pcd 다루는 프로젝트를 진행하다 보니, 비슷한 기능을 하는 프로그램이 어쩌다가 만들어져서, 그냥 프로젝트로 삼고 마무리 했다.

C++에는 pcl이라는 라이브러리가 있는데 이를 이용하면 좀 더 쉽게 바꿀 수 있을것으로 보이나
~~C계열 언어는 솔직히 최대한 피하고 싶은 마음이 크다~~


### 그 외

본 코드를 실행파일로 만들고 싶다면 **pyinstaller** 패키지를 사용하면 된다.

이에 대해 공부하기 싫다면

```
pyinstaller --onefile pcd_type_converting_program.py
```

이렇게 하면 dist라는 폴더 안에 실행파일 생긴다. 패키지 설치는


본 프로그램을 테스트하기 위한 pcd 샘플도 동봉한다

--> **sample_bin.pcd,
sample_ascii.pcd**

_같은 데이터 다른 타입_
이니까 이리저리 변환변환해보면서 성능을 확인해보면 되겠다

pcd 데이터 뷰어로는 **cloud compare**를 추천한다. bin, ascii 둘 다 호환된다


<p align="center">
	<img src="https://user-images.githubusercontent.com/57425658/153703612-7e2dfcd7-9390-4094-833c-be05ee12199c.gif"  width="700" height="370">
	<em>pcd-type-converter 사용 예시</em>
<p>

<p align="center">
	<img src="https://user-images.githubusercontent.com/57425658/153703616-132f1d63-806e-4341-91b7-2f4ec3ad9292.gif"  width="700" height="370">
	<em>cloud compare 사용 예시 및 결과 검증. 원본과 변환한 파일이 동일한 데이터를 보여줌을 알 수 있다.</em>
<p>



