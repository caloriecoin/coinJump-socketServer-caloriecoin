# skip-game-server
CalorieCoin battleMode web socket Game Server


## Event Architecture

### on
 - _enterQueue (socket)_  
  **Request Data**
    ```javascript
    {
    nickname: String // nickname of User
    }
    ```
 - _jumping (socket)_  
  **Request Data(NONE)**

### emit
 - _LOADING_GAME_  
  **Response Data**
    ```javascript
    {
      targetInfo: User // Transmit opposite User`s information    }
    ```
 - _START_GAME_  
  **Response Data**
    ```javascript
    {
      // This is just for start alarm , there is not special Event info
    }
    ```
 - _GAME_STATUS_  
   **Response Data**
    ```javascript
    {
      myJump: Number,         //  My jumps count
      targetJump: Number,     // opposite jumps count
    }
    ```
 - _END_GAME_  
  **Response Data**
    ```javascript
    {
     winner: String,           //  Winner Nickname (승리자 닉네임)
     loser: String,            //  Looser Nickname (패배자 닉네임)
     myScore: Number,          //  My Score (나의 점수)
     targetScore: Number,      // opposite Score (상대 점수) 
     draw: Boolean             // Checking for a draw

    }
    ```

## Installation
```sh
$ npm install
$ npm start
```
