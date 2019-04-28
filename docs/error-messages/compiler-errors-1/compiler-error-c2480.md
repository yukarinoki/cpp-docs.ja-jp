---
title: コンパイラ エラー C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 90016b65d4ddd58da3fb3c5ab6d81322dc0ef394
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187615"
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