# 代码阅读
## ERC20

#### 注意：  
        1.有一些ERC20合约没有按照标准来，可能就没有返回值
        2.接口实现是可以选择的
        3.转账无法携带额外信息，没有转账回调（依靠：授权、授权、授权；误入合约会被锁死）

 #### 整体梳理       
interface IERC20 {
 //发行总量
 function totalSupply() external view returns (uint256); 
 //获得account账号余额
 function balanceOf(address account) external view returns (uint256); 
 //转账发起人转到to地址
 function transfer(address to, uint256 amount) external returns (bool); 
 //owner给spender授权数量为uint256
 function allowance(address owner, address spender) external view returns (uint256); 
 //
 function approve(address spender, uint256 amount) external returns (bool); 
 //from地址转账到to地址，数量为amount
 function transferFrom(address from, address to, uint256 amount) external returns (bool); 
 event Transfer(address indexed from, address indexed to, uint256 value); 
 event Approval(address indexed owner, address indexed spender, uint256 value); 
}


## ERC777
#### 注意： 
            1.send(dest,value,data)可以携带转账信息，dest为目标地址
#### 整体梳理
