---
dependencies: []
disable_edit: true
kind: 도움말
title: 읽기 가능한 클래스 이름 정하기
---
## 메타데이터
**ID:** `python-best-practices/ambiguous-class-name`

**언어:** 파이썬(Python)

**심각도:** 알림

**범주:** 모범 사례

## 설명
일부 글꼴에서 일부 문자가 숫자 1과 0과 구분되지 않는 경우가 있습니다. 예를 들어 O는 영(0)처럼 보이기도 합니다. 분명한 문자를 사용하세요.

## 비준수 코드 예
```python
class I:  # use i instead
    pass
```

## 준수 코드 예
```python
class MyClass:
    pass
```