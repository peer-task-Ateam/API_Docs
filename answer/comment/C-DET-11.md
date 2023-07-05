# 답글의 댓글 삭제하기

## 공통 정보


<!-- 요청 시 URL 입니다. Root url에 대해서는 제외하고 서술합니다. -->
URL(endpoint): /v1/answer/{answerId}/comments/{commentId}

<!-- 요청 시 method 입니다. HTTP method를 기준으로 합니다. -->
method: POST

<!-- 요청 시 기능명세 코드 입니다. HTTP method를 기준으로 합니다. -->
기능명세 코드: C-DET-11

## 요청시 데이터

<!-- 요청시에 Path Parameter 혹은 Request Parameter가 필요한 지에 대해 체크합니다. -->
<!-- 만약 해당되는 데이터가 없다면 표를 비워주세요. 제목을 포함한 항목을 지우시면 안됩니다.-->
Path Parameter : <input type="checkbox" value="Path Parameter">

Request Body : <input type="checkbox" value="Request Body" checked>

Query Parameter : <input type="checkbox" value="Query Parameter" checked>


### Request Body 

<!-- 요청 시 데이터에 대해 명시하는 테이블입니다. -->
<!-- Key, Data-Type, Description, Condition 순으로 작성해주세요. -->
<!-- Key는 요청 시 데이터의 Key를,
    Data-Type은 요청 시 데이터의 Data-Type을,
    Description은 요청 시 데이터의 설명을,
    Condition은 요청 시 데이터의 조건을 명시해주세요. -->
| Key | Data-Type | Description | Condition |
| --- | --- | --- | --- |
| password | string | 답글에 댓글을 작성할 때 작성자가 본인 확인을 위해 입력한 비밀번호 | |

### Query Parameter 

<!-- 요청 시 데이터에 대해 명시하는 테이블입니다. -->
<!-- Key, Data-Type, Description, Condition 순으로 작성해주세요. -->
<!-- Key는 요청 시 데이터의 Key를,
    Data-Type은 요청 시 데이터의 Data-Type을,
    Description은 요청 시 데이터의 설명을,
    Condition은 요청 시 데이터의 조건을 명시해주세요. -->
| Key | Data-Type | Description | Condition |
| --- | --- | --- | --- |
| answerId | int | 수정할 댓글이 달린 답글의 id | |
| commentId | int | 수정할 댓글의 id | |

### 예시

```json
// 아래는 요청할 때의 Path Parameter 데이터 예시입니다.
{
    // 없음
}

// 아래는 요청할 때의 Request Body 데이터 예시입니다.
{
    "password": "1234aaaa"
}

// 아래는 요청할 때의 Query Parameter 데이터 예시입니다.
{
    "answerId": 1,
    "commentId": 1
}
```

***

## 응답시 데이터

### 성공

```json
// 아래의 응답에 대한 요청은 위의 요청시 데이터 예시를 참고해주세요.
// 요청시 Path Parameter와 Request Body에 따라 응답 데이터가 달라집니다.

// 응답시 HTTP Status Code는 아래와 같습니다.
STATUS CODE: 204 NO CONTENT

// 아래는 응답시 전달될 데이터 예시입니다.
{
    "message" : "comment on answer deleted successfully"
}
```

### 실패

#### answerId에 해당하는 답글이 존재하지 않을 때

```json
// 응답시 HTTP Status Code는 아래와 같습니다.
STATUS CODE: 404 NOT FOUND

// 아래는 응답시 전달될 데이터 예시입니다.
{
    "message" : "answer not found"
}
```

#### commentId에 해당하는 댓글이 존재하지 않을 때

```json
// 응답시 HTTP Status Code는 아래와 같습니다.
STATUS CODE: 404 NOT FOUND

// 아래는 응답시 전달될 데이터 예시입니다.
{
    "message" : "comment on answer not found"
}
```
<!-- 실패 사유가 여러가지 존재하여서 2개 이상의 실패 응답을 정의할 때에는 복수의 ### [실패사유] 탭을 만들어 주세요.-->