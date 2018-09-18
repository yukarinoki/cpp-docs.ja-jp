---
title: コンパイラの警告 (レベル 1) C4269 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dc986c98028530b8a5d4d25047305fd1a8effef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027279"
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