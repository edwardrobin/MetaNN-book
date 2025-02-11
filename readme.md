《C++模板元编程实战》一书分若干章节对本分支的代码进行了讨论。这些代码组合起来形成了 MetaNN 的框架，具有一定的整体性——很难按照书中所讨论的顺序划分章节进行组织。而这也就给需要对照代码来阅读本书的读者造成了一些困难：读者不得不通过搜索书中出现的关键字来定位所讨论的内容在源代码中的相应位置。为了解决这个问题，我在这里引入了这篇文档，描述了书中每一章所讨论的主要内容与源代码之间的对应关系。

源代码包含了两个目录： MetaNN 与 Test ，前者包含了框架的全部逻辑；而后者则是基于 MetaNN 中的逻辑所编写的测试代码。这个文档会同时说明框架逻辑与测试代码的位置，供读者参考。

### 第一章：基本技巧
- 这一章所讨论的内容相对基本、零散，没有对应的源码。

### 第二章：异类词典与 Policy 模板
- 异类词典
  - 框架逻辑：
    - MetaNN/facilities/var_type_dict.h
    - MetaNN/facilities/null_param.h
  - 测试代码：
    - Test/facilities/test_var_type_dict.cpp
- Policy 模板
  - 框架逻辑：
    - MetaNN/policies/policy_container.h
    - MetaNN/policies/policy_macro_begin.h
    - MetaNN/policies/policy_macro_end.h
    - MetaNN/policies/policy_selector.h
  - 测试代码：
    - Test/policies/test_policy_selector.cpp

### 第三章：深度学习概述
 - 这一章讨论深度学习的基本概念，不涉及代码。

### 第四章：类型体系与基本数据类型
  - MetaNN 的类型体系相关元函数
    - 框架逻辑：
      - MetaNN/data/facilities/tags.h
      - MetaNN/data/facilities/traits.h
  - 空间的分配与维护
    - 框架逻辑：
      - MetaNN/data/facilities/allocators.h
      - MetaNN/data/facilities/continuous_memory.h
  - 标量
    - 框架逻辑：
      - MetaNN/data/scalar.h
    - 测试代码：
      - Test/data/test_scalar.cpp
  - 矩阵
    - 框架逻辑：
      - MetaNN/data/matrices （目录）
    - 测试代码：
      - Test/data/test_general_matrix.cpp
      - Test/data/test_one_hot_vector.cpp
      - Test/data/test_trival_matrix.cpp
      - Test/data/test_zero_matrix.cpp
  - 列表
    - 框架逻辑：
      - MetaNN/data/batch （目录）
    - 测试代码：
      - Test/data/test_array.cpp
      - Test/data/test_batch_matrix.cpp
      - Test/data/test_batch_scalar.cpp
      - Test/data/test_duplicate.cpp

### 第五章：运算与表达式模板
  - 运算分类
    - 框架逻辑：
      - MetaNN/operators/facilities/tags.h
  - 辅助模板
    - 框架逻辑：
      - MetaNN/operators/facilities/category_cal.h
      - MetaNN/operators/facilities/oper_seq.h
      - MetaNN/operators/facilities/organizer.h
      - MetaNN/operators/facilities/traits.h
  - 运算模板框架
    - 框架逻辑：
      - MetaNN/operators/operators.h
  - 运算模板实现示例
    - 框架逻辑：
      - MetaNN/operators	（目录，其中的每个文件对应了一个运算）
    - 测试代码：
      - Test/operators	（目录，其中的每个 cpp 文件对应了一个运算的测试）

### 第六章：基本层
  - 初始化模块
    - 框架逻辑：
      - MetaNN/model_rel/param_initializer	（目录）
    - 测试代码：
      - Test/model_rel/param_initializer	（目录）
  - DynamicData 类模板
    - 框架逻辑：
      - MetaNN/data/dynamic.h
  - 常用 Policy 对象
    - 框架逻辑：
      - MetaNN/layers/facilities/policies.h
  - InjectPolicy 元函数
    - 框架逻辑：
      - MetaNN/policies/inject_policy.h
  - 通用 IO 结构
    - 框架逻辑：
      - MetaNN/layers/facilities/common_io.h
  - 通用操作函数
    - 框架逻辑：
      - MetaNN/layers/facilities/interface_fun.h
  - 层的具体实现
    - 框架逻辑：
      - MetaNN/layers/elementary	（目录）
    - 测试代码：
      - Test/layers/elementary	（目录）

### 第七章：复合层与循环层
  - Policy 的继承与修正逻辑
    - 框架逻辑：
      - MetaNN/policies/change_policy.h
      - MetaNN/policies/policy_operations.h
    - 测试代码：
      - Test/policies/test_change_policy.cpp
      - Test/policies/test_policy_operations.cpp
  - ComposeTopology & ComposeKernel
    - 框架逻辑：
      - MetaNN/layers/compose/compose_kernel.h
    - 测试代码：
      - Test/layers/test_compose_kernel.cpp
  - 复合层实现示例
    - 框架逻辑：
      - MetaNN/layers/compose/linear_layer.h
      - MetaNN/layers/compose/single_layer.h
    - 测试代码：
      - Test/layers/compose/test_linear_layer.cpp
      - Test/layers/compose/test_single_layer.cpp
  - 循环层
    - 框架逻辑：
      - MetaNN/layers/recurrent	（目录）
    - 测试代码：
      - Test/layers/recurrent	（目录）

### 第八章：求值与优化
  - 求值子系统
    - 框架逻辑：
      - MetaNN/evaluate	（目录）
    - 测试代码：
      - Test/evaluate/test_eval_plan.cpp
  - 具体求值实现与优化
    - 不同的数据、运算实现了不同的求值逻辑，请参考相应的目录以获取具体的求值逻辑与测试代码：
    - 框架逻辑：
      - MetaNN/data	（目录）
      - MetaNN/operators	（目录）
    - 测试代码：
      - Test/data	（目录）
      - Test/operators	（目录）
