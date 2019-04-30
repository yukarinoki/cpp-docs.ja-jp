---
title: 独自クラスの &gt;&gt; 演算子のオーバーロード
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 86b8af963345c8eb9b3f44cfb16332bc09420bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370724"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>独自クラスの &gt;&gt; 演算子のオーバーロード

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

[入力ストリーム](../standard-library/input-streams.md)<br/>
