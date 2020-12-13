---
description: 詳細については、「 &gt; &gt; 独自のクラスの演算子のオーバーロード」を参照してください。
title: 独自クラスのための &gt;&gt; 演算子のオーバーロード
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 4de7c16dd1c42f85f169da50f11a514eb245b47c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340854"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>独自クラスのための &gt;&gt; 演算子のオーバーロード

入力ストリームは、標準型に抽出 (`>>`) 演算子を使用します。 独自の型に同様の抽出演算子を記述できます。空白を正確に使用することにより、演算子は適切に機能します。

ここでは、前に示した `Date` クラスの抽出演算子の例を示します。

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)
