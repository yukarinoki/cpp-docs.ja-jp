---
title: 数値演算エラー M6111 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95a55ec6b7cdf0b6e4c15bd283dde77c610698fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074826"
---
# <a name="math-error-m6111"></a>数値演算エラー M6111

スタックのアンダー フロー

浮動小数点演算では、8087/287/387 コプロセッサまたはエミュレーター スタック アンダー フローが発生しました。

呼び出しによってこのエラーが原因となった多くの場合、`long double`値を返さない関数。 たとえば、次このエラーを生成コンパイルと実行。

```
long double ld() {};
main ()
{
  ld();
}
```

終了コード 139 でプログラムを終了します。