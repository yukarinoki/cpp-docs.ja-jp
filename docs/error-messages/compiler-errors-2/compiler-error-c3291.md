---
title: コンパイラ エラー C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: 4e8bc312bc10fb5ddc82d811f686004f08603d06
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228870"
---
# <a name="compiler-error-c3291"></a>コンパイラ エラー C3291

'default': trivial プロパティの名前にすることはできません

Trivial プロパティの名前を指定することはできません **`default`** 。 詳細については、「 [property](../../extensions/property-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3291 が生成されます。

```cpp
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```
