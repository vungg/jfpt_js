# jfpt_js
技服管理平台结算模块

1.维修
  
2.安装
&nbsp;&nbsp;1,Dps Type,Zone,Svc Request ID,Qty这几列不能为空<br/>
&nbsp;&nbsp;2,通过Dps Type算出fwz_Pricing，(Total Hrs忽略)<br/>
&nbsp;&nbsp;ProDeploy_Completed:ProDeploy Amount=Pricing*Qty<br/>
&nbsp;&nbsp;3.3个zone值表:EIS Completed,EIS ProDeploy_Completed,EDT Completed<br/>
&nbsp;&nbsp; 4.Additional Charge通过上传excel修改<br/>
&nbsp;&nbsp;&nbsp;&nbsp;扣费补贴管理：添加扣补类型：维修，安装，备件（默认维修)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;站结费：分三张表展示：维修，安装，备件<br/>
&nbsp;&nbsp;5.计算站结费时, 安装和备件要算出不含税价格(总价/1.06)（保留两位小数）<br/>
&nbsp;&nbsp;6.站结费：每个月有政策补贴(固定值，可能会有修改)(可以放在考核系数里)(都可以修改)（政策补贴参与考核不确定）<br/>
&nbsp;&nbsp;7.cancel 每单固定价格(可以加Additional Charge)<br/>

3.备件
&nbsp;&nbsp;1.RMA(3BRTD RMA和在一起)对服务站所有结费：对厂商结11则对服务站结10，对厂商结0则对服务站结0，BASE CITY作为deptno<br/>
&nbsp;&nbsp;2.good part：dlp_base_city作为 deptno<br/>
&nbsp;&nbsp;&nbsp;&nbsp;DL,XA,FZ,SY给11,其余给7,对厂商给0的结0<br/>
&nbsp;&nbsp;&nbsp;&nbsp;武汉:当年当量<84000 给11,<120000给9，>120000给7<br/>
&nbsp;&nbsp;3,billing:根据Billing SLA得出SLA cost<br/>
&nbsp;&nbsp;&nbsp;&nbsp;zone:有对应zone值表<br/>
&nbsp;&nbsp;&nbsp;&nbsp;DLP Base City作为deptno<br/>
&nbsp;&nbsp;&nbsp;&nbsp;special charge通过上传excel修改<br/>
&nbsp;&nbsp;&nbsp;&nbsp;站结费添加加班统计费用，ADY<br/>
