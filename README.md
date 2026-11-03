# AI Skills
**Codex**와 **Claude Code**에서 사용하는 개인용 AI 스킬 모음입니다. 각 zip은 스킬 폴더 하나이고, 사용법은 그 안의 `SKILL.md`에 있습니다.

## 공부 자료 스킬
강의 한 단위를 검증된 시험 대비 PDF로 만듭니다. 두 스킬이 `STUDY.md` 하나를 주고받습니다.

```
강의·실습·질문·시험 정보 → course-study-builder → _study/STUDY.md → study-sheet-design → PDF
```

| 스킬 | 하는 일 | 실행 |
|---|---|---|
| `course-study-builder` | 자료와 단원 폴더 정리, 읽기, 검증, STUDY.md 작성 | `scripts/check_study.py STUDY.md` |
| `study-sheet-design` | 그림 SVG 그리기, 수험서 판면 PDF 조판과 점검 | `scripts/build.py STUDY.md` |

- **STUDY.md**는 기계용 파일입니다. 구조는 영어, 인쇄될 내용은 한국어로 쓰고, 규격은 `course-study-builder/reference/format.md` 하나뿐입니다.
- **고치는 곳**: 내용은 STUDY.md, 그림은 `_study/figures/<id>.svg`. `sheet.html`은 빌드 산출물이라 고치지 않습니다.
- **필요한 것**: Python 3, Chromium 계열 브라우저(없으면 `build.py --html-only`), PyMuPDF.
- **읽기 쉬움**: 모든 글자는 바탕과 4.5:1 이상 대비가 나야 하고, `build.py`가 PDF에서 재서 알려 줍니다. 쪽수 목표는 없고, 빈 쪽 없이 이어서 흐르게 조판합니다.

단원 폴더는 이렇게 정리됩니다.

```
07_예외처리/
  강의/ 실습/ 과제/ 메모/        원본 자료 (이동만, 삭제·덮어쓰기 없음)
  _study/STUDY.md, figures/     기계용 파일
  7주차_공부자료(예외 처리).pdf   결과물
```

`study-skills-dev.zip`(로컬 전용, 커밋하지 않음)에는 회귀 테스트(강의 PDF, 실습 코드, 과제, 이전 질문과 기준 결과), 기능 예제, 견본 HTML, 평가 시나리오가 있습니다. 스킬 실행에는 필요 없습니다.
