Foundry 是目前最强大的 Rust 编写的智能合约开发框架，专为以太坊及 EVM 兼容链设计
Foundry

forge 
forge init <project-name>	初始化项目
forge build	编译项目（生成 ABI、字节码）
forge test	运行测试（支持 assert, expectRevert, ffi 等）
forge test -vvv	显示日志和调用栈（用于调试）
forge create	部署合约（支持多网络）
forge snapshot	生成测试覆盖率快照
forge remappings	查看路径映射


cast 
cast call <addr> "balanceOf(address)" <user>	调用 view 函数
cast send --private-key <key> <to> <data>	发送交易
cast balance <address>	查询 ETH 余额
cast block latest	获取最新区块
cast abi-encode	手动编码函数调用数据

anvil 
本地测试网节点（类似 Hardhat Network）
启动一个本地 EVM 节点（类似 Hardhat Network）,预充值 20 个带 ETH 的测试账户,支持 fork 主网状态,可作为开发和测试的后端节点
高级用法：分叉主网 anvil --fork-url https://eth-mainnet.alchemyapi.io/v2/YOUR_KEY


my-foundry-project/
├── src/               # 合约源码
├── test/              # 测试用例（Solidity 编写）
├── script/            # 脚本（用于部署，Solidity 编写）
├── foundry.toml       # 配置文件（网络、编译器版本等）
├── remappings.txt     # 依赖路径映射（如 OpenZeppelin）
└── lib/               # 依赖库（通过 `forge install` 安装）


Foundry 优势总结

高性能	Rust 编写，编译和测试速度极快
无 Node.js 依赖	不依赖 npm、JavaScript，减少攻击面
安全性高	测试用 Solidity 写，更贴近合约逻辑
强大测试功能	支持 Fuzz、Invariant、Snapshot 测试
易于集成 CI/CD	单二进制安装，适合 Docker 和 GitHub Actions