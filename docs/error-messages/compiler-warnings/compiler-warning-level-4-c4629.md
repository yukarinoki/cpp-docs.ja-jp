---
description: '詳細情報: コンパイラの警告 (レベル 4) C4629'
title: コンパイラの警告 (レベル 4) C4629
ms.date: 11/04/2016
f1_keywords:
- C4629
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
ms.openlocfilehash: b357b72ca95682c33d3f4019d4663593c5c5ee8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134174"
---
# <a name="compiler-warning-level-4-c4629"></a>コンパイラの警告 (レベル 4) C4629

digraph が使用されました。文字のシーケンス 'digraph' はトークン 'char' として解釈されます。(これが意図でない場合は、2 文字の間にスペースを挿入してください)

コンパイラで [/Za](../../build/reference/za-ze-disable-language-extensions.md)を使用すると、digraph の検出時に警告が表示されます。

次の例では C4629 が生成されます。

```cpp
// C4629.cpp
// compile with: /Za /W4
int main()
<%   // C4629 <% digraph for {
}
```
