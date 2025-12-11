# 축꾸미
> K리그 관련 영상/사진을 편집하고 공유하는 축구 커뮤니티 앱  

<br>

## 📌 프로젝트 소개
> 프로젝트 기간: 2025/11/03 ~ 2025/11/28   
> 팀 프로젝트 (iOS 3인 구성)

**축꾸미**는 축구 커뮤니티 앱입니다.
- K리그 경기 결과, 축구 게시물을 제공하며
- 영상/사진을 편집해 커뮤니티에 공유하고
- 팔로우, 1:1 채팅으로 사용자 간 소통할 수 있습니다.

<br>

## 📌 개발 환경

- **iOS Deployment Target** : 17.0+
- **Xcode** : 26.0.1
- **Swift** : 6.1.2
- **UI Framework** : SwiftUI (+UIKit)

<br>
  
## 📌 기술스택  

**Architecture**
- TCA 기반 단방향 구조로 상태 변화 흐름 명확화 및 로직 일관성 확보
- Core(Data+Domain), Features(Presentation) 분리로 책임 분리 및 유지보수성 향상

**Network**
- URLSession 기반 Router 패턴으로 네트워크 설계, Multipart/form-data 진행률 트래킹 구현
- SocketI.O 기반 실시간 채팅 WebSocket 구축 및 전송 실패 시 REST API 재시도 기능 구현
- Actor 기반 TokenRefreshManager를 활용한 Access/Refresh Token 자동 갱신 처리로 자동 로그인 편의성 제공

**Video & Image**
- Trim, Resizing, 필터, 자막, 렌더링으로 이어지는 영상 편집 파이프라인 설계
- Crop, 필터, PencilKit 드로잉, 스티커, 텍스트 합성으로 이어지는 사진 편집 파이프라인 설계
- CIFilter, Core ML 기반 편집 필터 제공 및 MetalGPU 가속으로 처리 성능 향상
- Core ML 모델 FP16 전환으로 모델 크기 축소 및 추론 속도 향상, 모바일 환경 최적화
- 고해상도 자막 렌더링 후 다운 스케일 기반 Anti-aliasing 처리로 선명한 자막 제공
- 영상/사진 썸네일 추출로 네트워크 비용 절감 및 빠른 사용자 경험 제공

**Payment**
- iamport SDK와 서버 영수증 검증 기반 결제 기능 제공 및 결제 안정성 향상

**Frameworks**  
- SwiftUI(+UIKit), TCA, AVFoundation, CoreImage, Photos, Metal, CoreML, PencilKit, Realm, URLSession, SocketI.O, iamport

<br>

## 📌 기능
<table align="center">
  <tr>
    <th><code>메인 화면</code></th>
    <th><code>게시물 피드</code></th>
    <th><code>영상 편집</code></th>
    <th><code>사진 편집</code></th>
    <th><code>채팅</code></th>
    <th><code>프로필</code></th>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/a13ed080-ea89-4d3d-804d-e7a8b2f9cf04" alt="메인 화면"></td>
    <td><img src="https://github.com/user-attachments/assets/8fc21917-e51b-4c15-a2a6-52dc3d85f1f6" alt="게시물 피드"></td>
    <td><img src="https://github.com/user-attachments/assets/d6f7fc07-6410-47a1-9625-2c2fc5e82bf6" alt="영상 편집"></td>
    <td><img src="https://github.com/user-attachments/assets/e91cbde2-73a8-408a-b10d-7e0a5f82600a" alt="사진 편집"></td>
    <td><img src="https://github.com/user-attachments/assets/2f7c7fb3-8ee5-4c81-a471-6412314f909a" alt="채팅"></td>
    <td><img src="https://github.com/user-attachments/assets/77d53f49-698a-431b-b982-fdce218d8926" alt="프로필"></td>
  </tr>
</table>

**로그인**
- 카카오/애플 소셜 로그인, 이메일 로그인 지원
- 자동 로그인 기능 지원


**경기 결과/게시물 조회**
- 경기 결과, 선수 라인업 등 정보 제공
- K리그 팀 별/해시태그 검색으로 게시물 조회
- 좋아요, 댓글, 공유, 북마크 기능 지원


**영상/사진 편집**
- 커스텀 갤러리 구현으로 영상 혹은 사진 선택
- 영상 자르기, 자막, 배경 음악, 필터 기능 지원
- 사진 자르기, 텍스트, 그리기, 필터, 스티커 기능 지원
- AI 모델 경량화를 통한 모바일 최적화 필터 적용, PG 결제 환경 지원


**채팅**
- 1:1 채팅 기능 구현(텍스트, 사진, 영상, 게시글 공유 지원)
- 채팅방 배경 테마 적용 기능


**프로필**
- 닉네임, 소개 문구 작성 및 수정
- 사용자 닉네임 검색 및 팔로우/언팔로우 기능 제공
- 작성 게시물과 북마크 게시물 모아보기

<br>

## 📌 설치 및 실행

### 1. 프로젝트 클론
```bash
git clone https://github.com/kyhlsd/Chukkoomi
cd Chukkoomi
```

### 2. Xcode에서 프로젝트 열기
- Xcode에서 .xcodeproj (또는 .xcworkspace) 파일 열기

### 3. 빌드 및 실행
- Xcode에서 타겟 디바이스 선택 후 실행 (⌘ + R)

> **참고**: API 사용을 위해 `Secrets/` 파일이 필요합니다.

<br>

## 연락처

- **GitHub**: [@kyhlsd](https://github.com/kyhlsd)
- **Email**: kmyghn@gmail.com

