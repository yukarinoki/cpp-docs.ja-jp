---
title: is_error_condition_enum クラス
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 213970d6260eaf55ac1bd678e6317cf2346ed9bc
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245176"
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum クラス

[error_condition](../standard-library/error-condition-class.md) をテストする型述語を表します。

## <a name="syntax"></a>構文

```cpp
template <_Enum>
    class is_error_condition_enum;
```

## <a name="remarks"></a>Remarks

型 `_Enum` が型 `error_condition` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。

ユーザー定義型のこの型に特殊化を追加できます。

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
