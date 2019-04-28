---
title: コンパイラ エラー C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 379bcc7f37ff8942e4e45c6a6188438400937875
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187907"
---
# <a name="compiler-error-c2348"></a>コンパイラ エラー C2348

'type name': C スタイルの集合ではありません、埋め込み IDL 内でエクスポートできません。

配置する、 `struct` .idl ファイルに、[エクスポート](../../windows/export.md)属性、`struct`データのみを含める必要があります。

次の例では、C2348 が生成されます。

```
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