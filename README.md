# A2Viewer

아이온2 파티 뷰어 — 패킷 캡처 기반 파티원 전투력 조회 + 실시간 DPS 미터 오버레이

## 스크린샷

| 조회 패널 | DPS 패널 |
|:-:|:-:|
| ![노말모드](normal.png) | ![노말모드](normal2.png) |
| ![컴팩트모드](compact.png) | ![컴팩트모드](compact2.png) |

## 설치 및 실행

1. [**A2Viewer.exe 다운로드**](https://github.com/gkrdl/A2Viewer/releases/latest)
2. 아이온2 게임 실행 → 캐릭터 선택 창까지 진행
3. **A2Viewer.exe** 실행 (관리자 권한 자동 요청, Npcap 미설치 시 자동 안내)
4. 캐릭터 로그인

> 별도 설치 과정 없이 exe 파일 하나로 바로 실행됩니다 (Portable).
> 앱 내 자동 업데이트를 지원합니다.

## 주요 기능

### 파티원 전투력 조회
- 패킷 캡처로 파티 가입/신청 자동 감지
- 전투력(CP) · 아툴(AT) 점수 조회 — 색상 배지로 구분 표시
- CP/AT 점수 DB 캐싱 — API 실패 시 마지막 저장값 자동 fallback
- 스티그마 스킬 추적 (직업별 설정)

### DPS 미터
- 실시간 파티원별 데미지/DPS 집계
- 전투력(CP) · 아툴(AT) 점수 표시 (CP만 / AT만 / 둘 다)
- DPS 측정 방식 선택 — 개인 딜 시간 / 파티 딜 시간 / 총 전투 시간(기믹 포함)
- 주 타겟 전용 집계 (비주 타겟 데미지 자동 제외)
- 보스 전환 시 자동 리셋 + 이전 전투 기록 자동 저장
- 스킬별 상세 통계 (크리티컬/백어택/하드히트/최소·최대 데미지)
- 스킬 기반 직업 자동 추론
- 최대 50건 전투 기록 열람
- 허수아비 모드 — 내 캐릭터 타격만 집계

### 오버레이
- 게임 위에 항상 표시 (클릭 투과)
- 컴팩트 모드 (카드만 표시)
- 게임 포그라운드 연동 (자동 표시/숨김)
- 투명도 조절, 글씨 크기 조절
- 자동 업데이트 알림 (30분 간격 체크, 비침투적 알림 바)

### 단축키
| 기능 | 기본값 |
|------|--------|
| 새로고침/DPS리셋 | Alt+1 |
| 숨기기/보이기 | Alt+` |
| 카드만 보기 | Alt+2 |
| 탭 전환 | Alt+3 |

> 설정에서 단축키 변경 가능. ESC로 해제(없음) 설정 가능.

## 요구사항

- Windows 10 이상
- 관리자 권한 (오버레이 기능)
- [Npcap](https://npcap.com) (미설치 시 자동 안내)
- WebView2 Runtime (Windows 10/11 기본 포함)

## 기술 스택

| 구성 요소 | 기술 |
|-----------|------|
| 런타임 | .NET 8 WinForms |
| UI 렌더링 | WebView2 + React 19 |
| 패킷 캡처 | Npcap (SharpPcap) |
| DPS 엔진 | PacketProcessor.dll (네이티브) |
| JS 실행 | Jint |

## 크레딧

- **[Aion2-Dps-Meter-Packet-Process](https://github.com/HappNJLand/Aion2-Dps-Meter-Packet-Process)** — DPS 미터 패킷 파싱 엔진 (PacketProcessor.dll). 감사합니다!
