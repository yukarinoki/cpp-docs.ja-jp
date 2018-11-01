---
title: コンパイラ エラー C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 90016b65d4ddd58da3fb3c5ab6d81322dc0ef394
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566726"
---
# <a name="compiler-error-c2480"></a>コンパイラ エラー C2480

'identifier': 'thread' は有効な静的データ項目に対してのみ

使用することはできません、`thread`属性または関数宣言または定義で、自動変数、非静的データ メンバー、関数のパラメーターを使用します。

使用して、`thread`グローバル変数、静的データ メンバー、およびローカル静的変数の属性。

次の例では、C2480 が生成されます。

```
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```