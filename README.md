# 2024-DACON-Puzzel_Solver
[대학 대항전 : 퍼즐 이미지 AI 경진대회] 퍼즐 이미지 재구성 알고리즘 개발 4th solution

![image](https://github.com/DYDevelop/DACON-Competitions/assets/55197580/dfaea029-7aeb-469d-b5b5-3e80a9714329)

## 대회 주제
퍼즐 이미지 재구성 AI 모델 개발

## Member
| 이름       | 학년 | 전공          | 역할                          |
|--------------|-----|-----------------------|------------------------------------|
| 김동영    | 4    | 지능기전공학부 무인이동체공학전공 |  Jigsawformer 모델 수정, Data Augmentation, Model CSV Ensemble |

## 개발 환경
- Ryzen 5600x
- Ram 32GB
- RTX 3090 24GB
- Windows WSL
- Batch Size == 64 (with AMP)
- Python 3.8.18
- torch.__version__ == 2.1.2
- Cuda compilation tools, release 11.5

## 주요 설명
[대학-대항전_퍼즐-이미지-AI-경진대회.pdf 참조]
1. Optimizer 변경 + LR scheduler 추가
- 기존 Adam에서 AdamW와 CosineAnnealingLR 조합을 사용

2. 다양한 Data Augmentation 적용
- Random Photometric Distort 
- Random Erasing
- Random Vertical Flip
- Random Horizontal Flip
- Random Rotate 90, 180, 270
- Random Cutout (Before Shuffle)
- Test Time Augment (Flip)

3. 여러개의 Pred 값들 Voting Ensemble 진행

## 모델 성능 순위표
![image](https://github.com/DYDevelop/DACON-Competitions/assets/55197580/a1cfbb6c-4d91-4f74-b2a2-9122e6c3416a)


