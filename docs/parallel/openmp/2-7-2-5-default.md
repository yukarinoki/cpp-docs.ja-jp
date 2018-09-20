---
title: 2.7.2.5 既定の |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 047110fe80d15d0ff3d979eeec8abf3e42dc35f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401564"
---
# <a name="2725-default"></a>2.7.2.5 default

**既定**句に変数のデータ共有属性の影響を与えるユーザーを使用できます。 構文、**既定**句を次に示します。

```
default(shared | none)
```

指定する**default(shared)** に現在表示されている各変数を明示的に一覧表示するのと同じですが、**共有**句である場合を除き**threadprivate**または**短所**`t`-修飾します。 明示的ながない場合は、**既定**句では、既定の動作と同じだ場合**default(shared)** 指定されました。

指定する**default(none)** parallel コンストラクトの構文範囲内の変数への参照をすべて true に設定で、次の少なくとも 1 つなければならないことが必要です。

- 変数は、参照を含んでいる構造のデータ共有属性句で明示的に一覧表示します。

- 変数は、parallel コンストラクト内で宣言されています。

- 変数が**threadprivate**します。

- 変数が、 **const**-型を修飾します。

- 変数が for ループ コントロール変数を**の**直後に続くループ、**の**または**の並列**ディレクティブ、および変数の参照がループ内で表示されます.

変数を指定する、 **firstprivate**、 **lastprivate**、または**削減**句に含まれているディレクティブの変数への暗黙的な参照が、それを囲むコンテキスト。 このような暗黙的な参照は、上記の要件の対象も。

1 つだけ**既定**句で指定できる、**並列**ディレクティブ。

変数の既定のデータ共有属性を使用してオーバーライドできます、**プライベート**、 **firstprivate**、 **lastprivate**、**削減**、および**共有**句は、次の例に示すようにします。

```
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```