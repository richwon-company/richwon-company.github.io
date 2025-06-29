---
sidebar_position: 2
---

# LISP 문제 해결 가이드

AutoCAD LISP 사용 중 발생할 수 있는 문제들과 해결방법을 안내합니다.

## 🚨 자주 발생하는 문제

### 1. APPLOAD에서 파일을 찾을 수 없는 경우

#### 증상
- APPLOAD 창에서 LISP 파일을 찾을 수 없음
- "파일을 찾을 수 없습니다" 오류 메시지
- 시작하기 세트에 추가되지 않음

#### 원인
- 파일 경로가 잘못됨
- 파일명에 한글이나 특수 문자가 포함됨
- 파일이 손상됨
- 파일 확장자가 잘못됨

#### 해결방법

**1단계: 파일 위치 확인**
- LISP 파일이 `C:\Users\[사용자명]\Documents\AutoCAD\LISP\` 폴더에 있는지 확인
- 파일 탐색기에서 직접 확인

**2단계: 파일명 확인**
- 파일명에 한글이나 특수 문자가 없는지 확인
- 파일 확장자가 `.lsp`인지 확인
- 예: `nameplate-automation.lsp` ✅

**3단계: APPLOAD에서 다시 추가**
1. **APPLOAD 명령어 실행**
2. **'시작하기 세트' 탭 선택**
3. **'추가' 버튼 클릭**
4. **파일 탐색기에서 LISP 파일 선택**
5. **'열기' 버튼 클릭**

:::warning[주의사항]
파일명에는 한글이나 특수 문자를 사용하지 마세요.
영문, 숫자, 하이픈(-)만 사용하는 것이 안전합니다.
:::

### 2. 시작하기 세트에 추가했지만 로드되지 않는 경우

#### 증상
- APPLOAD에서 시작하기 세트에 추가했지만 AutoCAD 시작 시 로드되지 않음
- 명령어 창에 로드 메시지가 나타나지 않음
- LISP 명령어가 작동하지 않음

#### 원인
- AutoCAD 설정 문제
- LISP 파일 로드 옵션이 체크되지 않음
- 파일 경로 문제

#### 해결방법

**1단계: AutoCAD 설정 확인**
1. **도구** → **옵션** → **시스템** 탭
2. **'일반 옵션' 섹션에서**
3. **'LISP 파일 로드' 체크박스 확인**
4. **체크되어 있지 않으면 체크**
5. **'확인' 클릭**

**2단계: AutoCAD 재시작**
- AutoCAD를 완전히 종료
- 다시 실행
- 명령어 창에 로드 메시지 확인

**3단계: APPLOAD에서 설정 재확인**
1. **APPLOAD 명령어 실행**
2. **'시작하기 세트' 탭에서 파일 목록 확인**
3. **파일이 목록에 있는지 확인**

### 3. 명령어가 정의되지 않는 경우

#### 증상
- LISP 파일은 로드되지만 명령어가 작동하지 않음
- "명령어가 정의되지 않았습니다" 오류 메시지
- 명령어가 AutoCAD 기본 명령어와 충돌

#### 원인
- LISP 파일에 명령어 등록 코드가 없음
- 명령어명이 AutoCAD 기본 명령어와 중복
- LISP 파일에 오류가 있음

#### 해결방법

**1단계: 명령어명 확인**
- 정확한 명령어명을 입력했는지 확인
- AutoCAD 기본 명령어와 중복되지 않는지 확인

**2단계: LISP 파일 확인**
- LISP 파일이 정상적으로 작성되었는지 확인
- 담당자에게 LISP 파일 점검 요청

**3단계: 대체 방법**
- 명령어 창에 `(load "파일명.lsp")` 입력하여 수동 로드
- 담당자에게 문의

:::tip[명령어 확인 방법]
명령어 창에 `명령어명` 입력 후 Enter
정상 작동하면 해당 기능이 실행됩니다.
:::

### 4. AutoCAD가 느려지거나 멈추는 경우

#### 증상
- LISP 파일 로드 후 AutoCAD가 느려짐
- 프로그램이 멈추거나 오류 발생
- 메모리 부족 메시지

#### 원인
- LISP 파일이 너무 큼
- 메모리 부족
- LISP 파일에 오류가 있음

#### 해결방법

**1단계: 다른 프로그램 종료**
- 불필요한 프로그램 종료
- 브라우저 탭 정리
- 메모리 확보

**2단계: AutoCAD 재시작**
- AutoCAD 완전 종료
- 다시 실행
- LISP 파일 다시 로드

**3단계: 담당자 문의**
- 문제가 지속되면 담당자에게 문의
- LISP 파일 최적화 요청

## 🔧 고급 문제 해결

### 1. APPLOAD 창이 열리지 않는 경우

#### 증상
- `APPLOAD` 명령어를 입력해도 창이 열리지 않음
- "명령어를 찾을 수 없습니다" 메시지

#### 해결방법

**1단계: 명령어 확인**
- `APPLOAD` 명령어를 정확히 입력했는지 확인
- 대소문자 구분 없음

**2단계: 메뉴 사용**
- **도구** → **응용프로그램 로드/언로드** 메뉴 선택

**3단계: AutoCAD 재시작**
- AutoCAD 재시작 후 다시 시도

### 2. 시작하기 세트에서 파일이 사라지는 경우

#### 증상
- APPLOAD에서 추가한 파일이 목록에서 사라짐
- AutoCAD 재시작 후 자동 로드되지 않음

#### 해결방법

**1단계: 파일 경로 확인**
- LISP 파일이 원래 위치에 있는지 확인
- 파일이 삭제되거나 이동되지 않았는지 확인

**2단계: 다시 추가**
1. **APPLOAD 명령어 실행**
2. **'시작하기 세트' 탭 선택**
3. **'추가' 버튼 클릭**
4. **파일 다시 선택**

**3단계: 파일 백업**
- 중요한 LISP 파일은 백업 보관
- 안전한 위치에 복사본 저장

## 📋 문제 해결 체크리스트

### 기본 확인사항
- [ ] LISP 파일이 올바른 위치에 있는지 확인
- [ ] 파일명에 한글이나 특수 문자가 없는지 확인
- [ ] 파일 확장자가 `.lsp`인지 확인
- [ ] 파일이 손상되지 않았는지 확인

### APPLOAD 설정 확인사항
- [ ] APPLOAD 명령어가 정상 실행되는지 확인
- [ ] 시작하기 세트에 파일이 추가되었는지 확인
- [ ] 파일 목록에 표시되는지 확인
- [ ] 확인 버튼을 클릭했는지 확인

### AutoCAD 설정 확인사항
- [ ] LISP 파일 로드 옵션이 체크되어 있는지 확인
- [ ] AutoCAD가 정상적으로 재시작되었는지 확인
- [ ] 명령어 창에 로드 메시지가 나타나는지 확인
- [ ] LISP 명령어가 정상 작동하는지 확인

## 🆘 긴급 상황 대처

### AutoCAD가 완전히 멈춘 경우

:::danger[긴급 대처]
1. **프로그램 강제 종료**
   - Ctrl + Alt + Delete → 작업 관리자
   - AutoCAD 프로세스 종료

2. **시스템 재부팅**
   - 컴퓨터 재부팅
   - AutoCAD 재실행

3. **LISP 파일 임시 제거**
   - APPLOAD에서 LISP 파일 제거
   - AutoCAD 정상 작동 확인 후 다시 추가
:::

### 데이터 손실 방지

:::warning[데이터 보호]
- 작업 전 항상 도면 백업
- 정기적인 LISP 파일 백업
- 중요한 작업은 단계별로 저장
:::

## 📞 추가 지원

문제가 지속되거나 해결되지 않는 경우:

:::info[지원 연락처]
- 담당자에게 문의
- 오류 메시지 스크린샷 준비
- APPLOAD 창 스크린샷 준비
- 발생 상황 상세 설명
:::

## 🔄 업데이트 정보

### 최신 변경사항
- APPLOAD 방식으로 변경
- UI 기반 설정 방법
- 사용자 친화적 가이드

### 향후 계획
- 자동 진단 도구 개발
- 원격 지원 기능
- 실시간 모니터링 시스템 