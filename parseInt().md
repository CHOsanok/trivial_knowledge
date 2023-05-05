# A mystery behavior of parseInt()

parseInt(numericalString)항상 첫 번째 인수를 문자열로 변환한 다음
(문자열이 아닌 경우)

해당 숫자 문자열을 정수 값으로 구문 분석합니다.


아래의 경우 예상한 결괏값으로는 모두 0이 나올 거라 생각했지만
```
parseInt(0.000005); // => 0
parseInt(0.0000005); // => 5
```
결과는 제가 예상한것과는 다르게 동작되었습니다 

이유는 10<sup>-6</sup>보다 작은 실수는 지수표기법으로 작성이 되기 때문에

0.0000005  =>  5e-7 이러한 작은 부동 소수점을 사용하면 예기치 않은 결과가 발생 한다


[Dmitri Pavlutin](https://dmitripavlutin.com/parseint-mystery-javascript/)

사이트를 참고 하여 궁금중을 해결 하였습니다
