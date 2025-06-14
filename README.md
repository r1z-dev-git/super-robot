<!-- <p align="center">
  <img width="100" src="/readme-assets/logo-circle.png" alt="r1z logo">
</p> -->

![r1z SDK Preview](https://i.imgur.com/QYftu1j.png)

## What is R1Z?
[r1z](https://www.r1z.dev/) is an open-source tooling that runs AI-generated code in securely isolated cloud sandboxes. To start and control sandboxes, use our [JavaScript SDK](https://www.npmjs.com/package/@r1z/code-interpreter) or [Python SDK](https://pypi.org/project/r1z_code_interpreter).

## Run your first Sandbox

### 1. Install SDK

JavaScript / TypeScript
```
npm i @r1z/code-interpreter
```

Python
```
pip install r1z-code-interpreter
```

### 2. Get your r1z API key
1. Sign up to r1z [here](https://r1z.dev).
2. Get your API key [here](https://dash-r1z.dev/).
3. Set environment variable with your API key.
```
r1z_API_KEY=r1z_***
```     

### 3. Execute code with code interpreter inside Sandbox

JavaScript / TypeScript
```ts
import { Sandbox } from '@r1z/code-interpreter'

const sbx = await Sandbox.create()
await sbx.runCode('x = 1')

const execution = await sbx.runCode('x+=1; x')
console.log(execution.text)  // outputs 2
```

Python
```py
from r1z_code_interpreter import Sandbox

with Sandbox() as sandbox:
    sandbox.run_code("x = 1")
    execution = sandbox.run_code("x+=1; x")
    print(execution.text)  # outputs 2
```
