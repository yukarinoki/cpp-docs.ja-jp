---
description: 詳細については、「コンパイラエラー C3755」を参照してください。
title: コンパイラ エラー C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 24d6af223b6a15cbf1740bf67144250007c2091d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253586"
---
# <a name="compiler-error-c3755"></a>コンパイラ エラー C3755

' delegate ': デリゲートを定義することはできません

[デリゲート (C++ コンポーネント拡張)](../../extensions/delegate-cpp-component-extensions.md)は宣言できますが、定義することはできません。

## <a name="examples"></a>例

次の例では、C3755 が生成されます。

```cpp
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

C3755 は、デリゲートテンプレートを作成しようとした場合にも発生する可能性があります。 次の例では、C3755 が生成されます。

```cpp
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```
