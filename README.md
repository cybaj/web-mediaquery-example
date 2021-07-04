# web-mediaquery-example
[MDN media queries](https://developer.mozilla.org/ko/docs/Web/CSS/Media_Queries/Using_media_queries) 설명을 참조함.
- CSS :
    - [CSS](https://developer.mozilla.org/ko/docs/Web/CSS) [@media](https://developer.mozilla.org/ko/docs/Web/CSS/@media)와 [@import](https://developer.mozilla.org/ko/docs/Web/CSS/@import) [@규칙](https://developer.mozilla.org/ko/docs/Web/CSS/At-rule)을 사용해 특정 조건에 따라 스타일을 적용할 때.

        ```css
        @media only screen and (max-width: 480px) {
            .box {
                background-color: orange;
            }
        }
        @import url("print.css") print;

        ```

- HTML :
    - [\<style\>](https://developer.mozilla.org/ko/docs/Web/HTML/Element/style), [\<link\>](https://developer.mozilla.org/ko/docs/Web/HTML/Element/link), [\<source\> (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source), 기타 다른 [HTML](https://developer.mozilla.org/ko/docs/Web/HTML) 요소에 `media` 특성을 사용해 특정 매체만 가리키게 할 때.

        ```html
        <style media="screen and (max-width: 780px">
            .box {
                border: 20px dashed green;
            }
        </style>
        ```

- JavaScript :
    - [Window.matchMedia()](https://developer.mozilla.org/ko/docs/Web/API/Window/matchMedia)와 [MediaQueryList.addListener() (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/addListener) [JavaScript](https://developer.mozilla.org/ko/docs/Web/JavaScript) 메서드를 사용해 [미디어 상태를 판별하고 관측 (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)할 때.

        ```jsx
        const isMobileMediaQuery = "screen and (max-width: 480px)"
            window.onload = (e) => {
                window.document.getElementsByClassName('box')[0].textContent = window.matchMedia(isMobileMediaQuery).matches
            }
            function isMobile() {
                return window.matchMedia(isMobileMediaQuery).matches
            }
            window.document.addEventListener('click', () => {
                console.log(`is mobile : ${isMobile()}`)
            })
            window.matchMedia(isMobileMediaQuery).addEventListener('change', (e) => {
                window.document.getElementsByClassName('box')[0].textContent = e.matches
            })
        ```
