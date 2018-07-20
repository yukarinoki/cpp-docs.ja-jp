---
title: is_nothrow_assignable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 424fcf5b960182326dc1192d8d60f168ead59d98
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965416"
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable クラス

値かどうかをテスト*から*型に割り当てることができます*に*型および割り当てがスローしないと判明します。

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>パラメーター

*To*代入を受け取るオブジェクトの型。

*From*値を提供するオブジェクトの型。

## <a name="remarks"></a>Remarks

式 `declval<To>() = declval<From>()` は正しい形式である必要があり、スローしないことがコンパイラに判明している必要があります。 両方*から*と*に*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
