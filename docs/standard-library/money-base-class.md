---
title: money_base クラス
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: b0c77b523dbe31bc5b07ae3d736441880fe04546
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610448"
---
# <a name="moneybase-class"></a>money_base クラス

このクラスは、テンプレート クラス [moneypunct](../standard-library/moneypunct-class.md) のすべての特殊化に共通する列挙型および構造体を表します。

## <a name="syntax"></a>構文

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Remarks

列挙体`part`構造パターンの配列フィールドの要素で指定できる値について説明します。 値`part`は。

- `none` 一致する 0 個以上の空白文字か何も生成しません。

- `sign` 一致するか、正または負の記号を生成します。

- `space` 0 個以上の空白文字と一致するか、空白を生成します。

- `symbol` 一致するか、通貨記号を生成します。

- `value` 一致するか、通貨値を生成します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
