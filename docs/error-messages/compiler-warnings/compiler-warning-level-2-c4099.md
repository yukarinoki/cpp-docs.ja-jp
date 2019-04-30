---
title: コンパイラの警告 (レベル 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: 09ea9e2963735c1e011e25b42b04ad6d67d084a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349816"
---
# <a name="compiler-warning-level-2-c4099"></a>コンパイラの警告 (レベル 2) C4099

'identifier': 型名が 'objecttype1' '%objecttype2' を使用して認識を使用して最初の表示

クラスと構造体として宣言されたオブジェクトが定義されているか、クラスとして宣言されたオブジェクトが構造体として定義されています。 コンパイラは、定義で指定された型を使用します。

## <a name="example"></a>例

次の例では、C4099 が生成されます。

```
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```