#命令
##TPA
/tpa <to/here> <player> 向目标玩家发起传送请求，其中to为传送到目标玩家位置，here为将目标玩家传送到你的位置
/tpa gui 打开GUI
/tpa ac/de/cancel/toggle
ac 同意请求
de 拒绝请求
cancel 取消你发送的请求
toggle 改变你的tpa接受状态，tpa接受状态指是否允许别人向你发送请求

/back 回到死亡点
/suicide 自杀

/warp go/add/ls/del/gui /warp go <传送点名> 到传送点
/warp ls 查看所有传送点
/warp gui 打开GUI
/warp add <传送点名> 添加传送点(需要OP)
/warp del <传送点名> 删除传送点(需要OP)

/home go/add/ls/del/gui /home go <家名> 传送回家
/home ls 查看所有家
/home gui 打开GUI
/home add <家名> 添加一个家
/home del <家名> 删除一个家

其中，OP可以通过/homeas指令以玩家身份执行home命令，从而查看玩家家或者删除玩家家
例如:/homeas steve ls
/homeas steve del jia
##Land
/land a/b/exit ("/"为"或"的意思)
/land a 为进入选点a模式，此时点地选点a
/land b 为进入选点b模式，此时点地选点b
选完两个点就可以输入/land buy，退出选点请输入/land exit

/land buy/sell/info/gui
buy 购买
sell 卖出你脚下的领地
info 查询脚下领地信息
gui 领地gui

/land trust/untrust/give
/land trust <玩家名> 信任玩家，玩家拥有除更改被信任人和出售领地以外的所有权限
/land untrust <玩家名> 取消信任玩家
/land give <玩家名> 转让领地主人权限(目标玩家必须在线)
/land perm <数字> 更改脚下领地权限掩码

0: NOTHING 无权限(默认)
1: PERM_INTERWITHACTOR 和生物互动，比如喂食，骑马，让宠物坐下
2: PERM_USE 空手点击
4: PERM_ATK 攻击实体
8: PERM_BUILD 建造
16: PERM_DESTROY 破坏

默认的land perm为0，表示陌生人没有被授予任何默认权限
如果想给陌生人权限，请更改perm值，perm值为权限值之和
例如: 允许领地内陌生人攻击实体和空手点击
根据land perm计算得出: 2(空手点击)+4(攻击实体)=6
则输入: /land perm 6

注: OP拥有所有领地的所有权限，同时OP买领地不扣钱
##Money
/money query/hist [玩家名]
query 查自己的余额或者指定玩家的
hist 查自己的历史或者指定玩家的
例如:/money query
/money hist steve

pay/set/add/reduce /money pay <玩家名> <数目> 向指定玩家转账若干的钱
/money set <玩家名> <数目> 设置目标玩家的钱数(仅OP可用)
/money add <玩家名> <数目> 为目标玩家增加若干金钱
/money reduce <玩家名> <数目> 从目标玩家的账户中拿走若干的钱

这里的目标为玩家名，不区分大小写

/money_op purge [秒] 清除多少秒之前的记录，不填写为清除全部
/money_op pay/set/add/reduce

注意:/money_op reduce存在返回状态，可以联动链命令方块使用
