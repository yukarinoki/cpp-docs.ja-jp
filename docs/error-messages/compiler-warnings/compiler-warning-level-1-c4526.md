---
description: '詳細情報: コンパイラの警告 (レベル 1) C4526'
title: コンパイラの警告 (レベル 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 13eddea0fcf82686333fe51d253c3b24552e18c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294822"
---
# <a name="compiler-warning-level-1-c4526"></a>コンパイラの警告 (レベル 1) C4526

' function ': 静的メンバー関数は、仮想関数 ' virtual function' override を無視できません。仮想関数は非表示になります

静的メンバー関数は、仮想関数をオーバーライドするための条件を満たしています。これにより、メンバー関数は virtual と static の両方で機能します。

次のコードでは、C4526 が生成されます。

```cpp
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

考えられる修正は次のとおりです。

- 関数が基底クラスの仮想関数をオーバーライドする場合は、静的指定子を削除します。

- 関数が静的メンバー関数である場合は、基底クラスの仮想関数と競合しないように名前を変更します。
