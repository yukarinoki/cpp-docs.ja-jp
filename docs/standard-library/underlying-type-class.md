---
description: '詳細情報: underlying_type クラス'
title: underlying_type クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: e717abe854f13fc96926deba1d4bf177529618cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132705"
---
# <a name="underlying_type-class"></a>underlying_type クラス

列挙型の基になる整数型を生成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

`type` *T* が列挙型である場合、クラステンプレートのメンバー typedef は、基になる整数型 *t* に名前を指定します。それ以外の場合は、メンバー typedef は存在しません `type` 。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
