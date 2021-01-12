---
description: '詳細情報: &lt; iomanip&gt;'
title: '&lt;iomanip&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iomanip>
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
ms.openlocfilehash: 2042ab5fb2ac9797d05d81056e65db202b4d6595
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126482"
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;

`iostreams` 標準ヘッダー \<iomanip> をインクルードして、それぞれが単一の引数を受け取る複数のマニピュレーターを定義します。

## <a name="syntax"></a>構文

```cpp
#include <iomanip>
```

## <a name="remarks"></a>解説

これらの各マニピュレーターは、 `T1` `T10` `basic_istream` \<**Elem**, **Tr**> `::` [演算子>>](../standard-library/istream-operators.md#op_gt_gt)と `basic_ostream` \<**Elem**, **Tr**> `::` [演算子<<](../standard-library/ostream-operators.md#op_lt_lt)の両方をオーバーロードする、を通じて指定されていない型を返します。

### <a name="manipulators"></a>マニピュレーター

|名前|説明|
|-|-|
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|必要に応じて国際化の形式で、金額を取得します。|
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|指定された形式を使用して、時間構造体内の時間を取得します。|
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|必要に応じて国際化の形式で、金額を提供します。|
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|時間構造体内の時間と、使用する書式設定文字列を提供します。|
|[引用符](../standard-library/iomanip-functions.md#quoted)|挿入演算子と抽出演算子を使用する文字列の便利なラウンド トリップを有効にします。|
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|指定したフラグをクリアします。|
|[setbase](../standard-library/iomanip-functions.md#setbase)|整数の基数を設定します。|
|[setfill](../standard-library/iomanip-functions.md#setfill)|右揃えの表示でスペースを埋めるために使用する文字を設定します。|
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|指定したフラグを設定します。|
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|浮動小数点値の有効桁数を設定します。|
|[setw](../standard-library/iomanip-functions.md#setw)|表示フィールドの幅を指定します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
