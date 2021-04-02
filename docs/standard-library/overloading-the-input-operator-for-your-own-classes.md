---
description: 詳細については、「 &gt; &gt; 独自のクラスの演算子のオーバーロード」を参照してください。
title: 独自クラスのための &gt;&gt; 演算子のオーバーロード
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: d1b89c94a87e94a5bab255ffafb2b049bad4356d
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099483"
---
# <a name="overloading-the--operator-for-your-own-classes"></a>独自クラスのための `>>` 演算子のオーバーロード

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
