---
title: is_error_condition_enum クラス
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 1b5b55431db806bb109a58199ad9d2d7c16f38ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612720"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** \<system_error>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
