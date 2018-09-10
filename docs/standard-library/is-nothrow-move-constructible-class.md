---
title: is_nothrow_move_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bba1380df8acf85aaf6729b5a6bf80465439773d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101652"
---
# <a name="isnothrowmoveconstructible-class"></a>is_nothrow_move_constructible クラス

型に **nothrow** 移動コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty* nothrow 移動コンス トラクターを持つ、それ以外の場合は false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
