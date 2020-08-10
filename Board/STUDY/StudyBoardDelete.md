# fan.catholic.ac.kr-api-reference - 팬 스터디 리스트 삭제 (요청)
# 의도: 리스트에서 삭제를 하면 데이터 전체가 삭제 됩니다.

fan.catholic.ac.kr 의 API Reference Repository 입니다.

- (예시) 부분에 프론트가 백엔드에게 요청하는 경우 ( 요청 ), 프론트가 요청한 API 백엔드가 제작 완료한 경우 ( 완료 )
- URI : fan.catholic.ac.kr:5000/api/study/delete
- METHOD : Post

- request

    | key | explanation | type |
    |--- |--- |--- |
    | user_id | 로그인 된 현재 아이디 | string |
    | title | 제목 | string |
    | delete | 삭제 요청| string |
    

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
            | |3|다른 사람의 글을 삭제 하려는 겨우|
            | |4|팀장이 아닌 자가 글을 삭제 하려는 겨우|
   
    - SUCCESS RESPONSE
    
        | key | explanation | type |
        |--- |--- |--- |
        | token | 발급 토큰(클라이언트에서 저장하세요!) | string |
        | created | 토큰 발급 일 시 | string |
        
        - 성공시 - 삭제 되었습니다.
        
        - 실패시 - 다시 확인 해주세요! 
