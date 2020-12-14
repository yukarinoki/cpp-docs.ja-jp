---
description: '詳細情報: money_base クラス'
title: money_base クラス
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 295984cfed4d6fdd47c772e29765c1484f52d32a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230472"
---
# <a name="money_base-class"></a>money_base クラス

クラスは、クラステンプレート [moneypunct](../standard-library/moneypunct-class.md)のすべての特殊化に共通する列挙型と構造体を記述します。

## <a name="syntax"></a>構文

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>解説

列挙体は、 `part` 構造パターンの配列フィールドの要素で使用可能な値を示します。 の値 `part` は次のとおりです。

- `none` 0個以上の空白に一致するか、何も生成しない場合は。

- `sign` 正または負の符号を一致または生成する場合は。

- `space` 0個以上の空白に一致するか、スペースを生成する場合は。

- `symbol` 通貨記号を一致または生成する場合は。

- `value` 通貨値を一致または生成する場合は。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
