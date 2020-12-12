---
description: 詳細については、「MixIn 構造」を参照してください。
title: MixIn 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: a438fb6846ae6ba88aaaa968d7b94e8d6636c4aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209387"
---
# <a name="mixin-structure"></a>MixIn 構造体

ランタイム クラスが Windows ランタイム インターフェイス (存在する場合) から派生し、次にクラシック COM インターフェイスから派生していることを確認します。

## <a name="syntax"></a>構文

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>パラメーター

*派生*<br/>
[Implements](implements-structure.md)構造体から派生した型。

*MixInType*<br/>
基本型。

*hasImplements*<br/>
**`true`***MixInType* が現在の実装から派生した場合、基本データ型はです。**`false`** それ以外の場合は。

## <a name="remarks"></a>解説

クラスが Windows ランタイムとクラスの両方の COM インターフェイスから派生している場合は、まず、クラス宣言リストで Windows ランタイムインターフェイスを一覧表示し、次にすべてのクラシック COM インターフェイスを一覧表示する必要があります。 **MixIn** は、インターフェイスが正しい順序で指定されることを保証します。

## <a name="inheritance-hierarchy"></a>継承階層

`MixIn`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
