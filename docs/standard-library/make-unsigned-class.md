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
ms.openlocfilehash: 37f121912a13d6e4dac1692d2dab1b5ffd34bd6d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
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
|`T`|変更する型。|

## <a name="remarks"></a>コメント

この型修飾子のインスタンスは、`is_unsigned<T>` が true を保持している場合に `T` になる修飾型を保持します。 それ以外の場合は、`sizeof (T) <= sizeof (ST)` である最小の符号付きの型 `ST` になります。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
