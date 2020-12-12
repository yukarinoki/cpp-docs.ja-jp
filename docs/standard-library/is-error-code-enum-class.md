---
description: '詳細情報: is_error_code_enum クラス'
title: is_error_code_enum クラス
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 359f15c3d809435df81408a721a0c9ad11c1e7e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323756"
---
# <a name="is_error_code_enum-class"></a>is_error_code_enum クラス

[error_code](../standard-library/error-code-class.md) 列挙型をテストする型述語を表します。

## <a name="syntax"></a>構文

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>解説

型 `_Enum` が型 `error_code` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。

ユーザー定義型のこの型に特殊化を追加できます。

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
