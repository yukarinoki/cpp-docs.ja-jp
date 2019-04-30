---
title: コンパイラ エラー C2498
ms.date: 11/04/2016
f1_keywords:
- C2498
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
ms.openlocfilehash: 1087dbb2297058f752e0a15776e4a7185e32a5c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360470"
---
# <a name="compiler-error-c2498"></a>コンパイラ エラー C2498

'function': 'novtable' は、クラス宣言または定義にのみ適用できます

使用してこのエラーは発生する`__declspec(novtable)`関数を使用します。

## <a name="example"></a>例

次の例では、C2498 が生成されます。

```
// C2498.cpp
// compile with: /c
void __declspec(novtable) f() {}   // C2498
class __declspec(novtable) A {};   // OK
```