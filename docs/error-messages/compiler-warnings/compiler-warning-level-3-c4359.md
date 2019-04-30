---
title: コンパイラの警告 (レベル 3) C4359
ms.date: 11/04/2016
f1_keywords:
- C4359
helpviewer_keywords:
- C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
ms.openlocfilehash: 3856c50aabce497f28a179b30346b30371986e51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402009"
---
# <a name="compiler-warning-level-3-c4359"></a>コンパイラの警告 (レベル 3) C4359

'type': 実際の配置 (8) が __declspec(align()) で指定された値より大きい

型指定された配置では、そのデータ メンバーのいずれかの型のアラインメントより小さいです。  詳細については、次を参照してください。 [align](../../cpp/align-cpp.md)します。

## <a name="example"></a>例

次の例では、C4359 が生成されます。

```
// C4359.cpp
// compile with: /W3 /c
struct __declspec(align(8)) C8 { __int64 i; };
struct __declspec(align(4)) C4  { C8 m8; };   // C4359
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK
struct __declspec(align(16)) C16  { C8 m8; };   // OK
```