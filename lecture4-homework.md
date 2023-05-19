# 第4课 课后作业

## 第1题 SkToPk
```
pragma circom 2.1.4;
 
include "circomlib/poseidon.circom";
 
template SkToPk () {
    signal input sk;
    signal output pk;
 
    component p;
    p = Poseidon(1);
    p.inputs[0] <== sk;
    pk <== p.out;
}
 
component main = SkToPk();
 
/* INPUT = {
    "sk": "5"
} */
```




## 第2题 Sign
```
pragma circom 2.1.4;
 
include "circomlib/poseidon.circom";
 
template SkToPk () {
    signal input sk;
    signal output pk;
 
    component p;
    p = Poseidon(1);
    p.inputs[0] <== sk;
    pk <== p.out;
}
 
template Sign () {
    signal input sk;
    signal input pk;
    signal input m;
 
    component s2p;
    s2p = SkToPk();
    s2p.sk <== sk;
    s2p.pk === pk;
 
}
 
component main {public [pk, m]}= Sign();
 
/* INPUT = {
    "sk": "5",
    "pk": "19065150524771031435284970883882288895168425523179566388456001105768498065277",
    "m": "1"
} */
```
