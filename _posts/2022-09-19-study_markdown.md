---
title : 마크다운(Markdown) 으로 글쓰기
date : 2022-09-19 20:30:00 +09:00
categories : [프로그래밍, 블로그]
tags : [blog, markdown] #소문자만 가능
---

수일간 컴퓨터와 씨름한 끝에 jekyll-Chripy-theme적용을 완료하였다.  
jekyll은 markdown이라는 언어를 사용하여서 포스트를 작성하는데 오늘은 이에 관해서 공부를 해보려 한다.

# 1. 마크다운(Markdown)이란?
위키백과에서는 이렇게 서술하고 있다
>마크다운은 일반 텍스트 기반의 경량 마크업 언어다. 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다.  

라고...서술되어있지만 처음 배우는 입장에서는 전혀 간단한것 같지 않다

# 2. 문법
## 1. 글자크기  
글자 한칸 앞에 `#`을 붙이는 방식으로 크기를 정한다  
#은 1~6개까지 붙일 수 있으며 #의 개수가 많아질수록 글자 크기가 작아진다  
># # 예시1
>## ## 예시2
>### ### 예시3
>#### #### 예시4
>##### ##### 예시5
>###### ###### 예시6

## 2. 각주 리스트  
문장 한칸 앞에 `-` `+` `*` 중에 하나를 붙여서 각주를 작성한다.  
>\- 리스트  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\+ 리스트 1_1  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\* 리스트 1_2

>- 리스트
  + 리스트 1_1
  * 리스트 1_2

## 3. 번호가 있는 리스트  
숫자뒤에 점`.`을 찍어 번호가 있는 리스트를 작성한다.  
단, 기입한 숫자와 실제로 붙는 번호는 관계가 없다.   
>1\. 번호가 있는 리스트1  
1\. 번호가 있는 리스트2  
1\. 번호가 있는 리스트3

>1. 번호가 있는 리스트1
1. 번호가 있는 리스트2
1. 번호가 있는 리스트3

## 4. 번호가 없는 리스트

## 5. 인용
문장 처음에 `>`를 붙여서 인용을 사용한다.  
`>>`를사용하여 2중선을 작성하는것도 가능하다.  
>\>인용  
\>>2중인용  

>인용
>>2중인용

## 6. 코드블록 
`스페이스4개`나 `TAB`을 문장 앞에 추가함으로써 코드블록을 표시한다.  
이 외에도 문자열의 앞과 뒤를 `~`나`` ` ``3개로 감싸서 표시할 수 있다.


    # Space or TAB
    class Hoge
      def hoge
        print 'hoge'
      end
    end  
   
##### 이때 특정언어를 명시하여 문법에 대한 서식을 적용할 수 있다

```ruby
class Hoge
    def hoge
        print 'hoge'
    end
end
```
	
## 7. 코드 표현
억음부호`` ` ``로 문자열을 감싸서 코드를 표현 가능하다  
>이렇게 \`문자열을 감싸서 코드를\` 표현 가능하다  

>이렇게 `문자열을 감싸서 코드를` 표현 가능하다

## 8. 강조: 이텔릭(italic)
별`*`또는 언더바`_`1개로 문자열을 감싸서 강조한다.  
>normal \*italic\* normal  
normal \_italic\_ normal

>normal *italic* normal  
normal _italic_ normal

## 9. 강조: 굵게(bold)
별`*`또는 언더바`_`2개로 문자열을 감싸서 강조한다.  
>normal \*\*bold\*\* normal  
normal \_\_bold\_\_ normal

>normal **bold** normal  
normal __bold__ normal

## 10. 강조: 이텔릭+굵게
별`*`또는 언더바`_`3개로 문자열을 감싸서 강조한다.  
>normal \*\*\*italic+bold\*\*\* normal  
normal \_\_\_italic+bold\_\_\_ normal

>normal ***italic+bold*** normal  
normal ___italic+bold___ normal

## 11. 강조: 취소선

## 12. 수평선
하이픈`-`또는 언더바`_` 또는 별`*`을 3개 연속으로 작성하여 수평선을 표시한다.
(중간에 공백이 있어도 상관없다)  
>\-\-\-
>
>\_\_\_
>
>\*\*\*
>
>\*  \*  \*

>---
>
>___
>
>***
>
>* * *

## 13. 하이퍼링크
`[표시문자](해당URL)`로 표현 가능하다.  
>\[handkin's blog](https://handkin.github.io/)  
[handkin's blog](https://handkin.github.io/)

만약 같은 URL을 여러번 사용할 경우 `[정의]:해당URL`로 따로 URL을 미리 정의하여 사용할 수 있다.

>\[이 링크는 handkin으로 연결됩니다]\[handkin's blog]  
여러 문자열  
\[이 링크도 handkin으로 연결됩니다]\[handkin's blog]  
\[handkin's blog]:https://handkin.github.io/

>[이 링크는 handkin으로 연결됩니다][handkin's blog]  
여러 문자열  
[이 링크도 handkin으로 연결됩니다][handkin's blog]

[handkin's blog]:https://handkin.github.io/

## 14. 페이지 내 링크
마크다운에서는 #을 사용하여 문단제목을 표시했을때 자동적으로 앵커가 생성된다.  
이를 이용하여 페이지 내 특정문단으로 이동이 가능하다.  
표현은 링크와 비슷하게 `[표시문자](#해당문단제목)`으로 표현 가능하다.  

>\* \[to header1](#header1)  
>\* \[to header2](#header2)
>
>\[return to menu](#menu)

## menu
* [to header1](#header1)
* [to header2](#header2)

[return to menu](#menu)
### header1
### header2

## 15. 표
문자열을 `|`로 감싸서 표를 표현한다.
또`:--` `--:` `:--:`등으로 문자열의 정렬위치를 지정할 수 있다.
```
|header1|header2|header3|
|:--|--:|:--:|
|align left|align right|align center|
|a|b|c|
```

|header1|header2|header3|
|:--|--:|:--:|
|align left|align right|align center|
|a|b|c|



## 후기
거의 처음으로 써보는 게시글로 생각보다 작성하는데 시간이 많이 걸렸지만 모든 문법들을 한번씩 다 써보게 되어 나름 나쁘지 않은 경험이라고 생각한다  
사실 이 게시글도 markdown을 공부하면서 작성한거라 중간에 새로 안 문법으로 표현을 바꾸거나 하는 경우도 있었기에 아마 조금 일정한 규칙이 없이 난잡하게 보일 수도 있을 것 같다.  
그렇지만 markdown을 처음 써보는데 생각보다 괜찮은 퀄리티가 나와서 어느정도 만족하고 있다.  



###### 출처  
###### "마크다운" 위키피디아. last modified Apr 4. 2022, accessed Set 19. 2022, https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4  
###### "Markdown記法 サンプル集" Qiita. last modified Mar 27. 2020, accessed Set 19. 2022, https://qiita.com/tbpgr/items/989c6badefff69377da7#%E8%A1%A8%E7%A4%BA%E4%BE%8B-9
