### 相关地址
	- ```csharp
	  /*启动信号 M20*/
	  busTcpClient.WriteCoil("2068", false)
	  
	  /*关闭气缸 M30*/
	  busTcpClient.WriteCoil("2078", true)
	  
	  /*读取面板温度 D272*/
	  busTcpClient.ReadPlcData<float>("4368")
	  
	  /*读取环境温度 D276*/
	  busTcpClient.ReadPlcData<float>("4372")
	  
	  /*读取电压 D876*/
	  busTcpClient.ReadPlcData<float>("4972")
	  
	  /*检测反馈D28 0 NG， 1 OK，2 重新检测*/
	  busTcpClient.Write("4376", 2)
	  
	  /*结束信号 M35*/
	  busTcpClient.WriteCoil("2083", true);
	  busTcpClient.WriteCoil("2078", false);
	  
	  ```