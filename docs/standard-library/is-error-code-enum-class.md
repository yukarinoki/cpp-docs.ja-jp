---
title: is_error_code_enum クラス
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: bc4ed7cd2e058414448c9366011b9efab97ee3d5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245186"
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum クラス

[error_code](../standard-library/error-code-class.md) 列挙型をテストする型述語を表します。

## <a name="syntax"></a>構文

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Remarks

型 `_Enum` が型 `error_code` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。

ユーザー定義型のこの型に特殊化を追加できます。

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
