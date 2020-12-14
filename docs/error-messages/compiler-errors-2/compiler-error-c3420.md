---
description: 詳細については、「コンパイラエラー C3420」を参照してください。
title: コンパイラ エラー C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3c79693823255ed7335e5805c0ac17de5ddcead7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315999"
---
# <a name="compiler-error-c3420"></a>コンパイラ エラー C3420

'finalizer' : ファイナライザーを仮想にすることはできません

ファイナライザーは、それを囲む型から非仮想的にのみ呼び出すことができます。 したがって、仮想のファイナライザーを宣言すると、エラーになります。

詳細については、「 [方法: クラスと構造体を定義および使用する (C++/cli)」の「デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

## <a name="example"></a>例

次の例では C3420 が生成されます。

```cpp
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```
