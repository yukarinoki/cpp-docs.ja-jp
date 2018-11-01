---
title: コンパイラ エラー C3218
ms.date: 11/04/2016
f1_keywords:
- C3218
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
ms.openlocfilehash: 87084f9751b1593ec93a3062f23714bba403da9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578205"
---
# <a name="compiler-error-c3218"></a>コンパイラ エラー C3218

'type': 型制約として許可されません。

制約のある型の場合は、値型またはマネージ クラスまたはインターフェイスへの参照があります。

## <a name="example"></a>例

次の例では、C3218 が生成されます。

```
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