# ubuntu下配置VScode编译C++

- **官网下载最新版VScode https://code.visualstudio.com/docs/?dv=linux64_deb**

- **安装VScode**

  ```shell
  sudo dpkg -i code_*******_amd64.deb
  ```

- **进入VScode安装C++插件**

- **安装 `gcc g++ gdb`**

  ```shell
  sudo apt-get update
  sudo apt-get install gcc
  sudo apt-get install g++
  sudo apt-get install gdb
  ```

- **创建新的cpp文件，编写代码**

- **生成laubch.json  Run -> Add Configuration -> C++(GDB/LLDB) -> Run -> Add Configuration ->[]中选择 `C/C++:(gdb)Launch`**

  ```shell
  {
      // Use IntelliSense to learn about possible attributes.
      // Hover to view descriptions of existing attributes.
      // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
      "version": "0.2.0",
      "configurations": [
          {
              "name": "(gdb) Launch",
              "type": "cppdbg",
              "request": "launch",
              "program": "enter program name, for example ${workspaceFolder}/a.out",
              "args": [],
              "stopAtEntry": false,
              "cwd": "${fileDirname}",
              "environment": [],
              "externalConsole": false,
              "MIMode": "gdb",
              "setupCommands": [
                  {
                      "description": "Enable pretty-printing for gdb",
                      "text": "-enable-pretty-printing",
                      "ignoreFailures": true
                  },
                  {
                      "description":  "Set Disassembly Flavor to Intel",
                      "text": "-gdb-set disassembly-flavor intel",
                      "ignoreFailures": true
                  }
              ]
          }
  
      ]
  }
  ```

- **生成 tasks.json Terminal ->Configure Tasks... -> C/C++:g++ build active file**

  ```shell
  {
  	"version": "2.0.0",
  	"tasks": [
  		{
  			"type": "cppbuild",
  			"label": "C/C++: g++ build active file",
  			"command": "/usr/bin/g++",
  			"args": [
  				"-fdiagnostics-color=always",
  				"-g",
  				"${file}",
  				"-o",
  				"${fileDirname}/${fileBasenameNoExtension}"
  			],
  			"options": {
  				"cwd": "${fileDirname}"
  			},
  			"problemMatcher": [
  				"$gcc"
  			],
  			"group": "build",
  			"detail": "compiler: /usr/bin/g++"
  		}
  	]
  }
  ```

- **修改launch.json文件中的program，与tasks.json文件中最终生成结果名称保持一致**

  ```shell
  "program": "${fileDirname}/${fileBasenameNoExtension}",
  ```

- **Run Without Debugging 直接跑 Start Debugging 加断点调试跑**

- **尽量不要修改launch.json 与tasks.json文件中其他內容**

- **在调试的时候 如果使用自带的终端作为工作台 则把launch.json中的 `"externalConsole": `设置为 `false`；相反利用Ubuntu终端的话 则设置为 `true`**

- 