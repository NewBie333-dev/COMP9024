## 用二进制运算来判断这个状态是否访问过
```
typedef enum {
    // This position has not been visited yet
    NOT_VISITED = 0,
    // go to visit the adjacent rightward position
    TO_RIGHT = 1,
    // go to visit the adjacent downward position
    TO_DOWN = 2,
    // go to visit the adjacent leftward position
    TO_LEFT = 4,
    // go to visit the adjacent upward position
    TO_UP = 8,
    // We have explored all four directions of the current position, 
    FINISHED = 0x0F,

} PositionState;
```
结合
`pCurPos->state |= nextState;// pCurPos->state = pCurPos->state | nextState;`