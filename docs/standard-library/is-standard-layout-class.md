---
title: is_standard_layout クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d899d9c56ecc8b27b18498de225bbba6f0d110d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852085"
---
# <a name="isstandardlayout-class"></a>is_standard_layout クラス

型が標準レイアウト型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Ty`|照会する型|

## <a name="remarks"></a>コメント

型 `Ty` がメモリ内にメンバー オブジェクトの標準レイアウトを持つクラスである場合、この型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
