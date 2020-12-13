---
description: '詳細情報: CInterfaceList クラス'
title: CInterfaceList クラス
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 2612ba4700466bb877f84978c55bfd018f1dd286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141532"
---
# <a name="cinterfacelist-class"></a>CInterfaceList クラス

このクラスには、COM インターフェイスポインターのリストを構築するときに役立つメソッドが用意されています。

## <a name="syntax"></a>構文

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceList:: CInterfaceList](#cinterfacelist)|インターフェイスリストのコンストラクター。|

## <a name="remarks"></a>解説

このクラスは、COM インターフェイスポインターのリストを作成するためのコンストラクターと派生メソッドを提供します。 配列が必要な場合は、 [Cinterfacearray](../../atl/reference/cinterfacearray-class.md) を使用します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a> CInterfaceList:: CInterfaceList

インターフェイスリストのコンストラクター。

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
ブロックサイズ。既定値は10です。

### <a name="remarks"></a>解説

ブロックサイズは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。

## <a name="see-also"></a>関連項目

[CAtlList クラス](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
