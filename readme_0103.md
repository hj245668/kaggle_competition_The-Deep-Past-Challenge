# Kaggle Competition – The Deep Past Challenge

Akkadian → English Machine Translation

## Repository 목적

이 레포지토리는 Kaggle 대회
**Deep Past Challenge – Translate Akkadian to English**
참가를 위한 코드와 기록을 관리하기 위한 곳이다.

작업은 다음과 같이 분리해 진행한다.

* Kaggle Notebook: 모델 학습, 제출 파일 생성
* GitHub Repository: 코드/노트북/결과/기록 관리

즉, 실행은 Kaggle에서 하고
버전 관리와 문서화는 GitHub에서 수행한다.

---

## 현재 상태

* competition 참가 및 규칙 동의 완료(Persona등록완료!)
* 데이터 구조 파악 완료
* GitHub repo 생성 완료
* 베이스라인 구축 준비 완료
* 다음 단계: Kaggle Notebook 베이스라인 실행

---

## 폴더 구조 계획

```
kaggle_competition_The-Deep-Past-Challenge/
│
├── README.md
├── notebooks/
│   ├── 01_explore.ipynb
│   ├── 02_train_mt5.ipynb
│   ├── 03_inference_submission.ipynb
│
├── submissions/
│   ├── baseline_dummy.csv
│   ├── mt5_v1.csv
│
├── src/
│   ├── dataset_utils.py
│   ├── training.py
│   └── inference.py
│
└── experiments.md
```

처음에는 notebooks와 README만 있어도 충분하며
필요해지면 src/로 리팩토링한다.

---

## 대회 개요

목표
Akkadian Old Assyrian cuneiform transliteration을
**영어로 번역하는 모델을 구축**하는 것.

핵심 파일

* train.csv
  transliteration + translation 제공

* test.csv
  transliteration만 존재, 번역 예측해야 함

* sample_submission.csv
  제출 형식 예시

주의
이 대회는 **Code Competition**이므로
채점 서버에서 재현 가능해야 한다.

---

## 진행 단계 체크리스트

### 1단계 – 준비

* Kaggle join & 규칙 동의
* GitHub repo 생성
* README 작성(현재 단계 완료)
* 더미 제출 1회로 파이프라인 확인

### 2단계 – 베이스라인

* mT5-small fine-tuning
* 기본 토크나이저 사용
* 간단한 validation split
* 첫 정상적인 모델 제출

### 3단계 – 개선

* 전처리 규칙 추가
* SentencePiece 학습
* 하이퍼파라미터 튜닝
* beam search / sampling 조정

### 4단계 – 고급 전략

* 추가 데이터 생성(publications.csv)
* 사전 데이터 활용(OA_Lexicon 등)
* pseudo-labeling
* 앙상블 / reranking

---

## 제출 전략

* 하루 제출 제한 확인
* 서로 다른 유형의 모델 2–3개 유지
* validation 점수와 LB 점수를 모두 참고
* 마지막 날 과도한 실험 지양하고 안정적 모델 제출

---

## 작업 방식

* 코드 작성: Kaggle Notebook
* 모델 학습: Kaggle GPU
* 기록 및 버전 관리: GitHub
* 최종 제출 파일: submissions 폴더에 저장 후 업로드

---

## 메모

* 처음 점수 낮아도 문제 없음
* 이 대회는 전처리와 토크나이저가 매우 중요
* 꾸준한 기록 관리가 가장 큰 무기

—————————————

이제 바로 할 것 두 가지만 정리해 줄게요.

1. GitHub README에 위 내용 붙여넣기
2. Kaggle에서 새 Notebook 만들기

Notebook 만들면

* 데이터 불러오기
* train.head() 출력
* 더미 제출 생성

여기까지만 해보고 화면 보여주면
바로 mT5 학습 코드까지 같이 이어가자.
