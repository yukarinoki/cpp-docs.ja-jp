---
title: コンパイラの警告 (レベル 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 1b63d1af49a53b7b15cdbae912d79a1b4f0cf787
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230715"
---
# <a name="compiler-warning-level-1-c4269"></a>コンパイラの警告 (レベル 1) C4269

' identifier ': コンパイラが生成した既定のコンストラクターで ' const ' 自動データが初期化されました。信頼性の低い結果が生成されます

**`const`** 自明でないクラスの自動インスタンスは、コンパイラによって生成される既定のコンストラクターで初期化されます。

## <a name="example"></a>例

```cpp
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

クラスのこのインスタンスはスタック上で生成されるため、の初期値は `m_data` 任意です。 また、インスタンスであるため、 **`const`** の値を `m_data` 変更することはできません。
