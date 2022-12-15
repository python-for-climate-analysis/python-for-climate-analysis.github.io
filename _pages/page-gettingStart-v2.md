---
layout: single
permalink: /gettingStart/
title: "Linux 가상환경 만들기"
excerpt: "PC/Laptop WINDOWS에서 Ubuntu를 이용한 Linux 가상환경 만들기"
last_modified_at: 2022-11-27T11:59:26-04:00
toc: true
---

# 데스크탑 Linux 가상환경

# 1. 우분투 설치

## 1-1. 시작하기 전에

### Windows 기능 켜기/끄기 의 Linux용 Windows 하위 시스템 체크

설정에서 'windows 기능 켜기/끄기' 을 검색 후 클릭 → 'Linux용 Windows 하위시스템'을 찾아서 체크

![Untitled](%E1%84%83%E1%85%A6%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%90%E1%85%A1%E1%86%B8%20Linux%20%E1%84%80%E1%85%A1%E1%84%89%E1%85%A1%E1%86%BC%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%204246c7dca3c34530b39d46b866d1b90b/Untitled.png)

### 개발자용 기능 사용 체크

![Untitled](%E1%84%83%E1%85%A6%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%90%E1%85%A1%E1%86%B8%20Linux%20%E1%84%80%E1%85%A1%E1%84%89%E1%85%A1%E1%86%BC%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%204246c7dca3c34530b39d46b866d1b90b/Untitled%201.png)

## 1-2. 우분투 설치하기

MS store에서 다운받아 설치하세용

# 2. 새로운 가상환경 만들기

```powershell
$ conda create -n 환경이름 python=파이썬버전
```

## 2-1. Ubuntu에서 Anaconda 설치

1. Anaconda  홈페이지에서 리눅스용 최신버전 다운로드 링크 복사
2. 우분투 열고 wget

```powershell
$ wget [Anaconda 다운로드 링크]
$ bash [Anaconda 설치파일.sh]
라이선스동의 [yes]하고 설치[enter] 마지막에 conda init할거냐고 물어보면 [yes]

$ source ~/.bashrc
```

![MobaXterm 도 편하고 좋습니다 😀](%E1%84%83%E1%85%A6%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%90%E1%85%A1%E1%86%B8%20Linux%20%E1%84%80%E1%85%A1%E1%84%89%E1%85%A1%E1%86%BC%E1%84%92%E1%85%AA%E1%86%AB%E1%84%80%E1%85%A7%E1%86%BC%204246c7dca3c34530b39d46b866d1b90b/Untitled%202.png)

MobaXterm 도 편하고 좋습니다 😀

## 2-2. 새로운 가상환경 만들기&삭제하기

```powershell
$ conda create -n [환경이름] python=3.8
$ conda remove -n [환경이름] --all
```

## 2-3. < .yml >파일로 가상환경 만들기 (나는 실패함)

```jsx
anaconda가 설치된 경로에 environment.yml 파일을 저장

$ conda env create -n ml --file environment.yml
```

## 2-4. 환경설정확인

```jsx
$ conda info --envs
```

## 2-5. 가상환경 활성화&비활성화

```jsx
$ conda activate 환경이름
$ conda deactivate
```

## 2-6. 필요한 모듈 설치하기 및 업데이트

```bash
$ conda upgrade conda

#sudo apt-get update
#sudo apt-get upgrade
#sudo apt install build-essential

$ conda update conda
# 여기까지 했는데 앵간한건 다 설치가 되버렸더라고...? pandas xarray scipy 등등 
# 그래서 아래 install은 추가 모듈만 설치해도 됐음 

conda install -y -c conda-forge jupyter jypyterlab netCDF4 xarray pandas numpy scipy seaborn matplotlib -c ncar geocat-comp geocat-viz geocat-datafiles bokeh
conda install -c conda-forge dateutil

```

## 2-7. 가상환경 완전 삭제

1. 홈에 있는 anaconda/miniconda 폴더를 rm -rf
2. ~/.bashrc 파일에 anaconda/miniconda source 정보 삭제
