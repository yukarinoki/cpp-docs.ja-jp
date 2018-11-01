---
title: コンパイラ エラー C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 56c316ac971d0bdd1a0ca27ef8d4282acbe24779
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490509"
---
# <a name="compiler-error-c2778"></a>コンパイラ エラー C2778

__declspec(uuid()) で不適切な形式の GUID

不適切な GUID が指定された、 [uuid](../../cpp/uuid-cpp.md)拡張属性。

GUID は、次の形式の 16 進数の文字列である必要があります。

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

`uuid`拡張属性がで認識される文字列を受け取る[CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring)かっこ区切り記号の有無、します。

次の例では、C2778 が生成されます。

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```