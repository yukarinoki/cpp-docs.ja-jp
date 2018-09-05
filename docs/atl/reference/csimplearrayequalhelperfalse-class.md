---
title: CSimpleArrayEqualHelperFalse クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74bc3326c50f1b460fc212074b7ca34dec518c76
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765636"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse クラス

このクラスのヘルパーは、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラス。

## <a name="syntax"></a>構文

```
template <class T>  
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>パラメーター

*T*  
派生クラスです。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(静的)False を返します。|

## <a name="remarks"></a>Remarks

この特性クラスを補完するは、`CSimpleArray`クラス。 False、およびさらに、返しますは呼び出しは常に it`ATLASSERT`引数が参照されている場合は false。 等しいかどうかテストが十分に定義されていない場合、このクラスは、ほとんどのメソッドに対して正常に動作しなどの比較に依存する方法を明確に定義された方法で失敗する可能性が要素を含む配列[CSimpleArray:。検索](../../atl/reference/csimplearray-class.md#find)します。

## <a name="requirements"></a>要件

**ヘッダー:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelperFalse::IsEqual

false を返します。

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>戻り値

false を返します。

### <a name="remarks"></a>Remarks

このメソッドは常に false を返し、呼び出されます`ATLASSERT`引数は参照されている場合は false。 目的は、`CSimpleArrayEqualHelperFalse::IsEqual`を強制的に比較を使用して、等しいかどうかテストが適切に定義されていないときに、明確に定義された方法で失敗するメソッド。

## <a name="see-also"></a>関連項目

[CSimpleArrayEqualHelper クラス](../../atl/reference/csimplearrayequalhelper-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
