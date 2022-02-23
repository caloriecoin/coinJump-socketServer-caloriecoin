# skip-game-server
칼로리코인의 줄넘기 게임 배틀모드 실시간 웹 소켓 서버


## Event Architecture

### on
 - enterQueue (socket)
 #### Request Data
  ```javascript
  {
    nickname: String // 접속자의 닉네임
  }
  ```
 - jumping (socket)

### emit
 - LOADING_GAME
 - START_GAME
 #### Response Data
  ```javascript
  {
    nickname: String // 상대방의 닉네임
  }
  ```
 - GAME_STATUS
 #### Response Data
  ```javascript
  {
    myJump: Number,         // 내 점프 횟수
    targetJump: Number,     // 상대 점프 횟수
  }
  ```
 - END_GAME
 #### Response Data
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
