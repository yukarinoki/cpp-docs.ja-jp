---
description: '詳細情報: duration_values 構造'
title: duration_values 構造体
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: 9bf784b0976a06c6d395498084508251d9ebd4bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324476"
---
# <a name="duration_values-structure"></a>duration_values 構造体

[duration](../standard-library/duration-class.md) テンプレート パラメーター `Rep` に対して特定の値を提供します。

## <a name="syntax"></a>構文

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[max](#max)|静的。 `Rep` 型の値の上限を指定します。|
|[min](#min)|静的。 `Rep` 型の値の下限を指定します。|
|[回](#zero)|静的。 `Rep(0)` が返されます。|

## <a name="requirements"></a>要件

**ヘッダー:**\<chrono>

**名前空間:** std::chrono

## <a name="duration_valuesmax"></a><a name="max"></a> duration_values:: max

`Ref` 型の値の上限の境界を返す静的メソッドです。

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>戻り値

実際には、`numeric_limits<Rep>::max()` を返します。

### <a name="remarks"></a>解説

`Rep` がユーザー定義型の場合、戻り値は [duration_values::zero](#zero) より大きい必要があります。

## <a name="duration_valuesmin"></a><a name="min"></a> duration_values:: min

`Ref` 型の値の下限の境界を返す静的メソッドです。

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>戻り値

実際には、`numeric_limits<Rep>::lowest()` を返します。

### <a name="remarks"></a>解説

`Rep` がユーザー定義型の場合、戻り値は [duration_values::zero](#zero) 以下である必要があります。

## <a name="duration_valueszero"></a><a name="zero"></a> duration_values:: 0

`Rep(0)` が返されます。

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>解説

`Rep` がユーザー定義型の場合、戻り値は追加の無限を示す必要があります。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
