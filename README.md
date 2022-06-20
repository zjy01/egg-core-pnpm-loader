# egg-core-pnpm-loader
当基于egg封装一个带scope的应用框架时，如`@zjy/egg-pnpm-bug`, 使用 pnpm 安装，会无法加载应用框架内的插件

egg: 2.36.0
egg-core: 4.23.0

## 快速复现
使用pnpm 进行安装
```bash
pnpm install
```

启动
```bash
pnpm run dev
```

报错
```bash
/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg-cluster@1.27.1/node_modules/egg-cluster/lib/agent_worker.js:32
  throw err;
  ^

Error: Can not find plugin egg-validate in "/Users/carvenzhang/Workspace/bug/node_modules, /Users/carvenzhang/Workspace/bug/node_modules/.pnpm/@zjy+egg-pnpm-bug@0.0.1/node_modules/@zjy/egg-pnpm-bug/node_modules, /Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg@2.36.0/node_modules/egg/node_modules, /Users/carvenzhang/Workspace/bug/node_modules/.pnpm/@zjy+egg-pnpm-bug@0.0.1/node_modules/@zjy, /Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg@2.36.0/node_modules"
    at AgentWorkerLoader.getPluginPath (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg-core@4.23.0/node_modules/egg-core/lib/loader/mixin/plugin.js:369:11)
    at AgentWorkerLoader.loadPlugin (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg-core@4.23.0/node_modules/egg-core/lib/loader/mixin/plugin.js:108:26)
    at AgentWorkerLoader.loadConfig (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg@2.36.0/node_modules/egg/lib/loader/agent_worker_loader.js:15:10)
    at new EggApplication (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg@2.36.0/node_modules/egg/lib/egg.js:55:17)
    at new Agent (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg@2.36.0/node_modules/egg/lib/agent.js:22:5)
    at new Agent (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/@zjy+egg-pnpm-bug@0.0.1/node_modules/@zjy/egg-pnpm-bug/lib/framework.js:13:1)
    at Object.<anonymous> (/Users/carvenzhang/Workspace/bug/node_modules/.pnpm/egg-cluster@1.27.1/node_modules/egg-cluster/lib/agent_worker.js:29:11)
    at Module._compile (internal/modules/cjs/loader.js:1085:14)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1114:10)
    at Module.load (internal/modules/cjs/loader.js:950:32)
```