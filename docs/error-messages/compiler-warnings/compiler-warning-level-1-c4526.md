---
title: コンパイラの警告 (レベル 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 892e6c37e54a868be48ced35354a1096aa7bf9d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160745"
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