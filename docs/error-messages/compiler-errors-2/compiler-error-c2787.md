---
title: コンパイラ エラー C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 656fcd8a1a0429546189de8c3f01ab928c6333ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256868"
---
# <a name="compiler-error-c2787"></a>コンパイラ エラー C2787

'identifier': このオブジェクトに関連付けられた GUID はありません。

[_ _Uuidof](../../cpp/uuidof-operator.md)操作はユーザー定義型、またはユーザー定義型のオブジェクトにアタッチされている GUID を使用します。 このエラーは、引数が GUID を持つユーザー定義型である場合に発生しません。

次の例では、C2787 が生成されます。

```
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```