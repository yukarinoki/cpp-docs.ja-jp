---
description: 詳細については、「コンパイラエラー C3080」を参照してください。
title: コンパイラ エラー C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 746e5527118c617983e96d02a584a0aa4508c64c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320155"
---
# <a name="compiler-error-c3080"></a>コンパイラ エラー C3080

'finalizer_function': ファイナライザーに、ストレージ クラスの指定子を含めることはできません

詳細については、「 [方法: クラスと構造体を定義および使用する (C++/cli)」の「デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

## <a name="example"></a>例

次の例では C3080 が生成されます。

```cpp
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```
