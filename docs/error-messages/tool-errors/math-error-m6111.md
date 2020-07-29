---
title: 数値演算エラー M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 986c0e53edcddfc47eb9ba970f3c32385e0a57d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225190"
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
