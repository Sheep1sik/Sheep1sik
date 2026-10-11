<div align="center">

<br/>

# 양원식 - Wonsik Yang

**iOS Developer**

코드 너머의 이유를 고민하는 iOS 개발자입니다.

돌아가는 코드보다 프로젝트의 규모와 단계에 맞는 코드가 더 잘 짜인 코드라고 생각합니다.  
AI가 제안한 코드도 여러 선택지 중 하나로 두고, 왜 이 방식이어야 하는지를 먼저 따져 봅니다.

<br/>

</div>

<br/>

## Skills

| 분류 | 기술 |
|---|---|
| **iOS** | Swift · SwiftUI · UIKit(SnapKit) · Swift Concurrency · RxSwift · SpriteKit · AVFoundation |
| **Architecture** | TCA · Tuist 모듈 구조 · MVVM-C · Clean Architecture |
| **Test · Build · CI/CD** | Swift Testing · XCTest · Tuist · SPM · fastlane · GitHub Actions |
| **Network · Data** | URLSession · Socket.IO · Alamofire · GRDB · SQLite · CloudKit |
| **Backend · Cross-platform** | Firebase · Supabase · React Native (Expo) |
| **AI** | Claude Code · Codex · OpenAI API |
| **Collaboration** | Notion · Slack · Figma · GitHub |

<br/>

## Projects

| 프로젝트 | 구분 | 소개 | 기간 · 상태 |
|---|---|---|---|
| **[한 칸](https://apps.apple.com/kr/app/%ED%95%9C-%EC%B9%B8-%EC%9D%BC%EC%A0%95-%EA%B4%80%EB%A6%AC-%ED%94%8C%EB%9E%98%EB%84%88/id6814798787)** | 개인 | Apple 캘린더 일정과 할 일을 한 달력과 위젯으로 모아 보는 캘린더 앱 | 2026.09 — 운영 중 |
| **[Spincell](https://apps.apple.com/kr/app/spincell/id6752841680)** | 팀 | 음악으로 연결되는 취향 기반 커뮤니티 | 2025.10 — 운영 중 |
| **Todog** | 팀 · iOS 리드 | 반려견 식사·투약·케어 일정을 기록하는 건강 케어 앱 | 2026.03 — 출시 준비 중 |
| **DeALL** | 프리랜서 | AI 인테리어 견적 플랫폼 (1인 풀스택) | 2026.05 — 2026.06 |
| **[소우주](https://apps.apple.com/kr/app/%EC%86%8C%EC%9A%B0%EC%A3%BC/id6760713435)** | 개인 | 하루의 기록을 감정 분석해 별로 만들어 주는 기록 앱 | 2026.03 — 2026.04 |
| **[MOUP](https://apps.apple.com/kr/app/moup/id6747497191)** | 팀 · 부리더 | 알바생과 사장님이 함께 쓰는 근무관리 플랫폼 | 2025.05 — 2025.12 |
| **JOSIMI** | 팀 · 경진대회 | 질병 정보 기반 식품 성분 위험도 시각화 앱 | 2024 |

<sub>이름에 링크가 있는 프로젝트는 App Store에 출시된 앱입니다.</sub>

<br/>

### 프로젝트별 맡은 일

<sub>프로젝트 이름을 누르면 펼쳐집니다.</sub>

<details>
<summary><b>한 칸</b> · 개인 · 기획·디자인·개발·출시 1인 · iPhone·iPad</summary>

- **규모에 맞춘 MVVM 구조** - TCA·Tuist 모듈화 대신 MVVM으로 시작해 프로토콜 11개로 의존성을 주입하고, 한 앱 타깃으로 iPhone·iPad 지원
- **구조 정리를 화면 104장으로 검증** - 3,173줄 ViewModel 파일을 기능별 extension 31개로 나누고, AI와 만든 XCUITest 비교로 화면 104장·데이터 덤프 26개가 같은지 확인
- **일정·할 일을 한 달력과 위젯으로** - EventKit 일정과 미리 알림을 합치고, 앱과 위젯 5종이 App Group의 같은 SQLite 저장소를 함께 사용
- **할 일 iCloud 동기화** - 저장 방식 6가지를 조사해 자체 SQLite + CKSyncEngine 선택, 할 일마다 iCloud·이 기기 선택
- **스크롤 막힘 원인을 측정으로 규명** - XCUITest로 시작 위치별 이동량(275pt 대 0)을 재 SwiftUI 롱프레스가 원인임을 찾고 UIKit 제스처 인식기로 교체
- **Swift Testing 583개** - 자연어 날짜 파서·반복 규칙·동기화까지 기준 시각을 주입해 검증

`SwiftUI` `UIKit` `WidgetKit` `EventKit` `SQLite` `CloudKit` `Swift Testing` `Tuist`

</details>

<details>
<summary><b>Spincell</b> · 팀 · iOS 2 · DM·클러스터 담당</summary>

- **TCA·Tuist 전환에서 DM·클러스터 담당** - 팀 리팩토링에서 DM·클러스터 Feature 모듈과 소켓·로컬 DB Core 모듈 구현
- **폴링 조회 시간당 최대 18만 건(추산) 제거** - 50명 그룹 채팅의 1초 폴링을 Socket.IO로 전환, 신규 기능인 DM에서 먼저 검증한 뒤 확장
- **재연결·누락 복구까지 갖춘 실시간 채팅** - 재연결 백오프, 누락 메시지 복구, 낙관적 업데이트, GRDB 캐시 구현
- **간헐적 EXC_BAD_ACCESS 크래시 해결** - 스레드 안전하지 않은 Socket.IO 호출을 라이브러리가 요구하는 단일 직렬 큐로 일원화
- **출시 후 클러스터 전면 개선** - 1,683줄 상세 리듀서 정리, 곡 재생 연결·커버 이미지·24시간 일시 정지 구현, 떼어 낸 기능에 테스트 추가

`SwiftUI` `TCA` `Tuist` `Socket.IO` `GRDB` `Firebase` `fastlane`

</details>

<details>
<summary><b>Todog</b> · 팀 · iOS 리드 · iOS 2</summary>

- **Tuist 5계층 모듈 구조 직접 설계** - 첫 커밋부터 의존성 플러그인·모듈 템플릿·make module 생성 도구를 만들어 두 명이 같은 규칙으로 개발, Feature마다 Example 앱
- **동시 토큰 갱신 요청을 1회로** - 라이브러리 없이 URLSession 통신 계층을 만들고, 선제 갱신·400/401 폴백과 actor 기반 단일 갱신을 Swift Testing으로 검증
- **홈 기능 전체 설계·구현** - 식사 기록·투약·케어 일정·예방접종·몸무게 화면과 API 연동
- **5겹 중첩 네비게이션을 StackState로 정리** - 온보딩·비용 관리 화면 전환을 StackState Path로 펴서 종료 신호 전달을 4단계에서 1단계로
- **공개 TestFlight 테스터 34명 베타 운영** - fastlane으로 작업마다 Firebase App Distribution 배포, 내부 TestFlight 검수 후 릴리스

`SwiftUI` `TCA` `Tuist` `Swift Concurrency` `URLSession` `fastlane`

</details>

<details>
<summary><b>DeALL</b> · 프리랜서 · 1인 풀스택 · 드올 인터내셔널</summary>

- **처음부터 1인 개발** - 디자인 시안과 저장소도 없는 상태에서 React Native iOS·Android 앱, Supabase 백엔드(Edge Functions 11개, 마이그레이션 40개), 배포까지 구축
- **크레딧 위·변조·중복 지급·도용 차단** - App Store Server API·Google Play Developer API 서버 검증과 거래 멱등 처리
- **견적 총액은 코드가 확정** - AI는 물량을 추정하고, 총액은 DB 단가로 계산하는 결정론 엔진이 확정
- **수십 초 걸리던 견적 요청을 바로 접수** - 요청은 즉시 접수하고 결과는 Realtime으로 받는 비동기 구조, 멈춘 세션 자가 복구
- **iOS archive 실패를 원인부터 해결** - 임시 전역 플래그를 걷어내고 문제 pod 두 개만 정적 라이브러리로 빌드해 복구
- **인수인계 가능한 코드베이스** - fastlane 배포 자동화, ADR 12건과 인수인계 문서

`React Native` `TypeScript` `Supabase` `expo iap` `OpenAI API` `fastlane`

</details>

<details>
<summary><b>소우주</b> · 개인 · 기획·개발·출시 1인</summary>

- **은하를 셰이더 하나로 GPU에서 생성** - 노드 조합 대신 GLSL 프래그먼트 셰이더로 절차 생성, 화면 밖 잔별은 뷰포트 컬링으로 제외
- **감정을 별의 시각 속성으로 변환** - OpenAI API로 기록의 감정을 분석해 별의 색·크기·반짝임에 반영
- **테스트 200여 개와 PR 게이트** - GitHub Actions에서 빌드·테스트·SwiftLint를 실행해 리팩토링 중 회귀 방지

`SwiftUI` `TCA` `Tuist` `SpriteKit` `SKShader` `OpenAI API`

</details>

<details>
<summary><b>MOUP</b> · 팀 · 부리더 · iOS 4</summary>

- **팀 부리더** - 기능 기획, 화면 흐름 정리, 개발 일정 조율
- **팀 공통 데이터 계층 선구현** - Service·Repository·UseCase를 먼저 만들어 팀원이 공통으로 사용, 실시간 리스너로 근무지·급여 데이터 동기화
- **급여·근무 핵심 로직 구현** - 급여 계산, 근무지·루틴·캘린더 로직, 회원 탈퇴 시 데이터 정리
- **Spring Boot 전환 후 등록 기능 구현** - 근무지·근무 등록과 수정, 초대 코드 합류, 사장님의 대리 등록을 UIKit·RxSwift로 구현

`UIKit` `RxSwift` `Firebase` `Clean Architecture` `MVVM C` `SnapKit`

</details>

<details>
<summary><b>JOSIMI</b> · 팀 · 공공데이터 창업 경진대회 장려상</summary>

- **SwiftUI MVP iOS 개발** - AVFoundation 바코드 인식과 공공데이터 API로 식품 성분 조회·안전성 정보 제공

`SwiftUI` `Combine` `CoreData` `AVFoundation`

</details>

<br/>

## Awards

**2024** · 제12회 범정부 공공데이터 활용 창업경진대회 왕중왕전 · 장려상
<br/>
**2021** · 창의·융합·통섭형 학생역량강화 캠프 · 동상
<br/>
**2018** · 고양시 스마트 시티 메이커톤 · 우수상

<br/>

## Recent Blog Posts

<!-- BLOG-POST-LIST:START -->
- [[ SwiftUI ] Button, Toggle, TextField로 배우는 SwiftUI 컨트롤](https://sheep1sik.tistory.com/230)
- [[ UIKit ] Auto Layout](https://sheep1sik.tistory.com/229)
- [[ Swift ] 열거형(Enum)](https://sheep1sik.tistory.com/228)
- [[ SwiftUI ] Text &middot; Image](https://sheep1sik.tistory.com/227)
- [[ UIKit ] 컨테이너 ViewController](https://sheep1sik.tistory.com/226)
<!-- BLOG-POST-LIST:END -->

<br/>

## Contact

<div align="center">

[![Gmail Badge](https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=Gmail&logoColor=white)](mailto:sheep1sik@gmail.com)
[![Instagram Badge](https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=Instagram&logoColor=white)](https://www.instagram.com/Sheep1sik/)
[![Blog Badge](https://img.shields.io/badge/Tistory-Blog-000000?style=flat-square&logo=Apple&logoColor=white)](https://sheep1sik.tistory.com/)

</div>
