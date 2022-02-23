# skip-game-server
칼로리코인의 줄넘기 게임 배틀모드 실시간 웹 소켓 서버


## Event Architecture

### on
 - _enterQueue (socket)_  
  **Request Data**
    ```javascript
    {
    nickname: String // 접속자의 닉네임
    }
    ```
 - _jumping (socket)_  
  **Request Data(NONE)**

### emit
 - _LOADING_GAME_  
  **Response Data**
    ```javascript
    {
      targetInfo: User // 상대방의 정보 전달
    }
    ```
 - _START_GAME_  
  **Response Data**
    ```javascript
    {
      // 시작 알림 용 이벤트로 별도 정보 없음
    }
    ```
 - _GAME_STATUS_  
   **Response Data**
    ```javascript
    {
      myJump: Number,         // 내 점프 횟수
      targetJump: Number,     // 상대 점프 횟수
    }
    ```
 - _END_GAME_  
  **Response Data**
    ```javascript
    {
     winner: String,           // 승리자 닉네임
     loser: String,            // 패배자 닉네임
     myScore: Number,          // 나의 점수
     targetScore: Number,      // 상대 점수
     draw: Boolean             // 무승부 여부 확인
    }
    ```

## Installation
```sh
$ npm install
$ npm start
```
