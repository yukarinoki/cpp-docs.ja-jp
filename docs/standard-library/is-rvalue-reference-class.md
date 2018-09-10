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
ms.openlocfilehash: 6bbaa215335a299eee8971b113fdcf3860e9b740
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106497"
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference クラス

型が右辺値参照かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合はこの型述語のインスタンスは true を保持型*Ty*は、[右辺値参照](../cpp/rvalue-reference-declarator-amp-amp.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
