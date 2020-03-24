---
title: コンパイラの警告 (レベル 3) C4359
ms.date: 11/04/2016
f1_keywords:
- C4359
helpviewer_keywords:
- C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
ms.openlocfilehash: 5cb65bab1f6490d1c39b20bfba2b3ecc68da664d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198693"
---
# <a name="compiler-warning-level-3-c4359"></a>コンパイラの警告 (レベル 3) C4359

' type ': 実際のアラインメント (8) は、__declspec (align ()) で指定された値を超えています

型に対して指定されたアラインメントは、そのデータメンバーの1つの型のアラインメントよりも小さくなっています。  詳細については、「 [align](../../cpp/align-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4359 が生成されます。

```cpp
// C4359.cpp
// compile with: /W3 /c
struct __declspec(align(8)) C8 { __int64 i; };
struct __declspec(align(4)) C4  { C8 m8; };   // C4359
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK
struct __declspec(align(16)) C16  { C8 m8; };   // OK
```
