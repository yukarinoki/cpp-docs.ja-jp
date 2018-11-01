---
title: コンパイラの警告 (レベル 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 9a7f42b2dd65644d3f2abec58236a0b93cc6f635
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653844"
---
# <a name="compiler-warning-level-1-c4269"></a>コンパイラの警告 (レベル 1) C4269

'identifier': 'const' 自動データがコンパイラによって生成された既定のコンス トラクターで初期化された生成結果の信頼性

A **const**自明でないクラスの自動インスタンスは、コンパイラによって生成された既定のコンス トラクターで初期化されます。

## <a name="example"></a>例

```
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

スタックの初期値に、クラスのこのインスタンスが生成されるので`m_data`任意に指定できます。 その後も、 **const**インスタンスの値`m_data`変更できないことができます。