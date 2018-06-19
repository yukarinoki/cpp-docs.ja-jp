---
title: is_copy_assignable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_copy_assignable
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9c63aa54675bd0b1d5a52a1c0a9d80a73f53290
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842821"
---
# <a name="iscopyassignable-class"></a>is_copy_assignable クラス

割り当て時に型をコピーできるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

## <a name="remarks"></a>コメント

型 `Ty` がコピー代入演算子を持つクラスの場合、型 predicate のインスタンスは true を保持します。それ以外の場合は false を保持します。 is_assignable\<Ty&, const Ty&> に相当します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
