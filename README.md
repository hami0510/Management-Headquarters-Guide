# KCIM 일가정양립 지원 가이드 v2.0 — 배포 안내

## 실행
```
pip install -r requirements.txt
streamlit run app.py
```

## 챗봇 (선택)
`.streamlit/secrets.toml` 파일에 아래 한 줄 추가 시 AI 상담이 활성화됩니다. 없으면 챗봇 외 모든 기능은 정상 동작합니다.
```
OPENAI_API_KEY = "sk-..."
```
⚠️ 외부 API 전송 구조이므로 사내 보안정책 검토 전에는 직원 실명 등 개인정보 입력을 금지하도록 안내되어 있습니다.

## 케이스 저장
`kcim_cases.json` 파일에 자동 저장됩니다. Streamlit Community Cloud 등 임시 스토리지 환경에서는 재배포 시 초기화될 수 있으니, 사내 서버 배포를 권장합니다.

## 유지보수 포인트 (매년 개정 시)
- 법정 제도: `app.py` 상단 `STEPS` 블록의 `legal` 항목만 수정
- 회사 복지: `STEPS`의 `company` 항목 + 상단 `VERSION_BASIS` 문구 수정
- 미확정 사안 3건(휴직자 복지 적용 / 차년도 연차 선사용 / 리프레시 사용 시점)은 확정 시 STEP 4·5·7 및 플래너 경고 문구 갱신

## 검증 완료 항목 (2026-07-04)
- 홈/단계/계산기 전 화면 렌더 및 상호작용 (Streamlit AppTest)
- 기존 Excel 사례(예정일 2026-09-07) 검산 일치: 연차 23일/소계 17일, 출산휴가 08-12~11-09
- 케이스 저장·복직 D-day·체크리스트 영속성
