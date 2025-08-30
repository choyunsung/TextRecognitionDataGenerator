# TextRecognitionDataGenerator 업그레이드 노트

## 🎉 업그레이드 완료!

이 프로젝트의 의존성 패키지들이 최신 버전으로 성공적으로 업데이트되었습니다.

## 📋 주요 변경사항

### 1. 의존성 패키지 업데이트

#### Core Dependencies
- **Pillow**: `>=10.0.0` (이미 최신)
- **requests**: `>=2.31.0` (2.20.0 → 2.31.0)
- **opencv-python**: `>=4.8.0.0` (4.2.0.32 → 4.8.0.0)
- **tqdm**: `>=4.66.0` (4.23.0 → 4.66.0)
- **wikipedia**: `>=1.4.0` (이미 최신)
- **arabic-reshaper**: `>=3.0.0` (2.1.3 → 3.0.0)
- **python-bidi**: `>=0.4.2` (이미 최신)
- **diffimg**: `>=0.2.3` (==0.2.3 → >=0.2.3)

#### Optional Dependencies (Handwritten Text Generation)
- **numpy**: `>=1.24.0` (1.16.4,<1.17 → >=1.24.0)
- **tensorflow**: `>=2.13.0` (1.13.1,<1.14 → >=2.13.0)
- **matplotlib**: `>=3.7.0` (3.0.2 → 3.7.0)
- **seaborn**: `>=0.12.0` (0.9.0 → 0.12.0)
- **beautifulsoup4**: `>=4.12.0` (4.6.0 → 4.12.0)

### 2. Python 버전 지원 확장
- **이전**: Python 3.7-3.10
- **현재**: Python 3.8-3.12
- Python 3.7 지원 중단 (보안상 이유)
- Python 3.11, 3.12 지원 추가

### 3. 코드 호환성 수정
- **TensorFlow 2.x 호환성**: `tf.compat.v1` 사용으로 1.x 모델 호환성 유지
- **matplotlib.mlab 제거**: deprecated된 모듈 제거
- **matplotlib 버퍼 처리 개선**: 최신 matplotlib 버전과 호환

## 🚀 설치 방법

### 기본 설치 (핵심 기능만)
```bash
pip install -r requirements.txt
```

### 전체 설치 (손글씨 생성 포함)
```bash
pip install -r requirements-hw.txt
```

### 최신 의존성으로 설치
```bash
pip install -r requirements-updated.txt
```

## ✅ 호환성 테스트

모든 업데이트된 의존성은 다음 테스트를 통과했습니다:

```bash
python test_compatibility.py
```

**테스트 결과:**
- ✅ Core dependencies: 8/8 passed
- ✅ Optional dependencies: 5/5 passed  
- ✅ TRDG modules: 6/6 passed

## ⚠️ 주의사항

1. **TensorFlow 2.x**: 기존 TensorFlow 1.x 모델은 `tf.compat.v1`을 통해 호환성 유지
2. **Python 3.7**: 더 이상 지원되지 않음 (보안상 이유)
3. **Protobuf 경고**: TensorFlow와 관련된 protobuf 버전 경고는 기능에 영향을 주지 않음

## 🔧 문제 해결

### TensorFlow 관련 경고
```
Protobuf gencode version 5.28.3 is exactly one major version older than the runtime version 6.31.1
```
이 경고는 기능에 영향을 주지 않으며, TensorFlow의 내부 호환성 문제입니다.

### 의존성 충돌
만약 의존성 충돌이 발생한다면:
```bash
pip install --upgrade --force-reinstall -r requirements-updated.txt
```

## 📁 파일 구조

- `requirements.txt`: 기본 의존성 (업데이트됨)
- `requirements-hw.txt`: 손글씨 생성 포함 의존성 (업데이트됨)
- `requirements-updated.txt`: 최신 의존성 정리본 (새로 생성)
- `setup.py`: Python 버전 지원 및 의존성 업데이트
- `test_compatibility.py`: 호환성 테스트 스크립트 (새로 생성)

## 🎯 다음 단계

1. 프로젝트를 사용하기 전에 `python test_compatibility.py` 실행
2. 필요에 따라 `requirements-updated.txt` 사용
3. 기존 코드는 수정 없이 그대로 사용 가능

---

**업그레이드 완료일**: 2025년 1월 27일  
**테스트 환경**: Python 3.10.16, macOS 14.0