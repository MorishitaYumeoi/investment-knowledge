## 1 以太坊研发进展  
  
### 1-1 以太坊基金会博客  

### 1-2 以太坊技术路线图  

## 2 Clarity法案进展

## 3 阅读资料    

### 3-1 ePBS 拆分 Slot 截止时间，为以太坊扩容腾出空间(精读): https://mp.weixin.qq.com/s/jiaWju2GQPcydZ4R629w4w  

&emsp;&emsp;目前以太坊有 12 秒的 Slot，但并非全部 12 秒都用于吞吐量。认证截止时间是 Slot 的第 4 秒。这意味着验证者需要在此之前下载并验证所有内容。提议者还需选择何时发布其区块，在争取更多时间获取 MEV 与承担错过截止时间的风险之间权衡。等待更久让提议者有更多时间打包有价值的交易，但增加了验证者无法及时接收和验证区块的风险。4 秒之后，Slot 剩余的 8 秒主要用于共识投票聚合，而不是用于提高执行吞吐量或 blob 容量。下图中，区块到达时间分布显示为什么 Slot 初期的窗口已经很紧张。  
<img width="1080" height="587" alt="IMG_1224" src="https://github.com/user-attachments/assets/e622296d-481c-4d12-a35d-a6e12cdee45e" />  

&emsp;&emsp;对 Slot 时间至关重要的有三项主要数据：共识区块、执行有效载荷和 blob。  
&emsp;&emsp;与执行有效载荷和 blob 数据相比，共识区块很小。在主网上，它通常仅占节点在 Slot 内需要下载数据的一小部分。同时，用户交易并不在共识区块本身中。它们位于执行有效载荷和 blob 中，而这些是需要更多时间下载和验证的对象。下图中，大多数下载内容是执行有效载荷，而非共识数据。  
<img width="1080" height="768" alt="IMG_1225" src="https://github.com/user-attachments/assets/9502a5f9-aacd-4489-b169-6b4296259222" />  

&emsp;&emsp;ePBS 的核心思想是将区块的共识部分与执行部分分离，使它们成为具有各自截止时间的独立网络对象。  
&emsp;&emsp;当前，在 4 秒认证截止时间下，如果提议者在 Slot 开始后 1-2 秒发布区块，区块和 blob 可能在 Slot 开始后 2-3 秒到达。这给节点仅剩 1-2 秒下载和验证所有内容。  
&emsp;&emsp;有了 ePBS，假设信标区块截止时间为 3 秒，有效载荷截止时间为 6 秒，blob 截止时间接近 Slot 末尾。有效载荷现在有 6 秒下载和验证，这让节点有更多时间在下一个 Slot 之前接收并执行它。Blob 现在有大约 9 秒在网络中传播。  
&emsp;&emsp;这就是以太坊能够以大幅扩容为目标而不增加去中心化压力的主要原因。具体的截止时间仍可能变化，但方向明确：以太坊开始将 12 秒 Slot 的更多部分用于有效的扩容工作。  
<img width="1080" height="608" alt="IMG_1223" src="https://github.com/user-attachments/assets/3be4ffb2-1b8f-463c-a7d8-a8c9beb3ce53" />  

