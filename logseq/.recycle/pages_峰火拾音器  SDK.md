- 提供的 SDK API接口和测试例子Demo ，具体运行流程如下：
  1、调用 TSDK_Init 函数初始化 SDK，并注册事件回调函数 OnTzlSdkCallback 。
  2、由广播设备主动向当前程序注册，通过 CB_Event_TermRegister 事件接收注册信息，注册信息 通过结构体 TSdkEventTermRegister 缓存在缓存列表 m_TermList 中，收到注册消息时如果设备 ID 在缓存列表 m_TermList 中不存在则添加到 m_TermList 中，如设备 ID 在 m_TermList 中存在，则更新 m_TermList 中的注册信息。
  3、通过 TSDK_SetupGroup 函数将缓存列表 m_TermList 中的设备创建广播分组，分组号 g_MyGroupNum。
  4、通过 TSDK_StartBroadMp3 函数 开启分组 g_MyGroupNum 广播MP3。
  5、通过 TSDK_BroadMp3File 函数 在分组 g_MyGroupNum 上广播MP3文件。
  6、通过 TSDK_StopBroadMp3 函数 停止分组 g_MyGroupNum 广播MP3文件。
  7、调用 TSDK_DeInit 注销 SDK。