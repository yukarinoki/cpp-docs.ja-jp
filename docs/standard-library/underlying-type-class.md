---
title: underlying_type クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: 465383357e6c0306c24fe8325327327c3a3b64c1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454983"
---
# <a name="underlyingtype-class"></a>underlying_type クラス

列挙型の基になる整数型を生成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>Remarks

テンプレート`type`クラスのメンバー typedef は、 *t*が列挙型である場合に、基になる整数型*t*に名前を指定します`type`。それ以外の場合は、メンバー typedef は存在しません。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
