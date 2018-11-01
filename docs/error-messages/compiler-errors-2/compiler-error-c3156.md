---
title: コンパイラ エラー C3156
ms.date: 11/04/2016
f1_keywords:
- C3156
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
ms.openlocfilehash: 115e8cd63562964b19e4a67f7a649ecfab2596c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465261"
---
# <a name="compiler-error-c3156"></a>コンパイラ エラー C3156

'class' : マネージド型または WinRT 型のローカル定義を持つことができません

関数に、マネージド型または WinRT 型のクラス、構造体、インターフェイスの定義 (宣言) を含めることはできません。

## <a name="example"></a>例

次の例では C3156 が生成されます。

```
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
