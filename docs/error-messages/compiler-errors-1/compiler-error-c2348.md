---
title: コンパイラ エラー C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 716fdf244f19fa8f0960a0279da3c39af1546178
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218261"
---
# <a name="compiler-error-c2348"></a>コンパイラ エラー C2348

' type name ': は C スタイルの集計ではありません。埋め込み IDL 内でエクスポートできません

**`struct`** [Export](../../windows/export.md)属性を使用して .idl ファイルにを配置するには、に **`struct`** データのみを含める必要があります。

次の例では、C2348 が生成されます。

```cpp
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```
