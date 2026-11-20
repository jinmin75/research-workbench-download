# 0.12.6 공개 배포 검사

2026-11-21, 가상 연구자 시나리오 점검 보고서의 수정 사항을 반영해 `0.12.6` 학생용 배포 ZIP을 빌드하고 자동 회귀 테스트 전체를 통과했습니다.

| 항목 | 결과 |
| --- | --- |
| 시나리오 점검 반영 (설계 판정·분리 저장) | 유보·부정 표현을 구분하는 `analyzeClaimText`, 목적·문헌(`records`) 경로 분기, `selectedAlternativeId` 연동 주장 범위, `previewAdoption` 직전 기록 참조, 질적·혼합 근거 및 주장 초안 편집 시 수치 계산 유지(`calculationSemanticFields`), cross-site 상단 `GET` 허용을 구현했습니다. |
| 앱 내부 확인 대화상자 및 계산 보존 | 브라우저 흐름에서 `window.confirm`을 앱 내부 확인 대화상자(`[data-confirm-dialog]`)로 교체해 헤드리스 VM 테스트 호환 계층 한 곳만 남겼습니다. 확인 대화상자 취소·수락과 질적·통합·초안 편집 뒤 계산 상태 유지 계약을 검사했습니다. |
| 척도·비교 진단과 AI 맥락 요약 | 기술통계와 비교 결과 소수 셋째 자리 반올림, 척도 이탈(`5점 리커트` 범위 밖 값)·소표본(`n < 10`)·결측(20% 이상) 진단 알림, 비교 방법(`Welch t`·`대응표본 t`) 및 군집·가중 보정 보류 표기, AI 맥락 요약 통계(`buildCalculationSummary`)와 개인정보 주의 알림(`detectPrivacyWarnings`)을 확인했습니다. |
| 전체 자동 회귀 테스트 | `node --test tests/*.test.mjs` 526개 중 **526개 통과** (실패 0건, 건너뜀 0건). |
| 배포 패키지 빌드 | `node scripts/build-release.mjs`로 **research-workbench-student-0.12.6.zip** (4,363,131바이트)을 생성했습니다. |

## 검사 범위

`0.12.6` 빌드는 개발 환경의 전체 단위·통합·UI 계약 자동 테스트(526개)와 ZIP 패키징을 확인했습니다. 빈 폴더에서의 공개 ZIP 첫 설치 실행, 실제 학생 PC·학교망 환경, 외부 AI 계정 로그인 및 실시간 응답은 `0.12.6`에서 별도 수동 재실행하지 않았습니다. [0.12.5 검사 기록](RELEASE-VERIFICATION-v0.12.5.md) · [0.12.4의 실제 AI 계정 검사](RELEASE-VERIFICATION-v0.12.4.md)

## 파일 확인

**research-workbench-student-0.12.6.zip** · 4,363,131바이트

SHA-256

```text
e24275c36ac71694b5aec8a388e40a7531123f24e5cd380104134e8d29a2eafe
```

[학생용 통합 ZIP 다운로드](https://github.com/jinmin75/research-workbench-download/releases/download/v0.12.6/research-workbench-student-0.12.6.zip) · [상세 사용법과 재현 실습](USER-GUIDE.md) · [0.12.5 검사 기록](RELEASE-VERIFICATION-v0.12.5.md)
