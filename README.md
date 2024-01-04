# Hello, BaDang

**제주위성데이터를 활용한 장기방치차량 탐지 지능형 플랫폼**  
"Intelligent Platform for Long-Term Abandoned Vehicle Detection Utilizing Jeju Satellite Data"

<p align="left">
  <img src="https://img.shields.io/badge/Ensemble-Weighted%20boxes%20fusion-FEE500?style=flat-square"/>
  <img src="https://img.shields.io/badge/Baseline-MMRotate-FEE500?style=flat-square"/>
  <img src="https://img.shields.io/badge/Baseline-YOLOv8-FEE500?style=flat-square"/>
  <br/>
  <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white"/>
  <img src="https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white"/>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Amazon%20AWS-FF9900?style=flat-square&logo=amazonaws&logoColor=white"/>
</p>

<br/>


***아래에서 프로토타입을 확인해보세요.***

<p align="left">
  <a href='https://desirable-sea.vercel.app/' target="_blank">
    <img src="https://img.shields.io/badge/Deployment-Vercel-000000?style=flat-square"/>
  </a>
  <a href='' target="_blank">
    <img src="https://img.shields.io/badge/Modeling-goorm-ffffff?style=flat-square"/>
  </a>
</p>


<br/>

# 1. 프로젝트 개요
본 아이디어는, 제주 위성데이터를 활용하고 컴퓨터 비전의 객체 인식 AI 기술을 적용하여, 제주 지역에서 장기적으로 주차되거나 방치되어 있는 차량을 탐지하고, 해당 정보를 유관 기관이 통합하여 관리할 수 있는 지능형 플랫폼을 연구 및 개발하는 것입니다. 이를 통해 장기 방치 차량의 전수조사에 소요되는 인력과 시간을 절약하고 제주 미래항공우주산업 육성을 위한 첫걸음이 되기를 기대합니다.


<table>
  <tr>
    <td>
      <p align='center'>딥러닝 모델링</p>
    </td>
    <td>
      <p align='center'>
        사용자 UX
      </p>
    </td>
  </tr>
   <tr>
    <td>
      <img src="./src/model-performance.png" width=500 height=250/>
    </td>
    <td>
      <img src="./src/user-ux.png" width=500 height=250/>
    </td>
  </tr>
</table>

<br/>

# 2. 프로젝트 설계

### 2.1 객체 인식 모델링

# 3. 프로젝트 설치방법

### 2.1 객체 인식 모델링

디렉토리 구조
```
desirable-sea
├── checkpoints
├── mmrotate
│   ├── config
│   ├── ...
│   └── demo
├── ...
├── demo.png
└── result.jpg
```

설치방법

setup.sh
this code is written in Linux.

```shell
sudo apt update
sudo apt -y install libgl1-mesa-glx

wget https://repo.anaconda.com/miniconda/Miniconda3-py37_4.9.2-Linux-x86_64.sh
chmod +x Miniconda3-py37_4.9.2-Linux-x86_64.sh
bash ./Miniconda3-py37_4.9.2-Linux-x86_64.sh -b -f -p /usr/local
which conda
conda --version

pip install torch==1.7.0+cu110 torchvision==0.8.1+cu110 torchaudio==0.7.0 -f https://download.pytorch.org/whl/torch_stable.html
pip install openmim --use-feature=2020-resolver
mim install mmcv-full==1.5.3
mim install mmdet==2.25.1

git clone https://github.com/open-mmlab/mmrotate.git
cd mmrotate
pip install -r requirements/build.txt
pip install -v -e .

cd ..


mkdir checkpoints
cd checkpoints
wget https://download.openmmlab.com/mmrotate/v0.1.0/rotated_retinanet/rotated_retinanet_obb_r50_fpn_1x_dota_ms_rr_le90/rotated_retinanet_obb_r50_fpn_1x_dota_ms_rr_le90-1da1ec9c.pth
cd ..

wget https://raw.githubusercontent.com/ziweek/desirable-sea/main/src/demo.png

```

<br/>

inference.sh
this code is written in Linux.

추론 시작
```shell
python mmrotate/demo/image_demo.py demo.png mmrotate/configs/rotated_retinanet/rotated_retinanet_obb_r50_fpn_1x_dota_ms_rr_le90.py checkpoints/rotated_retinanet_obb_r50_fpn_1x_dota_ms_rr_le90-1da1ec9c.pth --out-file result.jpg
```

<br/>

### 2.2 웹페이지 대쉬보드 구현


<br/>

# Contribute


<table>
  <tr>
    <td>
      <p align='center'>김지욱</p>
    </td>
    <td>
      <p align='center'>부선웅</p>
    </td>
  </tr>
   <tr>
    <td>
      <img src="https://drive.google.com/uc?export=view&id=1459-NPm4sC50nrQRdjTpmpz_eKunIi04" width=210 height=280/>
    </td>
    <td>
      <img src="https://drive.google.com/uc?export=view&id=1RXq9nhJ5xsv_tMCUZ4l6QwDeiyR1mtSD" width=210 height=280/>
    </td>
  </tr>
  <tr>
    <td>
      <p align='center'>
        <a href='' target="_blank">
          <img src="https://img.shields.io/badge/Github-000000?style=flat-square&logo=Github&logoColor=white"/>
        </a>
      </p>
    </td>
    <td>
      <p align='center'>
        <a href='' target="_blank">
          <img src="https://img.shields.io/badge/Github-000000?style=flat-square&logo=Github&logoColor=white"/>
        </a>
      </p>
    </td>
  </tr>
</table>







