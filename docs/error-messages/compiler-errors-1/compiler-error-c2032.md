---
title: コンパイラ エラー C2032 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab02ca695ec94f25054e3490232b782a46a53a4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064010"
---
# <a name="compiler-error-c2032"></a>コンパイラ エラー C2032

'identifier': 関数は 'structorunion' の構造体/共用体のメンバーであることはできません

構造体または共用体が、c 言語ではありませんが、C++ では許可されているメンバー関数エラーを解決するには、C++ プログラムとしてコンパイルするか、メンバー関数を削除します。

次の例では、C2032 が生成されます。

```
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

考えられる解決方法:

```
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```