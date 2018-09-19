---
title: コンパイラ エラー C2467 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bab320bfdba9fcbd408771b7859a22fc85fa06e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048776"
---
# <a name="compiler-error-c2467"></a>コンパイラ エラー C2467

匿名 'ユーザー定義型' の無効な宣言

入れ子にされたユーザー定義の型が宣言されました。 これは、ANSI 互換オプションを使用する C ソース コードをコンパイルするときのエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) を有効にします。

次の例では、C2467 が生成されます。

```
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```