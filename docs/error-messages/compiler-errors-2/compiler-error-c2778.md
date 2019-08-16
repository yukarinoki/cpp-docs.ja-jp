---
title: コンパイラエラー C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 98b5bf0a1315236f3ce96fd4b8c140ce1ab70a9f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501033"
---
# <a name="compiler-error-c2778"></a>コンパイラエラー C2778

__declspec (uuid ()) の GUID の形式が正しくありません

[Uuid](../../cpp/uuid-cpp.md)拡張属性に無効な GUID が指定されています。

GUID は、次の形式の16進数の文字列である必要があります。

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

拡張`uuid`属性は、 [CLSIDFromString](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)によって認識される文字列を受け入れます。かっこ区切り記号は使用できません。

次の例では、C2778 が生成されます。

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```