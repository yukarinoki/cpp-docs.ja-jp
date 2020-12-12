---
description: '詳細情報: CSimpleArrayEqualHelperFalse クラス'
title: CSimpleArrayEqualHelperFalse クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 196f7873f72799408a629bc784cb343966801d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140726"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse クラス

このクラスは、 [CSimpleArray](../../atl/reference/csimplearray-class.md) クラスのヘルパーです。

## <a name="syntax"></a>構文

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生クラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse:: IsEqual](#isequal)|雑音False を返します。|

## <a name="remarks"></a>解説

この特徴クラスは、クラスを補完するクラスです `CSimpleArray` 。 これは常に false を返し、さらに、が `ATLASSERT` 参照されている場合は、引数が false の引数を指定してを呼び出します。 等値テストが十分に定義されていない場合、このクラスを使用すると、要素を含む配列をほとんどのメソッドで正しく動作させることができますが、 [CSimpleArray:: Find](../../atl/reference/csimplearray-class.md#find)などの比較に依存するメソッドでは、適切に定義された方法では失敗します。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelperFalse:: IsEqual

false を返します。

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>戻り値

false を返します。

### <a name="remarks"></a>解説

このメソッドは常に false を返し、参照されて `ATLASSERT` いる場合は false の引数を指定してを呼び出します。 の目的は、 `CSimpleArrayEqualHelperFalse::IsEqual` 等値テストが適切に定義されていない場合に、比較を使用してメソッドを明確に定義された方法で失敗させることです。

## <a name="see-also"></a>関連項目

[CSimpleArrayEqualHelper クラス](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
