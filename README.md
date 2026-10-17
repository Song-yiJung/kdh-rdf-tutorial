# 한국학 자료와 시맨틱 데이터 입문 · Introduction to Semantic Data for Korean Studies

RDF로 만드는 지식그래프 첫걸음 — 케이팝 데몬 헌터스(KPop Demon Hunters)를 공통 자료로 한 40분 튜토리얼 자료이다.
A 40-minute tutorial on building a first knowledge graph with RDF, using *KPop Demon Hunters* as shared material.

- 강의자 · Instructor: 정송이 Jung Song-yi (한국학중앙연구원 디지털인문학연구소 · Academy of Korean Studies, Digital Humanities Research Institute) — [song-yijung.github.io](https://song-yijung.github.io/)
- 대상 · Audience: 한국학 전공 외국인 학부생 · International undergraduates in Korean Studies
- 장소 · Venue: Vienna, October 2026

## 데이터셋 · Dataset

| 항목 · Item | 값 · Value |
| --- | --- |
| 이름 · Name | 케이팝 데몬 헌터스와 한국 문화유산 · KPop Demon Hunters and Korean Heritage |
| prefix | `kdh` |
| 주소 · Namespace | `http://dh.aks.ac.kr/2026/kdh/` |
| 규모 · Size | 클래스 6, 관계 8, 개체 19, 관계 트리플 21 (파일 전체 트리플 435) · 6 classes, 8 relations, 19 individuals, 21 relation triples (435 in total) |

## 파일 · Files

| 경로 · Path | 내용 · Contents |
| --- | --- |
| `data/kdh_sample.ttl` | Protégé 5.5.0에서 여는 Turtle 파일 · Turtle file for Protégé 5.5.0 |
| `data/kdh-schema.tsv` | 클래스·관계 정의 (샘플 + 확장 예시) · Classes and relations (sample + extension examples) |
| `data/kdh-instance.tsv` | 개체 19개 · 19 individuals |
| `data/kdh-triple.tsv` | 관계 21개와 근거(remark) · 21 relations with remarks |
| `queries/*.rq` | 수업에서 쓰는 SPARQL 질의 3개 · Three SPARQL queries used in class |
| `slides/` | 수업 슬라이드 · Tutorial slides |

## 설계 원칙 · Design notes

- 모티프(유형)와 유물(실물 한 점)을 나눈다. 등장인물은 모티프에만 잇고, 유물은 `exampleOf`로 모티프에 잇는다.
  Motif (type) and Artifact (single object) are separate; characters link only to motifs.
- `heldBy`는 소장(현재 관리 기관, CIDOC CRM P50과 같은 뜻)이며 전시 여부를 뜻하지 않는다.
  `heldBy` means current keeper (as CIDOC CRM P50), not "on display".
- 표준 어휘가 있으면 가져다 쓴다(`schema:memberOf`, `schema:isBasedOn`). 없는 것만 `kdh:`로 정의한다.
- 트리플의 근거(remark)는 `owl:Axiom` 주석으로 관계에 붙인다.

## 학생 데이터셋 · Student datasets

조마다 prefix(영어 소문자 2–5자)와 주소 `http://dh.aks.ac.kr/2026/<prefix>/`를 정한다. ID는 조별 번호대(G01 → A0100–A0199, G02 → A0200–A0299 …)를 쓴다.
Each group picks a prefix and the namespace `http://dh.aks.ac.kr/2026/<prefix>/`, with its own ID range.

## 출처 · Sources

각 개체의 근거 링크는 `kdh-instance.tsv`의 `infoUrl` 열에 있다. 포스터 이미지는 저작권 문제로 저장소에 포함하지 않는다.
Source links are in the `infoUrl` column. Poster images are not included.

## 응용 사례 · Related work

Jung, S., Lim, I., Kim, B. (2026). *Developing an AI Cultural Heritage Docent Web Prototype: Internalizing Institutional Guidelines for Responsible Curation.* DH2026. [Zenodo](https://zenodo.org/records/21803582)
