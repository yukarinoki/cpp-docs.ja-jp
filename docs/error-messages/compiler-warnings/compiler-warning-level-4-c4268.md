---
title: コンパイラの警告 (レベル 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: e3cda7ed70963508d7663c6c12b2b98ac64db204
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400917"
---
# <a name="compiler-warning-level-4-c4268"></a>コンパイラの警告 (レベル 4) C4268

'identifier': 'const' static/global データがコンパイラによって生成された既定のコンス トラクターで初期化オブジェクトをゼロでの入力

A **const**自明でないクラスのグローバルまたは静的インスタンスは、コンパイラによって生成された既定のコンス トラクターで初期化されます。

## <a name="example"></a>例

```
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

クラスのこのインスタンスは**const**の値`m_data`変更ことはできません。