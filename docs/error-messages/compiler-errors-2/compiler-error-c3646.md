---
title: コンパイラ エラー C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 13a3ebeb6e7783687abc73cd0dcc018abe827809
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200474"
---
# <a name="compiler-error-c3646"></a>コンパイラ エラー C3646

> ' 指定子 ': 不明なオーバーライド指定子です。

## <a name="remarks"></a>解説

コンパイラは、オーバーライド指定子を検索する必要がある位置にトークンを検出しましたが、トークンはコンパイラによって認識されませんでした。

たとえば、認識されない*指定子*が **_NOEXCEPT**場合は、それをキーワード**NOEXCEPT**に置き換えます。

詳細については、「[オーバーライド指定子](../../extensions/override-specifiers-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3646 を生成し、その修正方法を示しています。

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```
