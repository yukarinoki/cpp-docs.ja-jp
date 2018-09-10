---
title: is_lvalue_reference クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecd065ff80b5c45bca863534e28bc467b3a4105c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105381"
---
# <a name="islvaluereference-class"></a>is_lvalue_reference クラス

型が左辺値参照かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合はこの型述語のインスタンスは true を保持型*Ty*または関数の場合、それ以外の場合は false を保持するオブジェクトへの参照です。 なお*Ty*右辺値参照ができない可能性があります。 右辺値の詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」をご覧ください。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
