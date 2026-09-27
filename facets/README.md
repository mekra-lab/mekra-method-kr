# Facets

facet은 대상에서 중요한 **한 측면이나 성질을 읽기 위한 관점**입니다. 여러 facet이 동시에 관련될 수 있으며, facet은 적용할 preset이나 저장소 구조 템플릿이 아닙니다.

에이전트는 대상의 실제 상태에서 관련 facet을 식별하고, 연결된 운영 지식과 기존 저장소 관례를 바탕으로 구조와 작업 방식을 자율적으로 판단합니다. facet 일치 여부가 OKF 적합성을 결정하지 않습니다.

| Facet | 의미 |
| --- | --- |
| [Software project](software-project.md) | 코드와 설정이 구현 사실의 주요 정본인 환경 |
| [Knowledge-centered](knowledge-centered.md) | 지식 자체가 주된 산출물인 환경 |
| [Large corpus](large-corpus.md) | 자료 규모나 복잡성 때문에 전부 내재화하기 어려운 환경 |
| [Personal context (preview)](personal-context.md) | 개인의 삶·관계·상태·선호를 장기 맥락으로 다루는 환경을 실험 중 |

새 facet은 가능한 경우의 수를 채우기 위해 만들지 않습니다. 대상에서 쉽게 관찰되지만 별도 판단을 더하지 않는 성질, 또는 공통 개념만으로 충분히 설명되는 문제는 facet으로 다시 소유하지 않습니다. 자세한 판단은 [Facet의 역할과 경계](../okf/facet-boundaries.md)에 둡니다.

`preview` facet은 아직 채택되지 않은 연구 후보입니다. 기본 적용의 전제로 삼지 않고 관련 실험이나 사례를 탐색할 때 참고합니다.

facet은 하나의 Markdown 문서를 기본 단위로 둡니다. facet 고유 자료가 실제로 여러 파일 필요해지기 전에는 하위 디렉터리를 만들지 않으며, 추가 내용이 공통 운영 지식·note·experiment·example 중 어디에 속하는지 먼저 판단합니다.

설계 판단의 정본은 [운영 지식망](../okf/index.md)에 있습니다. facet은 그 지식을 특정 환경에서 읽기 쉽게 연결하는 얇은 관점입니다.
