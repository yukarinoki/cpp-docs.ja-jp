---
description: 詳細については、「Math Error M6111」を参照してください。
title: 数値演算エラー M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 9bf2d620a0df18752b74aaacd4d2415510407f0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244343"
---
# <a name="math-error-m6111"></a>数値演算エラー M6111

スタックアンダーフロー

浮動小数点演算の結果、8087/287/387 コプロセッサまたはエミュレーターでスタックアンダーフローが発生しました。

このエラーは、 **`long double`** 値を返さない関数の呼び出しによって発生することがよくあります。 たとえば、次の例では、コンパイルして実行すると、このエラーが生成されます。

```
long double ld() {};
main ()
{
  ld();
}
```

プログラムは終了コード139で終了します。
