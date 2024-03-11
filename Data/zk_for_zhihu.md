# 一、零知识证明相关的定义和例子
简明非交互式零知识证明zkSNARKs(zero-knowledge succinct non-interactive argument of knowledge)是一种具备多种性质的证明系统。本部分将从一个简单的例子引出proof的概念（argument与proof仅有细微区别，argument额外要求prover的计算能力受限），并给出对应的completeness、soundness、knowledge soundness、zero-knowledge等性质的定义，最后以二次剩余为例介绍一个证明系统。
## 1.1、直观理解proof
![图片1](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片1.png"proof图片1")
## 1.2、proof system的相关定义
![图片3](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片3.png"proof system图片3")
**定义：** 如果 <img src="https://www.zhihu.com/equation?tex=(P,V)" alt="(P,V)" class="ee_img tr_noresize" eeimg="1"> 满足下面两条性质，且 <img src="https://www.zhihu.com/equation?tex=V" alt="V" class="ee_img tr_noresize" eeimg="1"> 是PPT的算法，则称 <img src="https://www.zhihu.com/equation?tex=(P,V)" alt="(P,V)" class="ee_img tr_noresize" eeimg="1"> 是针对语言 <img src="https://www.zhihu.com/equation?tex=L" alt="L" class="ee_img tr_noresize" eeimg="1"> (可简单理解为命题成立的集合)的proof system：
+ Completeness：如果 <img src="https://www.zhihu.com/equation?tex=T\in L" alt="T\in L" class="ee_img tr_noresize" eeimg="1"> ，则有 <img src="https://www.zhihu.com/equation?tex=Pr((P,V)(T)=accept)=1" alt="Pr((P,V)(T)=accept)=1" class="ee_img tr_noresize" eeimg="1"> 
+ Soundness：如果 <img src="https://www.zhihu.com/equation?tex=T\notin L" alt="T\notin L" class="ee_img tr_noresize" eeimg="1"> ，则对任意 <img src="https://www.zhihu.com/equation?tex=P^*" alt="P^*" class="ee_img tr_noresize" eeimg="1">  有 <img src="https://www.zhihu.com/equation?tex=Pr((P^*,V)(T)=accept)=negl(|T|)" alt="Pr((P^*,V)(T)=accept)=negl(|T|)" class="ee_img tr_noresize" eeimg="1"> 

**定义：** 对于多项式时间的关系 <img src="https://www.zhihu.com/equation?tex=R" alt="R" class="ee_img tr_noresize" eeimg="1"> 考虑 <img src="https://www.zhihu.com/equation?tex=L_R=\{x|\exists w,\ s.t.\ R(x,w)=accept \}" alt="L_R=\{x|\exists w,\ s.t.\ R(x,w)=accept \}" class="ee_img tr_noresize" eeimg="1"> 
![图片5](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片5.png"knowledge soundness图片5")
![图片7](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片7.png"zero-knowledge图片7")
## 1.3、以二次剩余为例
![图片9](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片9.png"二次剩余图片9")
![图片11](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片11.png"rewinding图片11")
![图片13](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片13.png"simulator图片13")
## 1.4、零知识证明的相关应用

# 二、zkSNARKs的构造

## 2.1、命题的描述方法与zkSNARKs的构造原理
![图片14](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片14.png"C1RS图片14")
![图片16](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片16.png"图片16")
![图片17](https://raw.githubusercontent.com/lcc1999/Markdown4Zhihu/master/Data/zk/图片17.png"图片17")
## 2.2、polynomial commitment system
## 2.3、


|  | proving time | verification time | proof size | setup assumption |

|-------|-------|-------|-------|-------|

| Groth16（2016） | O(\|C\| log \|C\|) | O(1)(≈ 3 ms) | O(1)(≈ 200 B) | cicuit-specific trusted setup |

| Bulletproofs（2018） | O(\|C\| log \|C\|) | O(\|C\|)(≈ 3 s) | O(log \|C\|)(≈ 1.5KB) | transparent setup |

| STARK（2018） | O(\|C\| log \|C\|) | O(log² \|C\|)(≈ 10 ms) | O(log² \|C\|)(≈ 100 KB) | transparent setup |

| Plonk（2020） | O(\|C\| log \|C\|) | O(1)(≈ 3 ms) | O(1)(≈ 400 B) | universal trusted setup |