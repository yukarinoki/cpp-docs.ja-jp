---
description: 詳細については、「コンパイラエラー C2569」を参照してください。
title: コンパイラ エラー C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: bf6b0670cfd90cadc939010a75f9faa9c7c25c30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209036"
---
# <a name="compiler-error-c2569"></a>コンパイラ エラー C2569

' EnumOrUnion ': 列挙型/共用体を基底クラスとして使用することはできません

指定した共用体または列挙体から型を派生させる必要がある場合は、共用体または列挙体をクラスまたは構造体に変更します。

次の例では、C2569 が生成されます。

```cpp
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```
