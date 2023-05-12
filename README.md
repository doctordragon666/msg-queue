# msg-queue

该项目是一个使用 Linux 消息队列的示例，它可以实现进程间通信。

## 安装

1. 克隆本仓库到本地

   ```
   git clone https://github.com/doctordragon666/msg-queue.git
   ```

2. 进入项目目录并执行 make 命令

   ```
   cd msg-queue
   make
   ```

3. 编译完成后，在 `bin` 目录下可以找到可执行文件 `sender` 和 `receiver`。

## 用法

### 启动接收方进程

在一个终端窗口中运行以下命令以启动接收方进程：

```
./bin/receiver
```

该进程会一直监听消息队列，如果有消息，则将其输出到控制台。

### 启动发送方进程

在另一个终端窗口中运行以下命令以启动发送方进程：

```
./bin/sender [message]
```

其中 `[message]` 是要发送的消息内容。

发送方进程会向消息队列发送消息，并马上退出。如果没有指定消息内容，则默认发送字符串 "Hello, World!"。

## 示例

1. 启动接收方进程。

   ```
   ./bin/receiver
   ```

   输出如下：

   ```
   Start receiver process...
   ```

2. 启动发送方进程，并发送消息 "Hello, World!"。

   ```
   ./bin/sender "Hello, World!"
   ```

   输出如下：

   ```
   Send message "Hello, World!"...
   ```

   接收方进程的输出如下：

   ```
   Received message: "Hello, World!"
   ```

## 注意事项

- 发送方进程只会发送一条消息，并马上退出。
- 尽管使用了消息队列来实现进程间通信，但是该示例并没有处理消息队列溢出的情况，因此在实际应用中需要进行改进。

## 参考资料

- 《Unix 环境高级编程》（第 3 版），W. Richard Stevens、Stephen A. Rago 著，张立坤、潘爱民、徐向民、李玮等译，中国电力出版社，2014 年。
