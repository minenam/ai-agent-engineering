# 팀원 갱신 방법

## 1. 처음 한 번

```bash
git clone https://github.com/minenam/ai-agent-engineering.git
cd ai-agent-engineering
```

저장소 쓰기 권한이 없으면 리더(남혜민)에게 GitHub ID를 알려주세요. collaborator로 초대합니다.

## 2. 갱신할 때마다

```bash
git switch main
git pull
git switch -c docs/<내-폴더명>-<주제>   # 예: docs/woo-yujin-v0.4.12
```

1. **내 폴더(`members/<내-폴더명>/`)만** 수정합니다. 팀 공통 문서(`README.md`, `CONTRIBUTING.md`)를 고쳐야 하면 PR 설명에 이유를 적어주세요.
2. 커밋하고 push한 뒤 `main`으로 PR을 올립니다.
3. 리더가 확인하고 머지합니다.

```bash
git add members/<내-폴더명>
git commit -m "docs(<내-폴더명>): <무엇을 갱신했는지>"
git push -u origin HEAD
gh pr create --fill   # 또는 GitHub 웹에서 PR 생성
```

폴더 이름이 마음에 들지 않으면 PR로 바꿔도 됩니다. 루트 `README.md`의 링크도 같이 고쳐주세요.

## 3. 내 폴더 구성

```
members/<내-폴더명>/
├── README.md     # 대표 문서. members/_template/README.md 구조를 따릅니다
├── logs/         # 주차별 수행 내역, Notion에서 내보낸 md
└── assets/       # 스크린샷, 다이어그램
```

### Notion 문서를 옮길 때

1. Notion 페이지에서 `···` → `내보내기` → `Markdown & CSV`를 선택합니다.
2. 압축을 풀어 md 파일은 `logs/`, 이미지는 `assets/`에 넣습니다.
3. md 안의 이미지 경로를 `../assets/파일명.png`로 바꿉니다.
4. 파일 이름에 붙은 Notion ID(`페이지 41d23e83....md`)는 지우고 `week06-security-review.md`처럼 바꿔주세요.

## 4. 올리기 전 보안 체크

이 저장소는 **공개(public)** 입니다. 심사위원과 외부인이 모두 볼 수 있습니다.

- [ ] API Key, 토큰, 비밀번호가 없다 (`.env`, 설정 파일, 스크린샷 포함)
- [ ] 회사 이름, 사내 코드, 고객 정보가 없거나 마스킹했다
- [ ] 비공개 Notion·사내 문서 링크를 넣지 않았다
- [ ] 다른 사람의 개인정보(이메일, 전화번호)가 없다

## 5. 마감

| 날짜 | 내 폴더에 있어야 할 것 |
| --- | --- |
| **11/25(수)** | `README.md`의 문제 정의, 해결 방식, OpenAI 기술 활용, 구현 현황, 결과물 링크 |
| 11/27(금) | 리더가 위 내용으로 프로젝트 설명서 PDF를 만들어 제출 |

11/25까지 채워주셔야 설명서에 반영할 수 있습니다.
