---
title: コンパイラ エラー C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 5b610d54331349c53ff01f5c09bb53ff52216c26
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455823"
---
# <a name="compiler-error-c3080"></a>コンパイラ エラー C3080

'finalizer_function': ファイナライザーに、ストレージ クラスの指定子を含めることはできません

詳細については、[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)を参照してください。

## <a name="example"></a>例

次の例では C3080 が生成されます。

```
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```