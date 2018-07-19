---
title: make_unsigned クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f379500f9455ed9ad9a581966e0f8ed7bfed13f7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953915"
---
# <a name="makeunsigned-class"></a>make_unsigned クラス

サイズが型以上の型または最小の符号なしの型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*T*|変更する型。|

## <a name="remarks"></a>Remarks

型修飾子のインスタンスを保持する、修飾型である*T*場合`is_unsigned<T>`true を保持します。 それ以外の場合は、`sizeof (T) <= sizeof (ST)` である最小の符号付きの型 `ST` になります。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
