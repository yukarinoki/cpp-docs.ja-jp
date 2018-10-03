---
title: time_base クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4e371bd242dff337450fd87527455b50556afc
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235777"
---
# <a name="timebase-class"></a>time_base クラス

クラスは、time_get テンプレート クラスの列挙型だけを定義するファセットの基底クラスとして機能`dateorder`とこの型の複数の定数。

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

- `no_order` 特定の順序は指定されません。

- `dmy` 注文日、月、年、2 December 1979 のように指定します。

- `mdy` 注文月、日、その後、December 2, 1979年のように、年を指定します。

- `ymd` 注文年、月、日、1979/12/2 のように指定します。

- `ydm` 注文年、日、その後、1979: 2 Dec のように、1 か月を指定します。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
