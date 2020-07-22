<회원 가입시>
URI : fan.catholic.ac.kr:5000/register
METHOD : POST
    request
    
    |key      | explanation | type
    |user_id  | id          | (string)
    |password | pwd         | (string)
    |name     | name        | (string)
    |student_id| student_id| (int)
    |grade    | grade       | (int)
    |semester |semester     | (int)
    |phone    |phone        |(string)
    |email    |email        |(string)
    
- response code

Header : Content-Type : application/json

- ERROR RESPONSE

        |key |explanation                   |type    |
        |error_code|	오류 코드             | integer|
        |error_msg|오류 내용                  |string|
        |error_code|(오류 별 반환 내용 및 상태) |

- ERROR RESPONSE

      
        |   key    | explanation |   type  |
        |--------  | ----------- |-------- |
        |error_code|오류 코드      |integer  |
        |error_msg |오류 내용      |string   |
        |error_code|(오류 별 반환 내용 및 상태)

- HTTP STATE	error_code	explanation

        |400	|0|파라미터 오류, 상세 내용은 error_msg 참고|
        |-------|-----------------------|------------- |
        |401	|1                      |	토큰 만료    |
        |401	|2                      |	토큰이 존재하지 않음|
    
- SUCCESS RESPONSE

        |key  |	explanation         |	type           |
        |token|	발급 토큰(클라이언트에서 저장하세요!)	|string|
        |created|	토큰 발급 일 시	|string            |

- <응답-회원 가입시>
회원가입 성공 : {id}님 환영합니다!
회원가입 실패: 빈칸이나 혹은 오타 확인 해주세요!