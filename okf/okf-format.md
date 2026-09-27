---
type: Concept
title: OKF의 역할과 활용
description: Mekra가 활용하는 OKF의 표현 방식과 번들 경계를 설명하고 공식 형식과 운영 판단을 구분한다
sources:
  - id: okf-spec-v02
    resource: https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md
    title: Open Knowledge Format v0.2
---

# OKF의 역할과 활용

Mekra는 현재 Open Knowledge Format(OKF)을 기반으로 지식과 맥락을 표현한다. OKF는 사람과 에이전트가 함께 읽고 교환할 수 있는 형식을 제공하고, Mekra는 무엇을 지식으로 남기고 어떻게 연결·유지할지 판단하는 운영 방법을 제공한다.

## 개념과 관계의 표현

OKF의 개념 문서는 YAML frontmatter와 Markdown 본문으로 구성한다. `type`은 항상 필요한 메타데이터이며, 개념 종류를 중앙의 고정 목록으로 제한하지 않는다. 본문에는 필수 절이 없고, 개념 사이의 관계는 Markdown 링크와 주변의 자연어로 표현한다.[^okf-spec-v02]

Mekra는 이 표현을 이용해 사실의 정의뿐 아니라 이유·조건·예외와 다른 개념에 미치는 영향을 [내재화](knowledge-internalization.md)한다. 관계를 해석하고 변경 범위를 고르는 [자율 판단](agent-autonomy.md)은 Mekra의 운영 선택이다. 파일 형식을 갖추는 일과 판단에 충분한 지식을 담는 일은 함께 살핀다.

## 번들 경계와 위치

번들은 지식 문서의 디렉터리 트리이며, 저장소 전체나 더 큰 저장소의 하위 디렉터리로 배포할 수 있다. 번들 안의 `index.md`와 `log.md`는 예약 파일이고, 나머지 `.md` 파일은 개념 문서로 취급한다.[^okf-spec-v02]

공식 명세는 번들의 디렉터리 이름을 `okf/`로 정하지 않는다. 이 저장소의 이름 선택을 생태계 전체의 확립된 관례로 일반화하지 않는다. 대상에서는 기존 지식의 위치와 함께 이동할 범위를 보고 번들 경계를 정하며, 구체적인 선택은 [적용 판단](adoption.md#번들-위치와-기존-구조)에 둔다.

## 명세 기능의 선택

OKF v0.2는 출처·생성·검증·수명주기 정보를 표현하는 필드와 계산 증명에 사용하는 형식을 제공한다. 각 필드와 개념 종류에 적용되는 조건은 공식 명세에서 확인한다.[^okf-spec-v02] [최소 템플릿](../templates/okf/concept.md)이 사용 가능한 표현의 한계를 뜻하지는 않는다.

Mekra에서는 추적할 출처, 확인한 검증 범위, 유효성 판단 등 실제로 전달할 정보가 있는지 보고 필요한 표현을 선택한다. 메타데이터와 본문이 같은 근거 범위를 가리키도록 하며, 속성의 존재나 개수만으로 지식의 정확성·최신성·채택 여부를 판단하지 않는다. 이 선택 역시 [운영 원칙](operating-principles.md)에 따른 판단이다.

## 형식과 방법론의 책임

공식 형식의 정본은 OKF 명세에 있고, Mekra가 참고하는 판본은 [현재 OKF 기준](../versions/current.md)에 기록한다. 이 문서는 활용에 필요한 맥락을 설명하며 명세 전체를 복제하지 않는다.

자율 판단, 정본과 맥락의 운영, facet과 선택적 `MEKRA.md` 진입점은 Mekra가 채택한 방식이다. 이를 OKF의 추가 필수 요건으로 취급하지 않는다. Mekra의 운영 방식 갱신과 OKF 형식의 버전 전환은 필요와 영향이 다를 수 있으며, [버전 안내](../versions/README.md)와 [적용 판단](adoption.md)에서 구분한다.

[^okf-spec-v02]: [OKF v0.2 §3: 번들 구조](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md#3-bundle-structure), [§4: 개념 문서](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md#4-concept-documents), [§5: 출처·신뢰·수명주기](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md#5-provenance-trust-and-lifecycle), [§6.1: 관계의 표현](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md#61-links-between-concepts), [§10: 계산 증명](https://github.com/GoogleCloudPlatform/open-knowledge-format/blob/ad30107c31c06aec8a7d5636e0d1058118604e6f/SPEC.md#10-attested-computations-concept). 형식 설명의 근거이며, Mekra의 운영 선택은 별도로 설명한다.
