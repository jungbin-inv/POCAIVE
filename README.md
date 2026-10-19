# POCAIVE

그룹별 포토카드 입고·반출을 기록하고 현재 재고를 누적 계산하는 재고 관리 페이지입니다.

## 기능

- 입고 / 반출 등록 (그룹 · 구분 · 날짜 · 수량(장) · 메모)
- 구분: 반송 이관 · 대량입고 이관 · 글로벌 대량입고 이관 · 앨범깡 이관
- 현재 재고 현황 (그룹별 합계 + 구분별 수량), 검색·정렬
- 주요그룹 지정 (☆ 클릭 또는 엑셀 업로드)
- 엑셀 일괄 등록 (양식 다운로드 → 작성 → 업로드 → 미리보기 확인 후 등록)
- 재고 출입 내역 (기간·유형 필터, 삭제, CSV 내보내기)

## GitHub Pages로 배포하기

1. 새 저장소를 만들고 `index.html`을 루트에 올립니다.
2. 저장소 **Settings → Pages** 에서 Source를 `Deploy from a branch`, Branch를 `main` / `(root)` 로 저장합니다.
3. 1~2분 뒤 `https://<계정>.github.io/<저장소>/` 에서 열립니다.

## 데이터 저장 방식 (중요)

이 버전은 데이터를 **사용하는 브라우저의 localStorage**에 저장합니다.

- 같은 PC·같은 브라우저에서는 새로고침해도 유지됩니다.
- 다른 사람, 다른 PC, 다른 브라우저와는 **공유되지 않습니다.**
- 브라우저 사이트 데이터를 지우면 기록도 지워집니다. 주기적으로 CSV 내보내기로 백업하세요.

팀원이 같은 재고를 함께 보려면 Firebase(Firestore)나 Supabase 같은 서버 저장소를 연결해야 합니다.
코드에서 `makeLocalDB()`가 저장소 역할을 하므로, 이 부분만 교체하면 됩니다.

## 외부 라이브러리

- [SheetJS (xlsx 0.18.5)](https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js) — 엑셀 읽기/쓰기
- Google Fonts — IBM Plex Sans KR, IBM Plex Mono
