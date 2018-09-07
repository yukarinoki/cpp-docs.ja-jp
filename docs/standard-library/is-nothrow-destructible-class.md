---
title: is_nothrow_destructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 245dd02a8077d652baae87d678122830f95869bc
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110345"
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

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
