# Current OKF baseline

이 문서는 공식 명세의 권장 기준을 기록합니다. Mekra Method 자체의 릴리스와 실제 참고 커밋은 [버전 안내](README.md)에서 구분합니다.

| 항목 | 값 |
| --- | --- |
| 권장 기준 | OKF v0.3 |
| 공식 저장소 | [open-knowledge-format/open-knowledge-format](https://github.com/open-knowledge-format/open-knowledge-format) |
| 공식 명세 | [SPEC.md](https://github.com/open-knowledge-format/open-knowledge-format/blob/main/SPEC.md) |
| 확인일 | 2026-11-23 |
| 확인한 SPEC blob | `0dc3f7aa0fc710e588ba918eb115935d41eb2943` |
| 기준 명세 고정 링크 | [SPEC.md @ 527e81a](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md) |

공식 명세 링크는 upstream의 현재 문서를, 고정 링크는 위 blob과 일치하는 기준 문서를 엽니다. 2026-11-23 GitHub API로 새 공식 저장소의 main이 `527e81a`이고 `SPEC.md` blob이 기록과 같음을 확인했습니다. 이전 공식 저장소 [GoogleCloudPlatform/open-knowledge-format](https://github.com/GoogleCloudPlatform/open-knowledge-format)은 개발이 새 저장소로 옮겨 갔다고 안내하며 더 갱신되지 않습니다.

## 이 저장소의 적용

- 새 template과 facet은 특별한 이유가 없으면 v0.3을 기준으로 합니다.
- 기존 번들은 새 버전이 나왔다는 이유만으로 즉시 전환하지 않습니다. 실제 호환성, 얻는 이점과 migration 비용을 평가합니다. v0.2에서 옮길 때 확인할 점은 [v0.2 → v0.3 전환 안내](migrations/v0.2-to-v0.3.md)에 있습니다.
- 이 문서는 명세를 복제하지 않습니다. 이 저장소의 운영 방식에 영향을 주는 차이만 migration 문서에 기록합니다.

현재 확인한 v0.3에서 개념은 frontmatter에 비어 있지 않은 `type`이 있는 Markdown 파일입니다. `type`이 없는 Markdown은 개념이 아니지만 번들의 적합성을 해치지 않습니다. bundle-root `index.md`에는 `okf_version: "0.3"`과 선택적인 `title`·`description`·`license`를 선언할 수 있습니다. provenance·trust·lifecycle·attestation 필드는 필요에 따라 사용합니다.

## OKF v0.2만 지원하는 도구

2026-11-23 현재 확인한 외부 도구 가운데 Google Knowledge Catalog의 `kcmd`는 공개된 v0.2 범위로 OKF를 지원하며, `bundle/` 안에 `type`이 없는 `.md`가 있으면 push를 거부합니다([PR #672](https://github.com/GoogleCloudPlatform/knowledge-catalog/pull/672)). 이런 도구로 번들을 주고받아야 한다면 `okf_version: "0.2"`를 유지하고 번들 안의 모든 Markdown에 `type`을 두는 v0.2 구성을 계속 사용할 수 있습니다. 도구의 지원 판본은 바뀔 수 있으므로 사용할 때 확인합니다.

## 이전 기준

| 기간 | 권장 기준 | 확인한 SPEC blob | 고정 링크 |
| --- | --- | --- | --- |
| 2026-09-18 ~ 2026-11-23 | OKF v0.2 | `c06e3eede0c910d0ecf12524c34204156f8795ac` | [SPEC.md @ ad30107](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md) |

이전 기준에 따라 만든 번들과 과거 릴리스의 고정 근거는 그 판본의 링크를 계속 사용합니다.
