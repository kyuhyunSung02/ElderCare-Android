# ElderCare-Android
> 치매 환자를 위한 실시간 응급 대응 앱  
> Android 클라이언트 팀 (24.12 ~ 25.01)  

<img width="266" height="284" alt="image" src="https://github.com/user-attachments/assets/547b0d1e-f344-40ba-82a3-406412605a86" />

## 📖 프로젝트 소개
ElderCare는 치매 환자를 위한 **실시간 응급 대응** 및 **복용 알람/건강 관리 기능**을 제공하는 모바일 애플리케이션입니다.  
본 프로젝트는 Android 클라이언트 개발을 목표로 진행되었으며, Clean Architecture 기반의 구조 설계와 다양한 Jetpack 기술 적용을 통해 확장성과 유지보수성을 고려했습니다.  
※ 현재 프로젝트는 초기 기능 구현 단계까지만 진행되었습니다.

## 🍨 *****Contributors*****

| 김성민 <br> [@1971123-seongmin](https://github.com/1971123-seongmin) | 허성현 <br> [@hyeonhh](https://github.com/hyeonhh) | 성규현 <br> [@KyuHyeon Sung](https://github.com/kyuhyunSung02) <br> [@dmp100](https://github.com/dmp100) | 조정범 <br> [@BeomBeom2](https://github.com/BeomBeom2) |
|:---:|:---:|:---:|:---:|
| <img height="150" src="https://github.com/user-attachments/assets/fca542a2-5d32-40f3-aea1-99bb81424a10"/> | <img height="150" src="https://github.com/user-attachments/assets/06a7d15f-000b-436c-b655-62333d48166c"/> | <img height="150" src="https://github.com/user-attachments/assets/0a18a502-fdc0-4a67-be76-04815066f668"/> | <img height="150" src="https://github.com/user-attachments/assets/01261fa2-9cfd-43af-9a6a-6520ed01b4a8"/> |
| 기기 정보 등록 및 관리 | 메인 홈 / 복용 알람 추가/삭제, 활동 탭 | 건강정보 등록 / 설정 / 스플래시 및 소셜 로그인 | 복용 알람 수정 / 기본 정보 등록 |




## 📗 *****Convention*****
[📕 Git Convention & Branch Strategy]()
<br>
[📘 Android Coding Convention]()
<br>
[📒 Package Convention]()

<br/>

## 🔧 *****TECH STACKS*****
| **Category** | **TechStack** |
| --- | --- |
| Language | Kotlin |
| Architecture | Clean Architecture, MVVM |
| DI | Hilt |
| Network | Retrofit |
| Asynchronous | Coroutines, Flow |
| Jetpack | ViewBinding, Navigation, DataStore |
| Image | Glide, Coil |

<br/>

## 📁 *****Foldering*****

```
📂 org.sopt.linkareer
┣ 📂 core
┃ ┣ 📂 designsystem
┃ ┣ 📂 state
┃ ┣ 📂 navigation
┣ 📂 data
┃ ┣ 📂 datasource
┃ ┣ 📂 datasourceimpl
┃ ┣ 📂 model
┃ ┃ ┣ 📂 request
┃ ┃ ┣ 📂 response
┃ ┣ 📂 repositoryimpl
┃ ┣ 📂 service
┣ 📂 domain
┃ ┣ 📂 model
┃ ┣ 📂 repository
┣ 📂 presentation
┃ ┣ 기능 별 패키징

```

## ✨ 구현된 초기 기능

### 📱 **앱 기본 구조**
- **스플래시 화면**: 앱 시작 시 로고 표시
- **로그인 화면**: 카카오 소셜 로그인 UI (임시 구현)
- **메인 화면**: Bottom Navigation을 통한 탭 구조

### 🏠 **홈 탭**
- **실시간 활동 모니터링**: 센서 감지 현황 표시
- **복용 알람 관리**: 약물 복용 시간 표시 및 관리
- **캘린더/리스트 탭**: 알람 보기 방식 전환
- **툴팁 기능**: 사용자 가이드 표시
- **정보 등록 버튼**: 보호대상자/건강정보 등록 화면 이동

### 📊 **활동 탭**
- **주간 캘린더**: 최근 7일 활동 내역 조회
- **날짜별 활동 기록**: 센서 감지 데이터 리스트 표시
- **활동 상세 정보**: 시간대별 움직임 패턴 확인

### ⚙️ **설정 탭**
- **기본 설정 UI**: 앱 설정 관리 화면

### 👤 **기본 정보 등록**
- **보호대상자 정보**: 이름, 생년월일, 전화번호, 닉네임, 주소, 응급연락처
- **보호자 정보**: 이름, 전화번호, 사진, 관계
- **주소 검색**: Kakao 우편번호 서비스 연동
- **단계별 입력**: Navigation Component를 통한 플로우 관리

### ⏰ **복용 알람 관리**
- **알람 추가**: 약물명, 복용 횟수, 복용 시간, 복용 주기 설정
- **알람 수정**: 기존 알람 정보 편집
- **시간 선택기**: 직관적인 시간 입력 UI

### 🏠 **기기 관리**
- **허브 추가**: 블루투스, WiFi 연결 가이드
- **센서 추가**: 센서 위치 및 이름 설정
- **기기 편집/삭제**: 등록된 기기 관리
- **연결 상태 표시**: 기기별 연결 상태 모니터링

---

## 🏗️ **아키텍처 구현**

### **Clean Architecture**
- **Data Layer**: API 통신, 로컬 저장소 관리
- **Domain Layer**: 비즈니스 로직 및 Use Case 구현
- **Presentation Layer**: MVVM 패턴 적용

### **기술적 구현 사항**
- **Hilt**: 의존성 주입을 통한 모듈화
- **Retrofit**: REST API 통신
- **Coroutines & Flow**: 비동기 작업 및 리액티브 프로그래밍
- **ViewBinding**: 안전한 뷰 참조
- **Navigation Component**: 화면 간 네비게이션 관리
- **DataStore**: 안전한 데이터 저장

---

## 📝 진행 상황
- ✅ Clean Architecture 기반 패키지 구조 설계 완료  
- ✅ Hilt / Retrofit / Coroutines 환경 세팅  
- ✅ 스플래시 및 로그인 UI 구현
- ✅ Bottom Navigation을 통한 메인 화면 구조 구현
- ✅ 홈, 활동, 설정 탭 기본 UI 구현
- ✅ 기본 정보 등록 플로우 구현 (다단계 입력)
- ✅ 복용 알람 추가/수정 기능 구현
- ✅ 기기 관리 (허브/센서 추가) UI 구현
- ✅ 주간 캘린더 및 활동 기록 조회 기능 구현
- ✅ Kakao 우편번호 서비스 연동
- ✅ Custom UI 컴포넌트 제작 (버튼, EditText, 다이얼로그)

---

## 📌 회고
프로젝트는 초기 기능 구현 단계에서 종료되었으나, Android 앱 설계와 협업 과정에서 다음과 같은 경험을 쌓을 수 있었습니다.

**기술적 성과:**
- Clean Architecture 패턴 적용을 통한 확장 가능한 코드 구조 설계
- Hilt를 활용한 의존성 주입으로 테스트 가능한 코드 작성
- Navigation Component를 통한 체계적인 화면 전환 관리
- Custom View 컴포넌트 제작으로 일관된 UI/UX 구현

**협업 경험:**
- Git Branch 전략 수립 및 PR 기반 코드 리뷰
- 기능별 모듈화를 통한 효율적인 팀 작업 분담
- Android Coding Convention 정립 및 적용
