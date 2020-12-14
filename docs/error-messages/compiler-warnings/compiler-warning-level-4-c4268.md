---
description: '詳細情報: コンパイラの警告 (レベル 4) C4268'
title: コンパイラの警告 (レベル 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: 50e4a2afd577653fa14ae5d663f2b00fa95670b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294666"
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
