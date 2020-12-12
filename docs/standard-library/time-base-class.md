---
description: '詳細情報: time_base クラス'
title: time_base クラス
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: cad27546109cf8ed6d8314869a3306f238cc6528
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289570"
---
# <a name="time_base-class"></a>time_base クラス

クラスは、列挙型 `dateorder` とこの型のいくつかの定数だけを定義するクラステンプレート time_get のファセットの基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>解説

各定数は、日付部分を順序付けるための異なる方法を特徴付けます。 定数は次のとおりです。

- `no_order` 特定の順序を指定しません。

- `dmy` 1979年12月2日のように、日付、月、年を指定します。

- `mdy` 1979年12月2日のように、月、日、年を指定します。

- `ymd` 1979/12/2 のように、年、月、日の順に指定します。

- `ydm` 1979: 2 Dec のように、年、日、月の順序を指定します。

## <a name="requirements"></a>要件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
