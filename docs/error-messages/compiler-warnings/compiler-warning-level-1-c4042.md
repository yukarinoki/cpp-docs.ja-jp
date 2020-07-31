---
title: コンパイラの警告 (レベル 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: cd8d8addb8441bd32d242c4f4858104048f7a62e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197073"
---
# <a name="compiler-warning-level-1-c4042"></a>コンパイラの警告 (レベル 1) C4042

' identifier ': 無効なストレージクラスがあります

このコンテキストでは、指定されたストレージクラスをこの識別子と共に使用することはできません。 コンパイラは、代わりに既定のストレージクラスを使用します。

- **`extern`***識別子*が関数の場合は。

- **`auto`***識別子*が仮パラメーターまたはローカル変数である場合は、。

- ストレージクラスがありません。*識別子*がグローバル変数です。

この警告は、パラメーター宣言で以外のストレージクラスを指定することによって発生することがあり **`register`** ます。

次の例では、C4042 が生成されます。

```cpp
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```
