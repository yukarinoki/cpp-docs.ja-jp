---
title: is_trivially_copy_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01c95007f1db1bcaf549398fa8865a9e51fe23d1
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible クラス

型に自明なコピー コンストラクターが含まれるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

## <a name="remarks"></a>コメント

型 `T` が自明なコピー コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

クラス `T` のコピー コンストラクターが自明となるのは、このコピー コンストラクターが暗黙的に宣言されており、クラス `T` に仮想関数も仮想基底も含まれず、クラス `T` のすべての直接基底が自明なコピー コンストラクターを持ち、クラス型の非静的データ メンバーすべてのクラスが自明なコピー コンストラクターを持ち、かつクラスの型配列の非静的データ メンバーすべてでクラスが自明なコピー コンストラクターを持つ場合です。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
