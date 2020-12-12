---
description: '詳細情報: is_null_pointer クラス'
title: is_null_pointer クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_null_pointer
helpviewer_keywords:
- is_null_pointer
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
ms.openlocfilehash: 91a8b6a27668af72d7641ce1fe36dafc119f5aa7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230667"
---
# <a name="is_null_pointer-class"></a>is_null_pointer クラス

型が std::nullptr_t であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_null_pointer;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型が *T* の場合、型の述語のインスタンスは true `std::nullptr_t` を保持します。それ以外の場合は、false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
