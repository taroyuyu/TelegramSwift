# TelegramSwift的编译

- clone项目

  ```bash
  $ git clone  https://github.com/overtake/TelegramSwift
  ```

- 回滚到特定的历史

  https://www.jianshu.com/p/968097f321d0

  ```bash
  $ git reset --hard 129f0903f9463672b6575c8d0e35ecb6820572f5
  ```

- 修改git子模块的路径

  将`.gitmodules `文件中的内容替换为以下内容

  ```bash
  [submodule "submodules/libtgvoip"]
  	path = submodules/libtgvoip
  url=git://github.com/telegramdesktop/libtgvoip
  [submodule "submodules/Sparkle"]
  	path = submodules/Sparkle
  url=git://github.com/overtake/Sparkle
  [submodule "submodules/Zip"]
  	path = submodules/Zip
  	url = git://github.com/overtake/Zip
  [submodule "submodules/telegram-ios"]
  	path = submodules/telegram-ios
  url=git://github.com/overtake/Telegram-iOS
  [submodule "submodules/rlottie"]
  	path = submodules/rlottie
  url=git://github.com/overtake/rlottie
  [submodule "submodules/ton"]
  	path = submodules/ton
  url=git://github.com/overtake/ton
  ```

- 加载子模块

  ```bash
  $ git submodule update --init --recursive
  ```

- 安装依赖

  ```bash
  $ brew install cmake ninja openssl@1.1 zlib
  ```

- 检查电脑上的openssl的版本

  ```bash
  % ls /usr/local/Cellar/openssl@1.1/  
  1.1.1i
  ```

- 修改Tonbinding_Xcode工程的Run Script

  选择Tonbinding_Xcode 切换到Build Phases，在Run Script中修改`openssl@1.1/1.1.1d`为电脑上的对应版本。例如，我的电脑上安装的事1.1.1i版本，则将其修改为`openssl@1.1/1.1.1i`

- 选择编译的目标为 Github进行编译。