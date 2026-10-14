# rss_news: RSS + 기사 100개 (가상 데이터)

기존 XML에 들어 있던 100개 가상 뉴스의 제목/설명/발행일을 그대로 유지하고, 각 기사에 실제 접근 가능한 GitHub Pages 링크를 연결하도록 준비한 파일입니다.

## 1. GitHub 업로드

1. `jihun4355/rss_news` 저장소의 `main` 브랜치에 **이 ZIP 안의 파일과 articles 폴더**를 업로드하세요 (ZIP 자체만 업로드하지 않음). 기존 `news.xml.xml` 파일은 덮어쓰세요.
2. GitHub `Settings` → `Pages` → `Build and deployment` → `Deploy from a branch` → `main` / `/(root)` → `Save`를 선택하세요.
3. Pages 배포가 완료되면 아래 URL이 열리는지 확인하세요. 저장소 이름, 계정명, Pages 공개 설정이 바뀌면 주소도 달라집니다.

## 2. 주소

RSS (Raw): https://raw.githubusercontent.com/jihun4355/rss_news/main/news.xml.xml
RSS (Pages): https://jihun4355.github.io/rss_news/news.xml
기사 예시: https://jihun4355.github.io/rss_news/articles/SEC-00001.html
목록: https://jihun4355.github.io/rss_news/

> 링크는 GitHub에 업로드하고 Pages 배포가 완료된 뒤 정상 동작합니다. 회사/수집 서버에서 GitHub 도메인에 접근 가능한지도 별도 확인하세요.

## 3. RSS 수집 설정

- url: `https://raw.githubusercontent.com/jihun4355/rss_news/main/news.xml.xml` (또는 Pages의 news.xml)
- item_field: `item`
- charset: `utf-8`
- title_field: `title`
- link_field: `link`
- date_field: `pubDate`
- date_format: `%a, %d %b %Y %H:%M:%S %z`
- creator_field: `author`
- xpath: `//*[@id="articleBody"]`

RSS 파서에 따라 item_field가 `channel/item` 또는 `/rss/channel/item`을 요구할 수 있습니다. XPath는 뉴스 링크의 HTML을 읽어 추출하는 시스템을 가정한 설정입니다. 시스템이 링크 본문을 읽지 않고 RSS 자체만 처리한다면 xpath는 다를 수 있습니다.

## 주의
- 전부 테스트용 가상 뉴스이며 외부의 실제 기사 URL로 연결되지 않습니다.
- GitHub Pages 공개 후에는 검색 및 외부 접근이 가능할 수 있습니다.
- GitHub Pages 배포와 접근 허용은 별도로 진행해야 하며, HTML 파일만 업로드하면 즉시 공개되는 것은 아닙니다.
