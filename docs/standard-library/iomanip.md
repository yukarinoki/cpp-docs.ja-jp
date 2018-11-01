---
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: f6470f98495362149b4e99c6d1e3fe521800438b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487920"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

含める、`iostreams`標準ヘッダー \<iomanip > 複数のマニピュレーターを定義するそのそれぞれ 1 つの引数を受け取ります。

## <a name="syntax"></a>構文

```cpp
#include <iomanip>

```

## <a name="remarks"></a>Remarks

これらのマニピュレーターの各と呼ばれる、未指定の型を返します`T1`を通じて`T10`、両方をオーバー ロード`basic_istream` \< **Elem**、 **Tr** >`::`[演算子 >>](../standard-library/istream-operators.md#op_gt_gt)と`basic_ostream` \< **Elem**、 **Tr** > `::` [演算子 <<](../standard-library/ostream-operators.md#op_lt_lt)します。

### <a name="manipulators"></a>マニピュレーター

|||
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|必要に応じて国際化の形式で、金額を取得します。|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|指定された形式を使用して、時間構造体内の時間を取得します。|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|必要に応じて国際化の形式で、金額を提供します。|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|時間構造体内の時間と、使用する書式設定文字列を提供します。|
|[quoted](../standard-library/iomanip-functions.md#quoted)|挿入演算子と抽出演算子を使用する文字列の便利なラウンド トリップを有効にします。|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|指定したフラグをクリアします。|
|[setbase](../standard-library/iomanip-functions.md#setbase)|整数の基数を設定します。|
|[setfill](../standard-library/iomanip-functions.md#setfill)|右揃えの表示でスペースを埋めるために使用する文字を設定します。|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|指定したフラグを設定します。|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|浮動小数点値の有効桁数を設定します。|
|[setw](../standard-library/iomanip-functions.md#setw)|表示フィールドの幅を指定します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
