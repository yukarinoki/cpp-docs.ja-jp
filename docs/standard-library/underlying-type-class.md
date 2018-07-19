---
title: underlying_type クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b3f796d5039900b591c219c840d1aef94d23e8f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957582"
---
# <a name="underlyingtype-class"></a>underlying_type クラス

列挙型の基になる整数型を生成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>パラメーター

*T*  
 変更する型。

## <a name="remarks"></a>Remarks

`type`テンプレート クラスのメンバー typedef 名の基になる整数型*T*、 *T*列挙型は、それ以外の場合はメンバー typedef `type`。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
