---
title: コンパイラ エラー C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 5f39510ee9ec0e717d675aa8b396405bc33b4ea1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445007"
---
# <a name="compiler-error-c3279"></a>コンパイラ エラー C3279

cli 名前空間で宣言されたクラス テンプレートの明示的なインスタンス生成と同様に、部分的または明示的な特殊化は許可されていません

`cli` 名前空間は、Microsoft によって定義され、擬似テンプレートが含まれています。 Visual C++ コンパイラでは、この名前空間におけるユーザー定義、部分的、および明示的な特殊化は許可されず、クラス テンプレートの明示的なインスタンス化も許可されません。

次の例では C3279 が生成されます。

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```