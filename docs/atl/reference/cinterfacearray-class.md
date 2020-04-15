---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: e6efe31989b06f0977ecff156a8f64053dc64ad1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326796"
---
# <a name="cinterfacearray-class"></a>クラス

このクラスには、COM インターフェイス ポインターの配列を構築するときに役立つメソッドが用意されています。

## <a name="syntax"></a>構文

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*私*<br/>
格納するポインターの型を指定する COM インターフェイス。

*ピッド*<br/>
I の IID への*ポインタ。*

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の手順を実行します。](#cinterfacearray)|インターフェイス配列のコンストラクター。|

## <a name="remarks"></a>解説

このクラスは、COM インターフェイス ポインターの配列を作成するためのコンストラクターと派生メソッドを提供します。 リストが必要な場合は[、CInterfaceList](../../atl/reference/cinterfacelist-class.md)を使用します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a>次の手順を実行します。

コンストラクターです。

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>解説

スマート ポインター配列を初期化します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtrクラス](../../atl/reference/ccomqiptr-class.md)<br/>
[クラスをクラス](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
