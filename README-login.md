<회원 가입시>
URI : fan.catholic.ac.kr:5000/login
METHOD : POST
    request
    
    - key | explanation | type
    - user_id  | id  | (string)
    - password | pwd | (string)

- response code

Header : Content-Type : application/json

- ERROR RESPONSE

        key |explanation|type
        error_code|	오류 코드|integer
        error_msg|오류 내용|string
        error_code|(오류 별 반환 내용 및 상태)

- HTTP STATE	error_code	explanation

        400	|0|파라미터 오류, 상세 내용은 error_msg 참고
        401	|1|	토큰 만료
        401	|2|	토큰이 존재하지 않음
    
- SUCCESS RESPONSE

        key|	explanation|	type
        token|	발급 토큰(클라이언트에서 저장하세요!)	|string
        created|	토큰 발급 일 시	|string

- <응답-로그인>
로그인 성공: {id}님 안녕하세요 !
로그인 실패: 다시 로그인 하세요 !
- <로그아웃 응답>
로그아웃시:   Free meeting Active studying Nice ending! :)