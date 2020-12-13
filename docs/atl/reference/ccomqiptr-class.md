---
description: '詳細情報: CComQIPtr クラス'
title: CComQIPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: e5af938cd7b2bbae3b091eac5323d3455ce1cf02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142325"
---
# <a name="ccomqiptr-class"></a>CComQIPtr クラス

COM インターフェイスポインターを管理するためのスマートポインタークラス。

## <a name="syntax"></a>構文

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
格納するポインターの型を指定する COM インターフェイス。

*piid*<br/>
*T* の IID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComQIPtr:: CComQIPtr](#ccomqiptr)|コンストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComQIPtr:: operator =](#operator_eq)|メンバーポインターにポインターを割り当てます。|

## <a name="remarks"></a>解説

ATL では `CComQIPtr` 、と [CComPtr](../../atl/reference/ccomptr-class.md) を使用して COM インターフェイスポインターを管理します。どちらも [CComPtrBase](../../atl/reference/ccomptrbase-class.md)から派生します。 両方のクラスは、との呼び出しによって自動参照カウントを実行し `AddRef` `Release` ます。 オーバーロードされた演算子はポインター操作を処理します。

## <a name="inheritance-hierarchy"></a>継承階層

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>要件

**ヘッダー:** atlcomcli. h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a> CComQIPtr:: CComQIPtr

コンストラクターです。

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>パラメーター

*世代*<br/>
インターフェイスポインターを初期化するために使用されます。

*T*<br/>
COM インターフェイス。

*piid*<br/>
*T* の IID へのポインター。

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a> CComQIPtr:: operator =

代入演算子。

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>パラメーター

*世代*<br/>
インターフェイスポインターを初期化するために使用されます。

*T*<br/>
COM インターフェイス。

*piid*<br/>
*T* の IID へのポインター。

### <a name="return-value"></a>戻り値

更新されたオブジェクトへのポインターを返し `CComQIPtr` ます。

## <a name="see-also"></a>関連項目

[CComPtr:: CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase クラス](../../atl/reference/ccomptrbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)
