---
description: 詳細については、「コンパイラエラー C2348」を参照してください。
title: コンパイラ エラー C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 829bd94c8fe78280b8b49b74f218e2143dda4335
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298358"
---
# <a name="compiler-error-c2348"></a>コンパイラ エラー C2348

' type name ': は C スタイルの集計ではありません。埋め込み IDL 内でエクスポートできません

**`struct`** [Export](../../windows/attributes/export.md)属性を使用して .idl ファイルにを配置するには、に **`struct`** データのみを含める必要があります。

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
