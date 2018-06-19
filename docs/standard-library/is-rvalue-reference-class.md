---
title: is_rvalue_reference クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b8645e9ac8a8d3e8f40590105df234b4ef55bac
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857065"
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference クラス

型が右辺値参照かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

## <a name="remarks"></a>コメント

型 `Ty` が [rvalue 参照](../cpp/rvalue-reference-declarator-amp-amp.md)である場合、この型述語のインスタンスは true を保持します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
