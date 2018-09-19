---
title: コンパイラの警告 (レベル 1) C4526 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed6f2da3252c27b7a84b4d5b73f7e8ba52823dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118506"
---
# <a name="compiler-warning-level-1-c4526"></a>コンパイラの警告 (レベル 1) C4526

'function': 静的メンバー関数は、仮想関数をオーバーライドできません ' 仮想 function'override を無視するには、仮想関数は非表示にします。

静的メンバー関数では、仮想と静的メンバー関数は、仮想関数をオーバーライドする条件を満たします。

次のコードでは、C4526 が生成されます。

```
// C4526.cpp
// compile with: /W1 /c
// C4526 expected
struct myStruct1 {
   virtual void __stdcall func( int ) = 0;
};

struct myStruct2: public myStruct1 {
   static void __stdcall func( int );
};
```

次に、考えられる修正方法を示します。

- 関数は、基底クラスの仮想関数をオーバーライドするためのものが場合、は、静的な指定子を削除します。

- 静的メンバー関数を使用する予定の関数場合、基底クラスの仮想関数とも競合しないように変更します。