# Mekra Method

*Knowledge finds its place.*

Mekra Method는 AI 에이전트가 프로젝트의 맥락을 이해하고 이어서 일할 수 있도록 지식을 정리하고 유지하는 방법론입니다.

매번 같은 배경을 설명하거나, 한 결정이 다른 작업에 미치는 영향을 다시 찾아야 한다면 그 이유와 관계를 관련 지식에 남길 수 있습니다. 판단에 필요한 지식과 맥락을 갖추고, 구체적인 작업 방식은 가능한 한 에이전트에게 맡깁니다.

## 시작하기

적용할 저장소를 읽고 수정할 수 있는 에이전트에게 다음처럼 요청합니다.

> https://github.com/mekra-lab/mekra-method-kr/releases/latest 를 이 저장소에 적용해줘.

기본 적용 기준은 최신 정식 릴리스입니다. 적용을 시작할 때 해당 릴리스의 태그·커밋을 확인하고, 그 기준의 적용 안내와 관련 문서를 이어 읽습니다. `main`에서 읽는 문서는 이후의 설명·링크 개선을 포함할 수 있습니다.

에이전트는 기존 자료와 구조를 살펴 어떤 지식을 정리하고 연결할지 판단합니다. 필요한 내용을 반영한 뒤에는 새 자료와 변경을 어디에, 어떻게 반영할지도 안내합니다.

[**Mekra Method 소개**](INTRODUCTION.md) — 이름과 기원, 슬로건, 핵심 아이디어와 원칙을 소개합니다. 실제 적용은 [적용 안내](APPLICATION.md)에서 시작합니다.

## 핵심 관점

**정본을 명확히 하고, 맥락을 나누고, 판단을 맡깁니다.**

사실을 정의하고 바꾸는 기준은 명확히 두고, 관련 개념에는 그 사실이 자신의 의미·조건·판단에 미치는 영향을 필요한 만큼 재서술합니다. 같은 사실의 반복보다 여러 문서가 그 사실을 독립적으로 정의하고 변경하는 상태를 피합니다. 기준이 바뀌면 관련 설명도 함께 검토합니다.

Mekra는 세부 작업 순서를 미리 지정하기보다 판단 근거가 되는 지식을 구성하고 유지하는 데 우선순위를 둡니다. 에이전트는 실제로 읽은 근거와 맥락을 바탕으로 목적과 상황에 맞는 작업 방식을 판단합니다.

판단의 근거는 [정본과 맥락](okf/source-of-truth.md), [지식 내재화](okf/knowledge-internalization.md), [맥락 파급](okf/context-propagation.md), [에이전트의 자율 판단](okf/agent-autonomy.md), [운영 원칙](okf/operating-principles.md)에 있습니다.

## 사용하는 법

원하는 작업을 더 구체적으로 표현할 수도 있습니다. 다음은 같은 URL과 함께 사용할 수 있는 요청 예시입니다.

| 요청 예시 | 주된 의도 |
| --- | --- |
| 이 repo에 OKF를 구축해줘. / 이 repo를 OKF화해줘. | 현재 자료를 살펴 필요한 구조와 지식망 구축 |
| 기존 OKF를 Mekra Method 방식으로 마이그레이션해줘. / 최신 Mekra Method 기준으로 맞춰줘. | 기존 지식을 보존하며 운영 방식 갱신 |
| 이 repo를 지식 중심 저장소에 맞게 정리해줘. | 지식이 주된 산출물인 특성을 고려해 운영 방식 판단 |
| OKF 버전을 올려줘. | 공식 명세 변경의 영향과 전환 필요성 판단 |
| 현재 OKF를 점검해줘. | 현재 구성과 지식의 적절성 진단 |
| 현재 OKF 구조를 점검하고 필요한 부분을 고쳐줘. | 진단과 필요한 개선 반영 |

표현을 정확히 맞추거나 내부 작업 이름을 알 필요는 없습니다. 에이전트는 [적용 안내](APPLICATION.md)에서 시작해 요청과 대상의 현재 상태를 함께 해석합니다. “적용해줘”는 필요한 작업을 종합 판단하는 요청이며, 구체적인 요청에서는 그 목적과 범위에 맞게 관련 철학과 facet을 참고합니다.

대상에서 알 수 있는 사항은 자율적으로 판단하고, 결과를 바꾸는 사용자 의도가 불명확할 때 필요한 질문을 합니다. 권장 방식으로 판단을 맡기거나 주요 선택을 함께 결정할 수 있으며, 완료 후에는 새 원자료와 지식의 투입 위치 및 반영 방법을 안내합니다.

facet은 preset이나 기본값이 아니라 판단 렌즈입니다. 템플릿 역시 필요한 경우 조정해서 쓰는 출발점입니다. 적합성은 파일 수나 구조 일치 여부가 아니라, 지식이 올바른 맥락에서 이해되고 변경의 영향이 필요한 곳에 반영되는지로 판단합니다.

## OKF와의 관계

Mekra Method는 현재 Open Knowledge Format(OKF)을 기반으로 하며, 기존 OKF Method의 지식과 이력을 이어갑니다. OKF는 사람과 에이전트가 함께 읽고 교환할 수 있도록 지식을 표현하는 형식입니다. 이 저장소는 채택한 원칙과 판단 지침을 제공하는 한국어 공개판입니다.

이 가이드는 명세의 복사본이나 모든 프로젝트가 따라야 할 프레임워크가 아닙니다. 공식 형식의 정본은 [GoogleCloudPlatform/open-knowledge-format](https://github.com/GoogleCloudPlatform/open-knowledge-format)입니다.

글로벌 영문판: [mekra-lab/mekra-method](https://github.com/mekra-lab/mekra-method). 예시와 적용 맥락은 특정 개인·조직을 식별하지 않도록 일반화해 서술합니다.

## 구조

| 위치 | 역할 |
| --- | --- |
| [`INTRODUCTION.md`](INTRODUCTION.md) | Mekra의 이름·기원·슬로건·핵심 아이디어·설계 선택 |
| [`APPLICATION.md`](APPLICATION.md) | 대상 탐색, 적용 판단과 문답, 반영 및 완료 후 사용 안내 |
| [`FEEDBACK.md`](FEEDBACK.md) | 적용·장기 운영 경험의 조사, 피드백 작성과 전송 안내 |
| [`okf/`](okf/index.md) | Mekra의 운영 원칙·패턴·적용 판단과 OKF 활용 지식 |
| [`facets/`](facets/README.md) | 대상의 성질에서 중요한 판단을 찾는 얇은 관점 |
| [`templates/`](templates/README.md) | 프로젝트에 복사한 뒤 문맥에 맞게 고치는 최소 뼈대 |
| [`versions/`](versions/README.md) | 기준 OKF 버전, Mekra Method 릴리스와 실제 참고 기준, 마이그레이션 기록 |
| [`experiments/`](experiments/README.md) | 가설과 검증 중인 방법 |
| [`notes/`](notes/README.md) | 아직 정리되지 않은 관찰과 고찰 |

## 연구와 적용 지식

이 저장소는 한국어 배포판입니다. 연구개발 공간에서 채택한 공개 가능한 지식을 제공하며, 같은 지식의 [글로벌 영문판](https://github.com/mekra-lab/mekra-method)도 배포합니다. 피드백은 사용자가 참고한 배포판에서 받고, 사례의 연구·검증은 연구개발 공간에서 이어갑니다.

[공개 범위와 언어별 책임](okf/distribution.md)에 따라 배포판을 갱신합니다. 마지막으로 검토한 원본과 배포 파일의 기준점은 [동기화 기록](SYNC.json)에 남깁니다.

채택한 판단 근거는 `okf/`에 두고, `facets/`는 관련 판단을 찾는 탐색 관점, `templates/`는 선택 가능한 적용 뼈대로 둡니다. `notes/`와 `experiments/`는 연구 자료이며 미채택 내용은 기본 적용 근거로 삼지 않습니다. 실제 운영에서 얻은 관찰은 이곳에 남기고, 재사용할 만한 결론을 관련 개념과 적용 자료에 반영합니다.

적용 중 발견한 가이드의 한계나 재사용할 개선은 [피드백](FEEDBACK.md)으로 돌아올 수 있습니다. 실제 사용 후에는 대상 저장소에서 다음처럼 요청할 수 있습니다.

> `이 저장소에서의 Mekra Method 사용 경험을 https://github.com/mekra-lab/mekra-method-kr 기준으로 피드백해줘.`

에이전트는 대상 저장소와 필요한 이력, 참고한 가이드를 살펴 공유 가능한 초안을 만듭니다. 조사와 작성은 [피드백 안내](FEEDBACK.md)에서 시작하며, 외부 전송은 사용자가 맡긴 범위에서 수행합니다. 평범한 적용마다 별도 보고를 요구하지 않습니다.

## 운영과 연락처

Mekra Method는 [Mekra Lab](https://github.com/mekra-lab)이 연구·개발·운영합니다.

- 일반 문의와 협업 제안: [contact@mekralab.org](mailto:contact@mekralab.org)
- 적용·사용 경험 피드백: [feedback@mekralab.org](mailto:feedback@mekralab.org). GitHub Issue와 전송 방법은 [피드백 안내](FEEDBACK.md)를 참고합니다.

## 현재 기준

- 권장 기준: **OKF v0.2**
- 확인일과 검증한 명세 기준점: [`versions/current.md`](versions/current.md)

최신 정식 릴리스를 기본 적용 기준으로 사용합니다. 공개 `main`에는 적용 의미를 유지하는 설명·링크·사용성 개선을 검토 후 수시로 반영할 수 있으며, 적용 판단이나 핵심 원칙을 바꾸는 변경은 릴리스와 함께 반영합니다. 개선을 정식 적용 기준에 포함하려면 새 릴리스를 발행합니다. 새 Mekra Method 릴리스는 `mekra-X.Y`를 기본으로 하고 별도 패치 배포에는 `mekra-X.Y.Z`를 사용합니다. OKF 명세 기준은 별도로 기록하며 기존 태그는 보존합니다. 변경 수준의 의미와 실제 참고 커밋을 남기는 방법은 [버전 안내](versions/README.md)에 있습니다.

## 라이선스

별도 표시가 없는 파일은 [Apache-2.0](LICENSE)을 따릅니다. `templates/` 전체는 README를 포함해 [CC0-1.0](templates/LICENSE)으로 제공하며, 복사·수정한 템플릿에 Mekra Method 출처를 남길 의무는 없습니다. 자세한 범위는 [배포 원칙](okf/distribution.md#라이선스-범위)에 있습니다.
