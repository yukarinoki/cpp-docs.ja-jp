---
title: コンパイラ エラー C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: f3c7b1a18dda9b2f9af7e346c2a1ed2f0303bb61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208900"
---
# <a name="compiler-error-c2007"></a>コンパイラ エラー C2007

\#構文を定義します。

後に識別子が表示されない、`#define`します。 エラーを解決するには、識別子を使用します。

次の例では、C2007 が生成されます。

```
// C2007.cpp
#define   // C2007
```

考えられる解決方法:

```
// C2007b.cpp
// compile with: /c
#define true 1
```