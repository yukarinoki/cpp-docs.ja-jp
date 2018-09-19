---
title: is_trivially_assignable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd0a8bbffd3a6e0f03635b659dd3743e12c9f077
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700766"
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable クラス

`From` 型の値を `To` 型に普通に代入できるかどうかをテストします

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>パラメーター

*目的*<br/>
代入を受け取るオブジェクトの型。

*From*<br/>
値を渡すオブジェクトの型。

## <a name="remarks"></a>Remarks

式 `declval<To>() = declval<From>()` は正しい形式である必要があり、トリビアルでない演算を必要としないことがコンパイラに判明している必要があります。 両方`From`と`To`完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
