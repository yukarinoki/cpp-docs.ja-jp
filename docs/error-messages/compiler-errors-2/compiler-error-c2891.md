---
description: 詳細については、「コンパイラエラー C2891」を参照してください。
title: コンパイラ エラー C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: e546340d0ba035da50dd36b18b870b565b6e1bc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337440"
---
# <a name="compiler-error-c2891"></a>コンパイラ エラー C2891

' parameter ': テンプレートパラメーターのアドレスを受け取ることはできません

左辺値でない限り、テンプレートパラメーターのアドレスを取得することはできません。 型パラメーターは、アドレスがないため、左辺値ではありません。 左辺値以外のテンプレートパラメーターリスト内の非型の値には、アドレスがありません。 これは、テンプレートパラメーターとして渡された値がコンパイラによって生成されるテンプレート引数のコピーであるため、コンパイラエラー C2891 を発生させるコードの例です。

```
template <int i> int* f() { return &i; }
```

参照型などの左辺値であるテンプレートパラメーターは、アドレスを取得できます。

```
template <int& r> int* f() { return &r; }
```

このエラーを修正するには、テンプレートパラメーターが左辺値でない限り、そのアドレスを取得しないでください。
