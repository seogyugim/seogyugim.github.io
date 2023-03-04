# HTTP 응답 크기를 줄이는 법

## 찾아본 방법

1. 압축으로 사이즈 자체를 줄이는 것
   - CPU가 많이 든다
2. 청킹(스트리밍)해서 응답을 쪼개는 법
   - 서버 상태에 따라서 응답이 너무 느려질 수 있을까 찾아봐야 함

## 참고 문서

- [Web HTTP Compression](https://developer.mozilla.org/ko/docs/Web/HTTP/Compression)
- [HTTP Headers Transfer-Encoding](https://developer.mozilla.org/ko/docs/Web/HTTP/Headers/Transfer-Encoding)