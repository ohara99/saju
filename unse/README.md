# 운세 풀이 앱 (Unse App)

생년월일시로 한국 전통 명리(사주)를 계산하고, 분야별(취업·시험·연애·사업) 운세를 시기 흐름(대운·세운·월운)과 함께 AI로 풀어주는 단일 HTML 웹앱입니다. 결과는 한글 PDF로 저장됩니다.

## 폴더 구성

```
.
├── README.md
├── local/
│   └── unse-local.html          # 로컬용: 본인 PC에서 열고 API 키를 직접 입력
└── skill/
    └── unse-app/                # Claude 스킬 패키지
        ├── SKILL.md
        └── assets/
            ├── unse-app.html        # Claude 환경용(키 불필요)
            └── unse-app-local.html  # 로컬용(키 입력) — local/ 파일과 동일
```

## 1) 로컬 버전 (`local/unse-local.html`)

- 본인 컴퓨터의 브라우저에서 파일을 직접 엽니다.
- AI 풀이를 쓰려면 화면 상단에 **본인 Anthropic API 키**(`sk-ant-...`)를 입력합니다.
  - 키는 서버로 전송·저장되지 않고 브라우저 메모리에만 머뭅니다.
  - 키 발급: console.anthropic.com
- 사주 계산·표 보기·PDF 저장은 키 없이도 동작합니다(AI 풀이만 키 필요).

## 2) Claude 환경용 (`skill/unse-app/assets/unse-app.html`)

- claude.ai 아티팩트 등 Claude 환경에서 열면 **API 키 입력 없이** AI 풀이가 작동합니다.
  (`api.anthropic.com` 호출을 Claude 환경이 대행)

## 3) 스킬 (`skill/unse-app/`)

Claude가 "운세 앱 만들어줘" 같은 요청에 이 완성본을 바로 제공하도록 하는 스킬 패키지입니다.
`SKILL.md`에 사용 환경별 제공 방법과 수정 위치가 정리되어 있습니다.

## 주의

- 운세 풀이는 자기 이해를 돕는 참고용이며, 미래를 단정하거나 의학·법률·재무 판단의 근거가 아닙니다.
- 음력 변환은 양력 1000~2050년 범위에서 정확합니다.
- 절기 경계일에는 드물게 하루 오차가 있을 수 있습니다.
