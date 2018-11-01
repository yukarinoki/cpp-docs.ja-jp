---
title: is_trivially_destructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_destructible
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
ms.openlocfilehash: 61d626c308338595a64031a45908ab299ae1a957
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656067"
---
# <a name="istriviallydestructible-class"></a>is_trivially_destructible クラス

型が普通に破棄可能であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*破棄可能な型であり、デストラクターが自明でない演算を使用しないようにコンパイラに判明します。 それ以外の場合、false を保持します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
