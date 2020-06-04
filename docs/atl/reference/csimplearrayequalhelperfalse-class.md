---
title: クラスを返します。
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 5eca3145d64895e34b599fbf83834af142b65973
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330893"
---
# <a name="csimplearrayequalhelperfalse-class"></a>クラスを返します。

このクラスは、クラスのヘルパー[です](../../atl/reference/csimplearray-class.md)。

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
|[を返します。](#isequal)|(静的)false を返します。|

## <a name="remarks"></a>解説

この特徴クラスはクラスを補完する`CSimpleArray`クラスです。 常に false を返し、さらに、`ATLASSERT`参照される場合は false の引数を指定して呼び出します。 等値テストが十分に定義されていない状況では、このクラスは、要素を含む配列がほとんどのメソッドで正しく動作しますが[、CSimpleArray::Find](../../atl/reference/csimplearray-class.md#find)などの比較に依存するメソッドに対して明確に定義された方法で失敗することを可能にします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a>を返します。

false を返します。

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>戻り値

false を返します。

### <a name="remarks"></a>解説

このメソッドは常に false を`ATLASSERT`返し、参照されている場合は false の引数を指定して呼び出します。 等価性テスト`CSimpleArrayEqualHelperFalse::IsEqual`が適切に定義されていない場合に、比較を使用するメソッドが明確に定義された方法で失敗するように強制することを目的とします。

## <a name="see-also"></a>関連項目

[クラスを配列します。](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
