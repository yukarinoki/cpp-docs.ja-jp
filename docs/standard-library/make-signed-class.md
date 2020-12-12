---
description: '詳細情報: make_signed クラス'
title: make_signed クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: 2f11fe3223e6193613772d2c4abbf0182215a17d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277558"
---
# <a name="make_signed-class"></a>make_signed クラス

サイズが型以上の型または最小の符号付きの型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

型修飾子のインスタンスは、が true を保持している場合は *T* である修飾型を保持し `is_signed<T>` ます。 それ以外の場合は、`sizeof (T) <= sizeof (UT)` である最小の符号なしの型 `UT` になります。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
