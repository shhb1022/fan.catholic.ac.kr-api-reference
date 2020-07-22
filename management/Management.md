## 회원관리 (요청)

- URI : fan.catholic.ac.kr:5000/member
- METHOD : POST
- request

    | key | explanation | type |
    |--- |--- |--- |
    | student_id | 학번 | int |
    | name | 이름 | string |
    
 
 
- URI : fan.catholic.ac.kr:5000/member/detail
- METHOD : POST
- request

    | key | explanation | type |
    |--- |--- |--- |
    | student_id | 학번 | int |
    | name | 이름 | string |
    | id | 아이디 | string |
    | grade | 학년 | int |
    | semester | 학기 | int |
    | phone | 전화번호 | string |
    | email | 이메일 | string |
    | rent | 도서대출여부(0/1) | int |
    | payment | 회비납부(0/1) | int |
    | level | 회원등급(0/1) | int |

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
            |  |3| 회비 납부 여부 수정에 실패 |
            |  |4| 회원 단계 수정에 실패|
    
    - SUCCESS RESPONSE
    
        | key | explanation | type |
        |--- |--- |--- |
        | token | 발급 토큰(클라이언트에서 저장하세요!) | string |
        | created | 토큰 발급 일 시 | string |
