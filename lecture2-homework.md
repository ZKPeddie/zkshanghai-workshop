# 第2课 课后作业


## 第1题 转换为bit位 Num2Bits

```
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

```






## 第2题 判零 IsZero
```
pragma circom 2.1.4;

include "circomlib/poseidon.circom";

template Example () {
    signal input in;
    signal input out;
    
    signal temp;
    temp <-- in * (in - 1);

    temp === out;
}

component main = Example();

/* INPUT = {
    "in": "1",
    "out": "1"
} */
```






## 第3题 相等 IsEqual
```
pragma circom 2.1.4;

include "circomlib/poseidon.circom";

template Example () {
    signal input in[2];
    signal output out;

    signal temp;

    temp <-- in[0] - in[1];
    
    out <== temp * (temp -1);
}

component main = Example();

/* INPUT = {
    "in": ["1","1"]
} */
```






## 第4题 选择器 Selector
```
pragma circom 2.1.4;

include "circomlib/poseidon.circom";

template Example () {
    signal input in[3];
    signal input index;
    signal output out;

    signal temp;
    temp <-- in[index];

    out <== temp;
}

component main = Example();

/* INPUT = {
    "in": ["1","2","3"],
    "index": "1",
    "out": "2"
} */
```






## 第5题 判负 IsNegative
```
pragma circom 2.1.4;

include "circomlib/poseidon.circom";

template Example () {
    signal input in;
    signal output out;

}

component main = Example();

/* INPUT = {
    "in": "1",
    "out": "0"
} */
```






## 第6题 少于 LessThan
```
pragma circom 2.1.4;

include "circomlib/poseidon.circom";

template Example () {
    signal input in;
    signal output out;

}

component main = Example();

/* INPUT = {
    "in": "1",
    "out": "0"
} */
```






## 第7题 整数除法 IntegerDivide
```
pragma circom 2.1.4;

include "circomlib/poseidon.circom";

template Example () {
    signal input in;
    signal output out;

}

component main = Example();

/* INPUT = {
    "in": "1",
    "out": "0"
} */
```







