---
title: コンパイラ エラー C2778 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2778
dev_langs:
- C++
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6106832ea82531a6f6915417ac56d53504db882e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022163"
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