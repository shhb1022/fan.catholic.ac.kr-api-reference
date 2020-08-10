# fan.catholic.ac.kr-api-reference - 팬 자유 게시판 리스트 (요청)
# 의도: 게시판의 리스트 목록이 뜰 예정 입니다.

fan.catholic.ac.kr 의 API Reference Repository 입니다.

- (예시) 부분에 프론트가 백엔드에게 요청하는 경우 ( 요청 ), 프론트가 요청한 API 백엔드가 제작 완료한 경우 ( 완료 )
- URI : fan.catholic.ac.kr:5000/api/fanboard
- METHOD : PUT (게시글에 대한 리스트를 작성하는 것으로 PUT이라고 이해했습니다 다만 문제가 있다면 고쳐주세요!)

- request

    | key | explanation | type |
    |--- |--- |--- |
    | noq. | 게시글번호 | integer |
    | user_id | 로그인 된 현재 아이디 | string |
     | title | 제목 | string |

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
            | |3| 로그인 안한 사람이 글을 작성 하려고 함|
            | |4| 본인의 게시글이 아닌 타인의 게시글을 삭제 하려는 경우|
            | |5| 높은 회원 등급의 글을 삭제 하려는 경우|
   
    - SUCCESS RESPONSE
    
        | key | explanation | type |
        |--- |--- |--- |
        | token | 발급 토큰(클라이언트에서 저장하세요!) | string |
        | created | 토큰 발급 일 시 | string |
        
        성공시 - 글쓰기 작성으로 넘어감
        실패시 - 글쓰기 작성으로 넘어가지 않고 / 에러 메시지가 뜨게됨
