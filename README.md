# AdversarialPaper

## 0x00 Detection

### [1] Raff E, Barker J, Sylvester J, et al. Malware detection by eating a whole exe[C]//Workshops at the Thirty-Second AAAI Conference on Artificial Intelligence. 2018.
> 整个exe作为输入，使用CNN检测
### [2] Anderson H S, Roth P. Ember: an open dataset for training static pe malware machine learning models[J]. arXiv preprint arXiv:1804.04637, 2018.
> 提出了一个叫做Ember的恶意软件检查标杆数据集，以json格式存储，而非真实的PE文件

## 0x01 Evasion

### [1] Demetrio L, Biggio B, Lagorio G, et al. Functionality-preserving black-box optimization of adversarial windows malware[J]. IEEE Transactions on Information Forensics and Security, 2021, 16: 3469-3478.
> 使用遗传算法，通过末尾添加字符、添加新section，攻击MalConv、EMBER两个模型

### [2] Gibert D, Fredrikson M, Mateu C, et al. Enhancing the insertion of NOP instructions to obfuscate malware via deep reinforcement learning[J]. Computers & Security, 2022, 113: 102543.
> 文章非常水，提出通过添加NOP汇编指令来修改PE文件，框架采用DDQN，但是存在两个致命的问题：
> 
> 1、文中说修改后，不影响PE文件的功能，但是实验部分说的使用的微软数据集。微软数据集根本不能执行，只是处理后的PE文件碎片，太水了
> 
> 2、没有描述如何处理NOP指令添加到函数汇编代码后，如何处理汇编代码的偏移问题，太水了
