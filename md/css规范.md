# CSS 规范

### 定义
CSS 规范是以 [stylelint](https://github.com/stylelint/stylelint) 提供的校验规则和官方推荐的标准配置 [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard) 为基础，并针对部分校验规则进行调整后制定的。具体定义请参考：
*   [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)（基础规范定义）
*   [项目标准配置文件 .stylelintrc](http://202.85.214.81/trunk/fe-team/generator-fe/generators/app/templates/.stylelintrc)（额外调整的规则定义）

### 执行
CSS 规范的执行以及以下工具实现：
*   **[stylelint](https://github.com/stylelint/stylelint)**  
    latest  
    通过一组预定义规则进行 CSS 代码校验。我们通过添加配置文件使其支持 [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard) 和额外调整的规则定义。

*   **[stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)**  
    latest  
    [stylelint](https://github.com/stylelint/stylelint) 官方推荐的标准规范配置，用于校验代码是否符合规范。

*   **[linter](https://atom.io/packages/linter)**  
    latest  
    [Atom](https://atom.io/) 插件，用于在 IDE 中支持不同类型代码的校验功能。

*   **[linter-stylelint](https://github.com/AtomLinter/linter-stylelint)**  
    latest  
    [Atom](https://atom.io/) 插件，基于 [linter](https://atom.io/packages/linter) 和 [stylelint](https://github.com/stylelint/stylelint) 实现 css 代码的实时校验和错误提示功能。

*   **[atom-beautify](https://atom.io/packages/atom-beautify)**  
    latest  
    [Atom](https://atom.io/) 插件，用于格式化代码。我们选择 [CSScomb](https://github.com/csscomb/csscomb.js) 引擎实现格式化功能。

*   **[CSScomb](https://github.com/csscomb/csscomb.js)**  
    随 [atom-beautify](https://atom.io/packages/atom-beautify) 安装  
    用于配合 [atom-beautify](https://atom.io/packages/atom-beautify) 按指定优先级对 CSS 代码进行排序、分段和格式化。
