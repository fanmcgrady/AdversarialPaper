# 恶意软件检测与对抗论文阅读笔记

## 0x00 Detection

#### [1] Raff E, Barker J, Sylvester J, et al. Malware detection by eating a whole exe[C]//Workshops at the Thirty-Second AAAI Conference on Artificial Intelligence. 2018.
> 整个exe作为输入，使用CNN检测
#### [2] Anderson H S, Roth P. Ember: an open dataset for training static pe malware machine learning models[J]. arXiv preprint arXiv:1804.04637, 2018.
> 提出了一个叫做Ember的恶意软件检查标杆数据集，以json格式存储，而非真实的PE文件

## 0x01 Evasion

#### [1] Demetrio L, Biggio B, Lagorio G, et al. Functionality-preserving black-box optimization of adversarial windows malware[J]. IEEE Transactions on Information Forensics and Security, 2021, 16: 3469-3478.
> 使用遗传算法，通过末尾添加字符、添加新section，攻击MalConv、EMBER两个模型

#### [2] Gibert D, Fredrikson M, Mateu C, et al. Enhancing the insertion of NOP instructions to obfuscate malware via deep reinforcement learning[J]. Computers & Security, 2022, 113: 102543.
> 文章非常水，提出通过添加NOP汇编指令来修改PE文件，框架采用DDQN，但是存在两个致命的问题：
> 
> 1、文中说修改后，不影响PE文件的功能，但是实验部分说的使用的微软数据集。微软数据集根本不能执行，只是处理后的PE文件碎片，太水了
> 
> 2、没有描述如何处理NOP指令添加到函数汇编代码后，如何处理汇编代码的偏移问题，太水了

#### [3] Chen S, Xue M, Fan L, et al. Automated poisoning attacks and defenses in malware detection systems: An adversarial machine learning approach[J]. computers & security, 2018, 73: 326-344.
> 基于Android样本提出了一种对投毒攻击的检测方法，用对抗样本来提升检测引擎鲁棒性，类似Re-Training。
> 
> 将样本中离hyperplane最远的两种样本，来修正对抗样本。
> 
> 实验对比计较充分，可以学习。
> 
> 启示：对于神经网络模型的对抗可以找置信度0.5左右的样本来改；对于传统机器学习模型可以找离决策边界较近的样本。

#### [4] Yuste J, Pardo E G, Tapiador J. Optimization of code caves in malware binaries to evade machine learning detectors[J]. Computers & Security, 2022, 116: 102643.
> 使用遗传算法，添加bytes到PE文件空隙里面（作者取名Code cave），根据插入的位置和插入内容的大小，设置了多种场景攻击MalConv模型
> 
> 总体没有创新，和文献[1]类似，涉嫌抄袭

#### [5] Zhao K, Zhou H, Zhu Y, et al. Structural attack against graph based android malware detection[C]//Proceedings of the 2021 ACM SIGSAC Conference on Computer and Communications Security. 2021: 3218-3235.
> CCS2021，确实写得不错
> 
> 提出结构攻击方法，相当于动态改，不是静态改

#### [6] Junod P, Rinaldini J, Wehrli J, et al. Obfuscator-LLVM--software protection for the masses[C]//2015 IEEE/ACM 1st International Workshop on Software Protection. IEEE, 2015: 3-9.
> 实现了LLVM IR层混淆方法：指令替换、虚假控制流插入、代码扁平化、基本块拆分、函数合并。
> 可以用来动态行为修改。

#### [7] Liu X, Zhang J, Lin Y, et al. ATMPA: attacking machine learning-based malware visualization detection methods via adversarial examples[C]//2019 IEEE/ACM 27th International Symposium on Quality of Service (IWQoS). IEEE, 2019: 1-10.
> 攻击了三种模型 CNN、SVM、RF
> 借助了FSGM、C&W的方法，逻辑混乱，概念性东西太多，故事没讲清楚。

#### [8] Shafiei A, Rimmer V, Tsingenopoulos I, et al. Position Paper: On Advancing Adversarial Malware Generation Using Dynamic Features[C]//Proceedings of the 1st Workshop on Robust Malware Analysis. 2022: 15-20.
> 概念性的文章，对恶意软件动静态规避提出了一些归纳和想法
