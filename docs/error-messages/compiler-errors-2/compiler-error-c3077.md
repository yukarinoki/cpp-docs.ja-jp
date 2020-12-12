---
description: 詳細については、「コンパイラエラー C3077」を参照してください。
title: コンパイラ エラー C3077
ms.date: 11/04/2016
f1_keywords:
- C3077
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
ms.openlocfilehash: a8e6a15f38427727939fbaabb0bfcf4d9e315d77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320168"
---
# <a name="compiler-error-c3077"></a>コンパイラ エラー C3077

'finalizer': ファイナライザーは、参照型のメンバーにのみなることができます

ネイティブ型または値型でファイナライザーを宣言することはできません。

詳細については、「 [方法: クラスと構造体を定義および使用する (C++/cli)」の「デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

## <a name="example"></a>例

次の例では警告 C3077 が生成されます。

```cpp
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
