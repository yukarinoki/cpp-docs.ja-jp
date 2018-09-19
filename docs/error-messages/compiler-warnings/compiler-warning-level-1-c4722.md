---
title: コンパイラの警告 (レベル 1) C4722 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f450120ff05c7e13888bf4b4ce4425405525b4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112500"
---
# <a name="compiler-warning-level-1-c4722"></a>コンパイラの警告 (レベル 1) C4722

'function': デストラクターに値が戻りません。メモリ リークの可能性があります

制御フローは、デストラクターで終了します。 スレッドまたはプログラム全体が終了し、割り当てられたリソースが解放されていない可能性があります。  さらに、例外の処理中にスタック アンワインドのためにデストラクターを呼び出す場合、実行可能ファイルの動作は未定義です。

解決するには、デストラクターが制御を戻さない原因となった関数呼び出しを削除します。

## <a name="example"></a>例

次の例では C4722 が生成されます。

```
// C4722.cpp
// compile with: /O1 /W1 /c
#include <stdlib.h>
class C {
public:
   C();
   ~C() { exit(1); };   // C4722
};

extern void func (C*);

void Test(){
   C x;
   func(&x);
   // control will not leave Test because destructor will exit
}
```