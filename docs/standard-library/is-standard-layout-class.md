---
title: is_standard_layout クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: fba77be22796f3cb5495543d262dd270ac13d598
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560596"
---
# <a name="is_standard_layout-class"></a>is_standard_layout クラス

型が標準レイアウト型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型

## <a name="remarks"></a>解説

型 *Ty* がメモリ内にメンバーオブジェクトの標準レイアウトを持つクラスである場合、この型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
