---
title: コンパイラ エラー C2801 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2801
dev_langs:
- C++
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d57ee5bf5f5152ef55852c9f9b829bc4a1d17d41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040636"
---
# <a name="compiler-error-c2801"></a>コンパイラ エラー C2801

'operator 演算子' は非静的メンバーである必要があります。

非静的メンバーとしてのみ、次の演算子をオーバー ロードできます。

- 割り当て `=`

- クラス メンバーへのアクセス `->`

- 添字演算子 `[]`

- 関数呼び出し `()`

C2801 の考えられる原因:

- オーバー ロードされた演算子は、クラス、構造体または共用体のメンバーではありません。

- オーバー ロードされた演算子が宣言されて`static`します。

- 次の例では、C2801 が生成されます。

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```