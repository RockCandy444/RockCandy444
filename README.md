# RockCandy444

클라우드·네트워크 환경의 동작을 패킷과 로그로 확인하고, 백엔드 API와 웹 서비스를 개발합니다.  
재현 가능한 실험과 테스트를 통해 문제를 분석하고, 해결 과정과 검증 한계를 문서로 남깁니다.

- **관심 분야**: 네트워크 · 클라우드 · 백엔드
- **Contact**: [ldh4563@gmail.com](mailto:ldh4563@gmail.com)

---

## 주요 프로젝트

### 1. [CloudShield](https://github.com/mmmphyun/aleph-project)
**클라우드 위협 탐지·자동 대응 SecOps 파이프라인 · 팀 프로젝트 · 최종 발표 완료**

- **담당**: 네트워크 모의 공격 시나리오, 신규 TCP 연결 계측 도구, tcpdump/TShark 패킷 분석, 차단·복구 왕복 검증
- **문제 해결**: 기존 SSH 세션의 생존 여부 대신 매초 새로운 TCP 연결을 시도해 차단을 관측했습니다. 정상 handshake 이후 신규 SYN 36회 연속 무응답을 PCAP과 실행 기록으로 대조했습니다.
- **분석과 검증**: L4 SG 격리와 L7 WAF의 응답 차이를 분석하고, API 반환·실제 트래픽 차단·통신 회복을 구분해 측정했습니다. 기준 시각과 목표 미달 결과, 측정 한계도 보고서에 기록했습니다.
- **주요 기술**: Python, Bash, Docker, Linux, Hydra, curl, tcpdump, TShark, pytest, AWS EC2·Security Group·WAF 차단 관측

[네트워크 보고서](https://github.com/mmmphyun/aleph-project/tree/main/docs/roles/network) · [L4 실측](https://github.com/mmmphyun/aleph-project/blob/main/docs/roles/network/2026-10-14-p3-3c-hydra-l4-remeasurement.md) · [차단·복구 왕복 검증](https://github.com/mmmphyun/aleph-project/blob/main/docs/roles/network/2026-10-30-p5-4-live-results.md)

### 2. [Gongju · 공주시립합창단](https://gongju.go.kr/gongjuchoir/)
**공연·단원·소식 등 홈페이지 콘텐츠 관리를 지원하는 CMS 백엔드 · 참여 프로젝트 · 소스 비공개**

- **담당**: 백엔드 API 개발 참여
- **프로젝트 기능**: 공연·단원·소식·팝업·메인 슬라이드·갤러리 관리, 검색·페이지네이션, 공개·비공개 조회, 관리자 인증
- **데이터와 파일 처리**: Prisma 스키마·마이그레이션을 통한 데이터 구조 변경, 게시물 번호 증가와 생성의 트랜잭션 처리, 첨부파일 업로드·교체·삭제 및 한글 원본 파일명 처리
- **주요 기술**: JavaScript, Node.js, Express, PostgreSQL, Prisma, JWT, Multer, Swagger, Docker

[공식 홈페이지](https://gongju.go.kr/gongjuchoir/)

### 3. [Coffee Marble · 커피마블](https://rockcandy444.github.io/coffeemarble/)
**참가자 명단과 당첨 등수를 설정하는 브라우저 구슬 경주 · 개인 프로젝트 · 공개 배포**

- **기능**: 최대 1,000개 구슬을 지원하는 참가자 설정, 코스별 경주와 능력 배틀, 결승 통과 순위·당첨자 판정
- **문제 해결**: 충돌·정체·진행 복구와 카메라 추적을 개선하고, 모바일 입력·배속·일시 정지 기능을 구현했습니다.
- **배포와 개선**: GitHub Pages로 배포하고 한국어·영어·일본어를 제공합니다. 명단·물리·카메라·진행 복구·다국어 회귀 검사와 변경 내역을 관리합니다.
- **주요 기술**: JavaScript, HTML, CSS, Canvas, Node.js 기반 검사 스크립트, GitHub Pages

[게임 실행](https://rockcandy444.github.io/coffeemarble/) · [소스 코드](https://github.com/RockCandy444/coffeemarble) · [변경 내역](https://github.com/RockCandy444/coffeemarble/blob/main/CHANGELOG.md)

---

## 사용 기술

| 영역 | 사용 경험 |
| --- | --- |
| 네트워크·계측 | Python, Bash, TCP/IP, tcpdump, TShark, PCAP 분석 |
| 백엔드·데이터 | JavaScript, Node.js, Express, PostgreSQL, Prisma |
| 환경·배포 | Linux, Docker, Windows·WSL2, GitHub Pages |
| 웹 | HTML, CSS, JavaScript, Canvas |
| 검증·도구 | pytest, Ruff, Git/GitHub, GitHub CLI, uv, PowerShell |

## 협업과 기록

- GitHub Issue·기능 브랜치·PR과 동료 리뷰를 통해 작업 범위와 변경 근거를 관리합니다.
- 실험 조건·패킷 타임라인·실패 원인·검증 한계를 Markdown 보고서로 기록합니다.
- PCAP의 SHA-256과 실행 manifest를 보존하고, 모의 테스트와 실제 관측의 결과를 구분합니다.
