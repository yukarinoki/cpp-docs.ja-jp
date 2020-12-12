---
description: '詳細情報: is_error_code_enum 構造'
title: is_error_code_enum 構造体
ms.date: 11/04/2016
f1_keywords:
- future/std::is_error_code_enum
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
ms.openlocfilehash: 0de1d5562fd59e72e43c5844421f4ce6b30fe7c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231122"
---
# <a name="is_error_code_enum-structure"></a>is_error_code_enum 構造体

[future_errc](../standard-library/future-enums.md#future_errc) が [error_code](../standard-library/error-code-class.md) の格納に適していることを示す特殊化です。

## <a name="syntax"></a>構文

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<future>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
