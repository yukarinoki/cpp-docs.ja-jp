---
title: コンパイラ エラー C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 8131b259f89c5cacd07d04edbf6c45adaa25b145
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367994"
---
# <a name="compiler-error-c2458"></a>コンパイラ エラー C2458

'identifier': 定義内で再定義されています。

独自の宣言は、クラス、構造体、共用体、または列挙型を再定義されます。

次の例では、C2458 が生成されます。

```
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```