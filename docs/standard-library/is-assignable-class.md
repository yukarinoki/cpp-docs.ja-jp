---
title: is_assignable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5666aca2d6a855b64af26d38a1ae834fecec5d6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958466"
---
# <a name="isassignable-class"></a>is_assignable クラス

`From` 型の値を `To` 型に代入できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>パラメーター

オブジェクトの型には、割り当てを受け取る。

オブジェクトの型から値を提供します。

## <a name="remarks"></a>Remarks

評価されていない式 `declval<To>() = declval<From>()` は整形式である必要があります。 両方`From`と`To`完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
