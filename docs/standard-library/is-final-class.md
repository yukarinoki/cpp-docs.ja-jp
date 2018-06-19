---
title: is_final クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_final
dev_langs:
- C++
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b3d2c37b73d79619aeb16e7b1b81ad71819b09b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844056"
---
# <a name="isfinal-class"></a>is_final クラス

型が `final` でマークされたクラス型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

## <a name="remarks"></a>コメント

型 `T` が `final` でマークされたクラス型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 `T` がクラス型の場合、完全な型である必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[final 指定子](../cpp/final-specifier.md)<br/>
