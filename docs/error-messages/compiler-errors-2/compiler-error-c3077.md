---
title: コンパイラ エラー C3077
ms.date: 11/04/2016
f1_keywords:
- C3077
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
ms.openlocfilehash: d59859b82c1a8d506bb793a2c4dcd887b0898d85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644042"
---
# <a name="compiler-error-c3077"></a>コンパイラ エラー C3077

'finalizer': ファイナライザーは、参照型のメンバーにのみなることができます

ネイティブ型または値型でファイナライザーを宣言することはできません。

詳細については、[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)を参照してください。

## <a name="example"></a>例

次の例では警告 C3077 が生成されます。

```
// C3077.cpp
// compile with: /clr /c
value struct vs {
   !vs(){}   // C3077
};

ref struct rs {
protected:
   !rs(){}   // OK
};
```