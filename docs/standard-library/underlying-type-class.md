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
ms.openlocfilehash: 4f45af807b37294b87920b6fabac18647f170025
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="underlyingtype-class"></a>underlying_type クラス

列挙型の基になる整数型を生成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>パラメーター

`T` 変更する型。

## <a name="remarks"></a>コメント

`T` が列挙型の場合、テンプレート クラスのメンバー typedef `type` は `T` の基になる整数型に名前を付けます。それ以外の場合はメンバー typedef `type` はありません。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
