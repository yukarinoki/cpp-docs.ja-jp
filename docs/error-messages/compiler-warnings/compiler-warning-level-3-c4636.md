---
description: '詳細情報: コンパイラの警告 (レベル 3) C4636'
title: コンパイラの警告 (レベル 3) C4636
ms.date: 11/04/2016
f1_keywords:
- C4636
helpviewer_keywords:
- C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
ms.openlocfilehash: 09ba549c4fcd7f48a1a6ed7e1e16bc293c7ad884
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238116"
---
# <a name="compiler-warning-level-3-c4636"></a>コンパイラの警告 (レベル 3) C4636

'construct' に適用された XML ドキュメント コメント: タグには空でない '' 属性が必要です。

`cref`などのタグに値がありませんでした。

## <a name="example"></a>例

次の例では C4636 が生成されます。

```cpp
// C4636.cpp
// compile with: /clr /doc /W3 /c
/// <see cref=''/>
// /// <see cref='System::Exception'/>
ref struct A {   // C4636
   void f(int);
};

// OK
/// <see cref='System::Exception'/>
ref struct B {
   void f(int);
};
```
