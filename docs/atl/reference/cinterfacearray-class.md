---
description: '詳細情報: CInterfaceArray クラス'
title: CInterfaceArray クラス
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: 6dbe382682b8411d7562d1d0ff75f0ef587396f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141545"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray クラス

このクラスには、COM インターフェイスポインターの配列を構築するときに役立つメソッドが用意されています。

## <a name="syntax"></a>構文

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*I*<br/>
格納するポインターの型を指定する COM インターフェイス。

*piid*<br/>
*I* の IID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CInterfaceArray:: CInterfaceArray](#cinterfacearray)|インターフェイス配列のコンストラクター。|

## <a name="remarks"></a>解説

このクラスは、COM インターフェイスポインターの配列を作成するためのコンストラクターと派生メソッドを提供します。 リストが必要な場合は、 [Cinterfacelist](../../atl/reference/cinterfacelist-class.md) を使用します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a> CInterfaceArray:: CInterfaceArray

コンストラクターです。

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>解説

スマートポインターの配列を初期化します。

## <a name="see-also"></a>関連項目

[CAtlArray クラス](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
