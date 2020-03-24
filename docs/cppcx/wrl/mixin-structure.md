---
title: MixIn 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: b302d6e08e401a24b465508d5ddabcae8b16bd8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213695"
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

*導出*<br/>
[Implements](implements-structure.md)構造体から派生した型。

*MixInType*<br/>
基本型。

*hasImplements*<br/>
*MixInType*が、基本型の現在の実装から派生している場合は**true** 。それ以外の場合は**false** 。

## <a name="remarks"></a>解説

クラスが Windows ランタイムとクラスの両方の COM インターフェイスから派生している場合は、まず、クラス宣言リストで Windows ランタイムインターフェイスを一覧表示し、次にすべてのクラシック COM インターフェイスを一覧表示する必要があります。 **MixIn**は、インターフェイスが正しい順序で指定されることを保証します。

## <a name="inheritance-hierarchy"></a>継承階層

`MixIn`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
