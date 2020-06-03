---
title: コンパイラ エラー C2871
ms.date: 11/04/2016
f1_keywords:
- C2871
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
ms.openlocfilehash: cc24e5fefe9ffd67dc6b01520ea32805a22f70c3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201683"
---
# <a name="compiler-error-c2871"></a>コンパイラ エラー C2871

' name ': この名前の名前空間は存在しません

このエラーは、名前空間ではない識別子を[using](../../cpp/namespaces-cpp.md#using_directives)ディレクティブに渡した場合に発生します。

## <a name="example"></a>例

次の例では、C2871 が生成されます。

```cpp
// C2871.cpp
// compile with: /c
namespace a {
   int fn(int i) { return i; }
}
namespace b {
   using namespace d;   // C2871 because d is not a namespace
   using namespace a;   // OK
}
```
