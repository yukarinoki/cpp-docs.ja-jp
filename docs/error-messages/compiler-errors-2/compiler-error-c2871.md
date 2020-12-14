---
description: 詳細については、「コンパイラエラー C2871」を参照してください。
title: コンパイラ エラー C2871
ms.date: 11/04/2016
f1_keywords:
- C2871
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
ms.openlocfilehash: 6b62d5decb67cf6f8bad4d9b30123ccab54f51c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198298"
---
# <a name="compiler-error-c2871"></a>コンパイラ エラー C2871

' name ': この名前の名前空間は存在しません

このエラーは、名前空間ではない識別子を [using](../../cpp/namespaces-cpp.md#using_directives) ディレクティブに渡した場合に発生します。

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
