# fan.catholic.ac.kr-api-reference - 팬 공지사항 리스트 (요청)
# 의도: ( 새로운 글쓰기를 클릭을 하여 ) 글을 작성하여 적고 리스트로 보낼 예정입니다.

fan.catholic.ac.kr 의 API Reference Repository 입니다.

- (예시) 부분에 프론트가 백엔드에게 요청하는 경우 ( 요청 ), 프론트가 요청한 API 백엔드가 제작 완료한 경우 ( 완료 )
- URI : fan.catholic.ac.kr:5000/api/notice/new
- METHOD : Post

- request

    | key | explanation | type |
    |--- |--- |--- |
    | user_id | 로그인 된 현재 아이디 | string |
    | title | 제목 | string |
    | text | 내용 | string |
    | image | 이미지 및 파일들? | string |
    

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
            | |3| 글을 안적고 저장 하려는 경우|
            | |4| 그림이나 이미지가 못 받아지는 경우?|
            | |5| 제목을 안적고 저장 하려는 경우|
             | |6| 임원진이 아닌 자가 글작성을 하여 저장을 하려는 경우|
   
    - SUCCESS RESPONSE
    
        | key | explanation | type |
        |--- |--- |--- |
        | token | 발급 토큰(클라이언트에서 저장하세요!) | string |
        | created | 토큰 발급 일 시 | string |
        
        - 성공시 - 리스트로 넘어감
        
        - 실패시 - 리스트로 넘어가지 않고
        에러 메시지가 뜨게됨 => 접근 할 수 없는 페이지입니다!
