---
title: is_aggregate クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 7d979d4e4019ada12b72fb563c0b969fffe2c12d
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268984"
---
# <a name="isaggregate-class"></a>is_aggregate クラス

型が `aggregate` でマークされたクラス型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*クラス型がマークされている`aggregate`、それ以外の場合は false を保持します。 場合*T*クラスの型は、完全な型があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
