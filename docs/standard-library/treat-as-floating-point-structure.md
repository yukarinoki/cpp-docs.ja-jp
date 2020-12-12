---
description: '詳細情報: treat_as_floating_point 構造'
title: treat_as_floating_point 構造体
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 498421d454de1e15ea52282665bcf9ae7d045946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169061"
---
# <a name="treat_as_floating_point-structure"></a>treat_as_floating_point 構造体

`Rep` を浮動小数点型として扱うことができるかどうかを指定します。

## <a name="syntax"></a>構文

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>解説

`Rep` は、特殊化 `treat_as_floating_point<Rep>` が [true_type](../standard-library/type-traits-typedefs.md#true_type) から派生したときにのみ浮動小数点型として処理できます。 クラステンプレートは、ユーザー定義型に特化したものにすることができます。

## <a name="requirements"></a>要件

**ヘッダー:**\<chrono>

**名前空間:** std::chrono

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
