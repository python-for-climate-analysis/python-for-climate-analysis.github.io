---
permalink: /gettingStart/
title: "데스크탑 Linux 가상환경"
excerpt: "Minimal Mistakes is a flexible two-column Jekyll theme."
layouts_gallery:
  - url: /assets/images/mm-layout-splash.png
    image_path: /assets/images/mm-layout-splash.png
    alt: "splash layout example"
  - url: /assets/images/mm-layout-single-meta.png
    image_path: /assets/images/mm-layout-single-meta.png
    alt: "single layout with comments and related posts"
  - url: /assets/images/mm-layout-archive.png
    image_path: /assets/images/mm-layout-archive.png
    alt: "archive layout example"
last_modified_at: 2022-05-27T11:59:26-04:00
toc: true
---

# 데스크탑 Linux 가상환경

# 1. 우분투 설치

다운받으세욤

## 1-1. 우분투 실행하기 전에

### Windows 기능 켜기/끄기 의 Linux용 Windows 하위 시스템 체크

설정에서 'windows 기능 켜기/끄기' 을 검색 후 클릭 → 'Linux용 Windows 하위시스템'을 찾아서 체크

![img](/assets/fig_gettingStart_1.png)

### 개발자용 기능 사용 체크

![img](/assets/fig_gettingStart_2.png)

# 2. 새로운 가상환경 만들기

```powershell
$ conda create -n 환경이름 python=파이썬버전
```

## 1-1. Ubuntu에서 Anaconda3/Miniconda3 설치

Anaconda/miniconda 홈페이지에서 리눅스용 최신버전 다운로드 링크 복사

우분투 열고 wget

```powershell
$ wget [Miniconda 다운로드 링크]
$ bash [Miniconda 설치파일.sh]
라이선스동의 [yes]하고 설치[enter] 마지막에 conda init할거냐고 물어보면 [yes]

$ source ~/.bashrc
```

## 1-2. Ubuntu에서 Anaconda3/Miniconda3 삭제

홈에 있는 anaconda/miniconda 폴더를 rm -rf

~/.bashrc 파일에 anaconda/miniconda source 정보 삭제

## 2-1. 새로운 가상환경 만들기&삭제하기

```powershell
$ conda create -n [환경이름] python=3.8
$ conda remove -n [환경이름] --all
```

## 2-2. < .yml >파일로 가상환경 만들기 (실패함)

```jsx
anaconda가 설치된 경로에 environment.yml 파일을 저장

$ conda env create -n ml --file environment.yml
```

## 3. 환경설정확인

```jsx
$ conda info --envs
```

## 4. 가상환경 활성화&비활성화

```jsx
$ conda activate 환경이름
$ conda deactivate
```

## 5. 필요한 모듈 설치하기

```bash
conda upgrade conda
sudo apt-get update
sudo apt-get upgrade
sudo apt install build-essential
conda update conda
conda create -n jupyter python
conda install -y -c conda-forge jupyter jypyterlab xarray pandas numpy scipy seaborn matplotlib -c ncar geocat-comp geocat-viz geocat-datafiles bokeh

conda install -c conda-forge dateutil

```

## 6. 모듈 업데이트

```bash
conda update conda 
```

#
