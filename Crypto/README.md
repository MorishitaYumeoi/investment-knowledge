## 1 以太坊研发进展  
  
### 1-1 以太坊基金会博客  

### 1-2 以太坊技术路线图  

## 2 Clarity法案进展

## 3 阅读资料    

### 3-1 ePBS 拆分 Slot 截止时间，为以太坊扩容腾出空间(精读): https://mp.weixin.qq.com/s/jiaWju2GQPcydZ4R629w4w  
&emsp;&emsp;ePBS 的核心思想是将区块的共识部分与执行部分分离，使它们成为具有各自截止时间的独立网络对象。当前，在 4 秒认证截止时间下，如果提议者在 Slot 开始后 1-2 秒发布区块，区块和 blob 可能在 Slot 开始后 2-3 秒到达。这给节点仅剩 1-2 秒下载和验证所有内容。  
&emsp;&emsp;有了 ePBS，假设信标区块截止时间为 3 秒，有效载荷截止时间为 6 秒，blob 截止时间接近 Slot 末尾。有效载荷现在有 6 秒下载和验证，这让节点有更多时间在下一个 Slot 之前接收并执行它。Blob 现在有大约 9 秒在网络中传播。  
&emsp;&emsp;这就是以太坊能够以大幅扩容为目标而不增加去中心化压力的主要原因。具体的截止时间仍可能变化，但方向明确：以太坊开始将 12 秒 Slot 的更多部分用于有效的扩容工作。  

<img width="1080" height="608" alt="IMG_1223" src="https://github.com/user-attachments/assets/3be4ffb2-1b8f-463c-a7d8-a8c9beb3ce53" />

