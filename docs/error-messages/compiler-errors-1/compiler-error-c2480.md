---
title: コンパイラ エラー C2480 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b5d8f80293c05b651ad01e725ae501288005dfe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102587"
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