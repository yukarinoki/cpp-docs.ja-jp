---
title: is_nothrow_destructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 366b40af45c57d058d918c4c2f21d1b2ba486d35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217327"
---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible クラス

型が破棄可能で、デストラクタ―がスローしないとコンパイラに判明しているかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T* 、破棄可能な型であり、デストラクターは、コンパイラにスローしないと判明します。 それ以外の場合、false を保持します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
