---
description: 詳細については、「コンパイラエラー C3218」を参照してください。
title: コンパイラ エラー C3218
ms.date: 11/04/2016
f1_keywords:
- C3218
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
ms.openlocfilehash: 9b8b3ed9fdd0fa2632435f4afd9d6ef9bb39b49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173702"
---
# <a name="compiler-error-c3218"></a>コンパイラ エラー C3218

' type ': 型は制約として使用できません

型を制約として使用するには、値型であるか、マネージクラスまたはマネージインターフェイスへの参照である必要があります。

## <a name="example"></a>例

次の例では、C3218 が生成されます。

```cpp
// C3218.cpp
// compile with: /clr /c
class A {};
ref class B {};

// Delete the following 3 lines to resolve.
generic <class T>
where T : A   // C3218
ref class C {};

// OK
generic <class T>
where  T : B
ref class D {};
```
