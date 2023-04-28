# 第2课 课后作业

## 第1题 转换为bit位 Num2Bits

`
pragma circom 2.1.4;
 
include "circomlib/poseidon.circom";
 
template Example () {
    signal input in;
     signal input b[4];
 
    in === b[0]*8 + b[1]*4 + b[2]*2 + b[3];
 
    var acc;
    for(var i=0; i<4; i++){
        acc += b[i]*(2**(3-i));
    }
 
    in === acc;
 
    for(var i=0; i<4; i++){
        b[i]*(1-b[i]) === 0;
    }
 
}
 
component main = Example();
 
/* INPUT = {
    "in": "1",
    "b": ["1","0","1","1"]
} */

`






## 第2题 判零 IsZero
`

`





