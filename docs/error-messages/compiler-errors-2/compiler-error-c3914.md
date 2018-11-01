---
title: コンパイラ エラー C3914
ms.date: 11/04/2016
f1_keywords:
- C3914
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
ms.openlocfilehash: e7c04da2b7574d3af0e1c05ae4adc3ad513faa0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577888"
---
# <a name="compiler-error-c3914"></a>コンパイラ エラー C3914

既定のプロパティを静的にすることはできません。

既定のプロパティの宣言が正しくありません。  詳細については、次を参照してください。[方法: プロパティを使用して c++/cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)します。

## <a name="example"></a>例

次の例では、C3914 を生成し、その修正方法を示しています。

```
// C3914.cpp
// compile with: /clr /c
ref struct X {
   static property int default[int] {   // C3914
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```