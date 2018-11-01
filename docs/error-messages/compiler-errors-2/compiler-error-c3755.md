---
title: コンパイラ エラー C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 90dc3b7a0e1dbc4e0dc6c42ca722ca1db462fca9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558211"
---
# <a name="compiler-error-c3755"></a>コンパイラ エラー C3755

'delegate': デリゲートが定義されていません

A[デリゲート (C++ コンポーネント拡張)](../../windows/delegate-cpp-component-extensions.md)宣言しますが、定義されていないことができます。

## <a name="example"></a>例

次の例では、C3755 が生成されます。

```
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>例

C3755 は、デリゲートのテンプレートを作成しようとした場合にも発生します。 次の例では、C3755 が生成されます。

```
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```