---
title: money_base クラス
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 5b19635cf4d2cce58ec50226c463a075cfac5b0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455560"
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

列挙`part`体は、構造パターンの配列フィールドの要素で使用可能な値を示します。 の`part`値は次のとおりです。

- `none`0個以上の空白に一致するか、何も生成しない場合は。

- `sign`正または負の符号を一致または生成する場合は。

- `space`0個以上の空白に一致するか、スペースを生成する場合は。

- `symbol`通貨記号を一致または生成する場合は。

- `value`通貨値を一致または生成する場合は。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
