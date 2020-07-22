# fan.catholic.ac.kr-api-reference
fan.catholic.ac.kr 의 API Reference Repository 입니다.

## 회원가입 (요청)
- (예시) 부분에 프론트가 백엔드에게 요청하는 경우 ( 요청 ), 프론트가 요청한 API 백엔드가 제작 완료한 경우 ( 완료 )
- URI : fan.catholic.ac.kr:5000/register
- METHOD : POST
- request

    | key | explanation | type |
    |--- |--- |--- |
    |key      | explanation  | type
    |user_id  | id:아이디    | string
    |password | pwd:비밀번호 | string
    |name     | name :이름   | string
    |student_id| 학번        | int
    |grade    | grade :학년  | int
    |semester |semester:학기 | int
    |phone    |phone:전화번호|string
    |email    |email:이메일  |string

- response code
    - Header :
        Content-Type : application/json
    - ERROR RESPONSE
    
        |    key   | explanation |   type  |
        | -------- | ----------- |-------- |
        |error_code| 오류 코드     | integer | 
        |error_msg | 오류 내용  | string  |
        
        - error_code (오류 별 반환 내용 및 상태)
        
            | HTTP STATE | error_code | explanation |
            |----------- | ---------- | ----------- |
            | 400 |0| 파라미터 오류, 상세 내용은 error_msg 참고 |
            | 401 |1| 토큰 만료 | 아이디에 특수문자 존재 등|
            | 401 |2| 토큰이 존재하지 않음|
            |  |3| 아이디 등 빈칸이 있을때 |
            |  |4| 전화번호 숫자가 모자를때 |
            |  |5| 학번의 숫자가 모자를때|
            |  |6| 이미 가입을 하였는데 중복 가입 하려는 경우|
    
    - SUCCESS RESPONSE
    
        | key | explanation | type |
        |--- |--- |--- |
        | token | 발급 토큰(클라이언트에서 저장하세요!) | string |
        | created | 토큰 발급 일 시 | string |
        
       -  <응답-회원 가입시> 회원가입 성공 : {id}님 환영합니다! 
       -  회원가입 실패: 빈칸이나 혹은 오타 확인 해주세요!
