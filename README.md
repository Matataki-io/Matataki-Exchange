## uniswap exchange魔改
- [ ] uniswap中ETH修改为我们的稳定币ECny
- [ ] 【Fan票】erc20支持和ECny交易
- [ ] 【Fan票】支持添加到交易所
- [ ] 创建交易所权限（控制哪些币能添加到我们的交易所）
- [ ] 【Fan票】支持使用ECny定价，通过接口可以获得添加这些【Fan票】以及价格（ECny价格）
- [ ] 后端同步【Fan票】的数据

## ECny
- [ ] 发币/交易权限（owner）
- [ ] 后端收到用户付款将对应ECny tranfer到用户托管的以太坊账号

## Fan票
见 https://hackmd.io/wI6hYAzHSg2wFSu4dkM-Ag


## uniswap exchange部署到rinkeby testnet说明
### 合约部署
项目地址：https://github.com/Uniswap/contracts-vyper
1. 项目clone，设置好python环境，详情见：https://github.com/Uniswap/contracts-vyper/blob/master/README.md
2. use vyper uniswap_factory.vy to get bytecode and vyper -f abi uniswap_factory.vy to get the ABI. Do the same for uniswap_exchange.vy
3. Deploy both contracts separately from their bytecode using https://mycrypto.com/contracts/deploy
4. Use factory ABI (step 2) + factory address (step 3) and https://mycrypto.com/contracts/interact to open an interface to the uniswap factory
5. call initializeFactory(templateAddress) and pass in the address of the deployed uniswap_exchange.vy contract (step 2)

### 前端部署
项目地址：https://github.com/Uniswap/uniswap-frontend
1. 修改env.local
2. 修改src/constants/index.js
3. npm run build


附件图片：
创建交易所![图片](/api/project/93154/files/2665881/imagePreview)
