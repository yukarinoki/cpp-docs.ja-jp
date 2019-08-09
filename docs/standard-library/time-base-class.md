---
title: time_base クラス
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: 85565dc0c0ec904551eb8dd981cfacc9a2e1f256
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460039"
---
# <a name="timebase-class"></a>time_base クラス

クラスは、テンプレートクラス time_get のファセットの基底クラスとして機能し、列挙`dateorder`型とこの型のいくつかの定数だけを定義します。

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

## <a name="remarks"></a>Remarks

各定数は、日付部分を順序付けるための異なる方法を特徴付けます。 定数は次のとおりです。

- `no_order`特定の順序を指定しません。

- `dmy`1979年12月2日のように、日付、月、年を指定します。

- `mdy`1979年12月2日のように、月、日、年を指定します。

- `ymd`1979/12/2 のように、年、月、日の順に指定します。

- `ydm`1979のように、年、日、月の順序を指定します。2 Dec。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
