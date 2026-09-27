# Current OKF baseline

이 문서는 공식 명세의 권장 기준을 기록합니다. Mekra Method 자체의 릴리스와 실제 참고 커밋은 [버전 안내](README.md)에서 구분합니다.

| 항목 | 값 |
| --- | --- |
| 권장 기준 | OKF v0.2 |
| 공식 명세 | [SPEC.md](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/main/SPEC.md) |
| 확인일 | 2026-09-18 |
| 확인한 SPEC blob | `c06e3eede0c910d0ecf12524c34204156f8795ac` |
| 기준 명세 고정 링크 | [SPEC.md @ ad30107](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md) |

공식 명세 링크는 upstream의 현재 문서를, 고정 링크는 위 blob과 일치하는 기준 문서를 엽니다. 2026-09-26 GitHub API로 고정 링크의 `SPEC.md` blob이 기록과 같음을 확인했습니다. 이는 기존 기준의 참조 경로 확인이며, 최신 upstream 전체의 재검토나 기준 변경은 아닙니다.

## 이 저장소의 적용

- 새 template과 facet은 특별한 이유가 없으면 v0.2를 기준으로 합니다.
- 기존 번들은 새 버전이 나왔다는 이유만으로 즉시 전환하지 않습니다. 실제 호환성, 얻는 이점과 migration 비용을 평가합니다.
- 이 문서는 명세를 복제하지 않습니다. 이 저장소의 운영 방식에 영향을 주는 차이만 migration 문서에 기록합니다.

현재 확인한 v0.2에서는 concept의 유일한 필수 frontmatter key가 `type`이며, bundle-root `index.md`에 `okf_version: "0.2"`를 선언할 수 있습니다. provenance·trust·lifecycle·attestation 필드는 필요에 따라 사용합니다.
