# JavaScript 规范

### 定义
JavaScript 规范是以 [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) 为基础，并针对 [eslint](http://eslint.org/) 提供的部分校验规则进行额外调整后制定的。具体定义请参考：
*   [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)（基础规范定义）
*   [项目标准配置文件 .eslintrc](http://202.85.214.81/trunk/fe-team/generator-fe/generators/app/templates/.eslintrc)（额外调整的规则定义）

### 执行
JavaScript 规范的执行基于以下工具实现：
*   **[eslint](http://eslint.org/)**  
    latest  
    通过一组预定义规则进行 JavaScript 代码校验，校验内容包括编码风格，常见错误和最佳实践等。我们通过添加配置文件使其支持 [eslint-config-airbnb](https://github.com/airbnb/javascript) 和额外调整的规则定义。

*   **[eslint-config-airbnb](https://github.com/airbnb/javascript)**  
    latest  
    以 [eslint](http://eslint.org/) 配置文件方式实现的 Airbnb JavaScript 编码规范，用于校验代码是否符合规范。

*   **[linter](https://atom.io/packages/linter)**  
    latest  
    [Atom](https://atom.io/) 插件，用于在 IDE 中支持不同类型代码的校验功能。

*   **[linter-eslint](https://github.com/AtomLinter/linter-eslint)**  
    latest  
    [Atom](https://atom.io/) 插件，基于 [linter](https://atom.io/packages/linter) 和 [eslint](http://eslint.org/) 实现 js 代码的实时校验和错误提示功能。

*   **[atom-beautify](https://atom.io/packages/atom-beautify)**  
    latest  
    [Atom](https://atom.io/) 插件，用于格式化代码。我们提供一组配置使插件尽可能按代码规范进行格式化，具体定义见 [项目标准配置文件 .jsbeautifyrc](http://202.85.214.81/trunk/fe-team/generator-fe/generators/app/templates/.jsbeautifyrc)。
