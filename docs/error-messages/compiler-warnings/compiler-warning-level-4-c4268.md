---
title: コンパイラの警告 (レベル 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: 1db8f67591560c130bc25c40c63232f54b3b7884
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219912"
---
# <a name="compiler-warning-level-4-c4268"></a>コンパイラの警告 (レベル 4) C4268

' identifier ': コンパイラで生成された既定のコンストラクターで ' const ' 静的/グローバルデータを初期化しました。オブジェクトには0が設定されます

**`const`** 単純なクラスのグローバルまたは静的インスタンスは、コンパイラによって生成される既定のコンストラクターで初期化されます。

## <a name="example"></a>例

```cpp
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

クラスのこのインスタンスはである **`const`** ため、の値は `m_data` 変更できません。
