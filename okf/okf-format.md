---
type: Concept
title: OKF의 역할과 활용
description: Mekra가 활용하는 OKF의 표현 방식과 번들 경계를 설명하고 공식 형식과 운영 판단을 구분한다
sources:
  - id: okf-spec-v03
    resource: https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md
    title: Open Knowledge Format v0.3
---

# OKF의 역할과 활용

Mekra는 현재 Open Knowledge Format(OKF)을 필수 지식 표현 형식으로 사용한다. 기존 자료와 정본 전체를 변환할 필요는 없으며, Mekra 지식은 기존 OKF를 활용하거나 OKF 형식으로 구성한다. 운영 안내만 보강한 비-OKF 구성은 Mekra 적용 완료로 보지 않는다.

OKF는 사람과 에이전트가 함께 읽고 교환할 수 있는 형식을 제공하고, Mekra는 무엇을 지식으로 남기고 어떻게 연결·유지할지 판단하는 운영 방법을 제공한다. OKF 필수 사용은 현재 Mekra의 적용 기준이며, 다른 표현 방식의 필요가 실제 적용에서 드러나면 재검토할 수 있다.

## 개념과 관계의 표현

OKF의 개념 문서는 YAML frontmatter와 Markdown 본문으로 구성한다. `type`은 개념에 항상 필요한 메타데이터이며, 개념 종류를 중앙의 고정 목록으로 제한하지 않는다. 본문에는 필수 절이 없고, 개념 사이의 관계는 Markdown 링크와 주변의 자연어로 표현한다. 링크는 방향은 있지만 종류가 정해지지 않은 관계이며, 관계의 구체적인 의미는 주변의 서술이 전한다.[^okf-spec-v03]

링크와 경로 필드의 값은 `/`로 시작하면 번들 루트에서, 그 밖의 상대 값은 그 값을 담은 파일의 디렉터리에서 해석한다. 번들 루트 밖으로 해석되는 값은 외부 참조이며, 번들을 따로 읽는 소비자는 그 대상을 로컬에서 읽지 않는다.[^okf-spec-v03]

Mekra는 이 표현을 이용해 사실의 정의뿐 아니라 이유·조건·예외와 다른 개념에 미치는 영향을 [내재화](knowledge-internalization.md)한다. 관계를 해석하고 변경 범위를 고르는 [자율 판단](agent-autonomy.md)은 Mekra의 운영 선택이다. 파일 형식을 갖추는 일과 판단에 충분한 지식을 담는 일은 함께 살핀다.

## 번들 경계와 위치

번들은 지식 문서의 디렉터리 트리이며, 저장소 전체나 더 큰 저장소의 하위 디렉터리로 배포할 수 있다. `index.md`와 `log.md`는 모든 깊이에서 예약 파일이다. 그 밖의 `.md` 파일은 frontmatter에 비어 있지 않은 `type`이 있으면 개념이다. frontmatter나 `type`이 없는 `.md` 파일은 개념이 아니지만 번들의 적합성을 해치지 않으며, `.md`가 아닌 파일은 자산이다.[^okf-spec-v03]

Mekra가 구성하는 번들에서는 frontmatter를 둔 문서를 개념으로 보고 `type`을 반드시 적는다. 이는 개념으로 쓰려던 문서가 `type` 누락으로 조용히 빠지지 않게 하는 작성 관례이며 명세의 요구가 아니다. `README.md`처럼 개념이 아닌 안내 문서는 frontmatter 없이 둘 수 있다. 다만 v0.2만 지원하는 도구는 이런 문서도 개념으로 읽으려 할 수 있으므로, 함께 쓰는 도구의 지원 판본을 [현재 OKF 기준](../versions/current.md)에서 확인한다.

저장소 전체를 읽는 에이전트에게는 번들 밖 문서로 가는 링크도 탐색 경로가 된다. 번들만 따로 배포하거나 소비하면 그 대상은 없으므로, 번들 안의 지식만으로 필요한 판단이 성립하는지 살핀다.

공식 명세는 번들의 디렉터리 이름을 `okf/`로 정하지 않는다. 새 파일 기반 Mekra의 기본 위치인 `mekra/`도 Method의 적용 선택이며 공식 형식의 요구가 아니다. 대상에서는 기존 지식의 위치와 함께 이동할 범위를 보고 번들 경계를 정하며, 구체적인 선택은 [구조와 발견](structure-and-discovery.md#번들-위치와-기존-구조)에 둔다.

`index.md`는 개념 링크와 짧은 설명을 묶어 탐색을 돕는 선택적인 예약 파일이며, 자동 생성할 수 있다. 번들 루트의 `index.md`만 frontmatter를 가질 수 있다. 여기에는 `okf_version`과 선택적인 `title`·`description`·`license`, 확장 키를 두며, 인덱스를 재생성하는 도구는 기존 frontmatter를 보존해야 한다.[^okf-spec-v03] Mekra에서는 이름과 선택 범위가 실제로 있을 때 `title`·`description`을, 권리를 확인한 경우에만 `license`를 둔다. `description`은 여러 번들 가운데 고를 때 필요한 한 문장으로 쓰고 `MEKRA.md`의 목적 설명을 되풀이하지 않는다.

Mekra에서는 질문별 분류·순서처럼 인덱스가 책임지는 고유한 탐색 정보도 유지할 수 있다. 인덱스를 재생성할 때는 그 탐색 정보와 필요한 메타데이터를 보존하도록 갱신 방식을 선택한다. 도메인의 규칙·근거는 관련 개념에 두고, 탐색 정보의 변경 책임은 인덱스에 둘 수 있다. 이는 [정본과 맥락](source-of-truth.md)을 인덱스 운영에 적용한 판단이며, 특정 생성기의 보존 동작을 보장하는 명세 규칙은 아니다.

## 명세 기능의 선택

OKF v0.3은 출처·생성·검증·수명주기 정보를 표현하는 필드, 폐기한 개념의 대체 위치를 가리키는 `superseded_by`, 계산 증명에 사용하는 형식을 제공한다. 각 필드와 개념 종류에 적용되는 조건은 공식 명세에서 확인한다.[^okf-spec-v03] [최소 템플릿](../templates/mekra/concept.md)이 사용 가능한 표현의 한계를 뜻하지는 않는다.

Mekra에서는 추적할 출처, 확인한 검증 범위, 유효성 판단 등 실제로 전달할 정보가 있는지 보고 필요한 표현을 선택한다. 메타데이터와 본문이 같은 근거 범위를 가리키도록 하며, 속성의 존재나 개수만으로 지식의 정확성·최신성·채택 여부를 판단하지 않는다. 이 선택 역시 [운영 원칙](../PRINCIPLES.md)에 따른 판단이다.

v0.3의 신뢰 등급은 마지막 의미 있는 변경(`generated.at`) 이후의 검증만으로 계산한다. 내용을 바꾼 뒤 다시 확인하지 않았다면 등급이 내려가는 것이 맞으므로, 형식 전환·번역·링크 수리만으로 검증 기록을 새로 만들거나 시각을 옮기지 않는다. `superseded_by`는 이동하거나 교체한 개념의 기존 참조를 이어야 할 때 쓰고, 일반적인 관련 문서는 본문 링크로 둔다.

## 형식과 방법론의 책임

공식 형식의 정본은 OKF 명세에 있고, Mekra가 참고하는 판본은 [현재 OKF 기준](../versions/current.md)에 기록한다. 이 문서는 활용에 필요한 맥락을 설명하며 명세 전체를 복제하지 않는다.

자율 판단, 정본과 맥락의 운영, facet, 개별 Mekra의 `MEKRA.md` 진입점과 여러 Mekra 환경의 `MEKRAS.md` 인덱스는 Mekra가 채택한 방식이다. 이를 OKF의 추가 필수 요건으로 취급하지 않는다. Mekra의 운영 방식 갱신과 OKF 형식의 버전 전환은 필요와 영향이 다를 수 있으며, [버전 안내](../versions/README.md)와 [적용 판단](adoption.md)에서 구분한다.

[^okf-spec-v03]: [OKF v0.3 §3: 번들 구조와 개념 판정](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md#3-bundle-structure), [§4: 개념 문서](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md#4-concept-documents), [§5: 출처·신뢰·수명주기](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md#5-provenance-trust-and-lifecycle), [§6: 링크와 경로](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md#6-links-and-paths), [§8: 인덱스와 번들 메타데이터](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md#8-index-files), [§10: 계산 증명](https://github.com/open-knowledge-format/open-knowledge-format/blob/527e81aff55992be21507e97004286789126f88c/SPEC.md#10-attested-computations). 형식 설명의 근거이며, Mekra의 운영 선택은 별도로 설명한다.
