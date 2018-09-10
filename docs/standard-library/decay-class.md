---
title: decay クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d3ad5bae067bb9661b6cf475d0831b2b2dfcd2a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099526"
---
# <a name="decay-class"></a>decay クラス

値で渡されように型を生成します。 型を非参照、非定数、非揮発性にします。または、関数からの型または配列型へのポインターを作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
変更する型。

## <a name="remarks"></a>Remarks

型が引数として値で渡されたかのように結果の型を生成するには、decay テンプレートを使います。 テンプレート クラスのメンバー typedef `type` は、次の段階で定義された修飾型を保持します。

- 型 `U` が `remove_reference<T>::type` として定義されます。

- `is_array<U>::value` が true の場合、修飾型 `type` は `remove_extent<U>::type *` になります。

- `is_function<U>::value` が true の場合、修飾型 `type` は `add_pointer<U>::type` になります。

- それ以外の場合、修飾型 `type` は `remove_cv<U>::type` になります。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
