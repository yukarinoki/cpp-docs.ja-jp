---
title: コンパイラ エラー C2891 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86d81662cb02fa3c8f6af75009daf4dab9b70196
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016560"
---
# <a name="compiler-error-c2891"></a>コンパイラ エラー C2891

'parameter': テンプレート パラメーターのアドレスを取得できません

左辺値である場合を除きは、テンプレートのパラメーターのアドレスを取得できません。 型パラメーターは、アドレスがないために、左辺値ではありません。 また、左辺値ではない、テンプレート パラメーター リスト内の非型の値には、アドレスがありません。 これは、テンプレート パラメーターとして渡される値がコンパイラによって生成されたテンプレート引数のコピーであるために、コンパイラ エラー C2891、原因となるコードの例です。

```
template <int i> int* f() { return &i; }
```

など、参照型の左辺値であるテンプレート パラメーターが、アドレスを取ることができます。

```
template <int& r> int* f() { return &r; }
```

このエラーを修正するにはなりませんテンプレートのパラメーターのアドレスを左辺値である場合を除き。