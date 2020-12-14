---
description: 詳細については、「コンパイラエラー C2778」を参照してください。
title: コンパイラエラー C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: e614ed5ee94a4876a687bfa8257abc5bcd9d8587
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298072"
---
# <a name="compiler-error-c2778"></a>コンパイラエラー C2778

__declspec (uuid ()) の GUID の形式が正しくありません

[Uuid](../../cpp/uuid-cpp.md)拡張属性に無効な GUID が指定されています。

GUID は、次の形式の16進数の文字列である必要があります。

```cpp
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

`uuid`拡張属性は、 [CLSIDFromString](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)によって認識される文字列を受け入れます。かっこ区切り記号は使用できません。

次の例では、C2778 が生成されます。

```cpp
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```
