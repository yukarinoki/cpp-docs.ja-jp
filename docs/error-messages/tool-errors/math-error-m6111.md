---
title: 数値演算エラー M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: e8abedf6a326a826d0c8ac513b15037c8bf89bce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173692"
---
# <a name="math-error-m6111"></a>数値演算エラー M6111

スタックアンダーフロー

浮動小数点演算の結果、8087/287/387 コプロセッサまたはエミュレーターでスタックアンダーフローが発生しました。

このエラーは、値を返さない `long double` 関数の呼び出しによって発生することがよくあります。 たとえば、次の例では、コンパイルして実行すると、このエラーが生成されます。

```
long double ld() {};
main ()
{
  ld();
}
```

プログラムは終了コード139で終了します。
