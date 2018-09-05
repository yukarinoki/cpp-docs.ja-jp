---
title: CInterfaceArray クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64b6266ac31e2d6dec6eabc847b67b080b250837
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751424"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray クラス

このクラスは、COM インターフェイス ポインターの配列を構築するときに役立つメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*I*  
COM インターフェイスを格納するポインターの種類を指定します。

*piid*  
ポインターの IID を*は*します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|インターフェイスの配列のコンス トラクター。|

## <a name="remarks"></a>Remarks

このクラスは、コンス トラクターおよび COM インターフェイス ポインターの配列を作成するための派生メソッドを提供します。 使用[CInterfaceList](../../atl/reference/cinterfacelist-class.md)一覧が必要な場合。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

##  <a name="cinterfacearray"></a>  CInterfaceArray::CInterfaceArray

コンストラクターです。

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>Remarks

スマート ポインターの配列を初期化します。

## <a name="see-also"></a>関連項目

[CAtlArray クラス](../../atl/reference/catlarray-class.md)   
[CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)   
[CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
