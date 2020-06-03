---
title: CComQIPtrクラス
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: 2b1d8b92fbc5e95a5061956bafc4922d249a6f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327419"
---
# <a name="ccomqiptr-class"></a>CComQIPtrクラス

COM インターフェイス ポインターを管理するためのスマート ポインター クラス。

## <a name="syntax"></a>構文

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
格納するポインターの型を指定する COM インターフェイス。

*ピッド*<br/>
*T*の IID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComQIPtr::CComQIPtr](#ccomqiptr)|コンストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComQIPtr::演算子 =](#operator_eq)|メンバ ポインタにポインタを割り当てます。|

## <a name="remarks"></a>解説

ATL`CComQIPtr`は COM インターフェイス ポインタを管理するために[CComPtr](../../atl/reference/ccomptr-class.md)を[CComPtrBase](../../atl/reference/ccomptrbase-class.md)使用します。 どちらのクラスも、 と`AddRef``Release`の呼び出しを通じて自動的に参照カウントを実行します。 オーバーロードされた演算子は、ポインター操作を処理します。

## <a name="inheritance-hierarchy"></a>継承階層

[コムプトルベース](../../atl/reference/ccomptrbase-class.md)

[Ccomptr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli.h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a>CComQIPtr::CComQIPtr

コンストラクターです。

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>パラメーター

*Lp*<br/>
インターフェイス ポインターを初期化するために使用します。

*T*<br/>
COM インターフェイス。

*ピッド*<br/>
*T*の IID へのポインター。

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a>CComQIPtr::演算子 =

代入演算子。

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>パラメーター

*Lp*<br/>
インターフェイス ポインターを初期化するために使用します。

*T*<br/>
COM インターフェイス。

*ピッド*<br/>
*T*の IID へのポインター。

### <a name="return-value"></a>戻り値

更新された`CComQIPtr`オブジェクトへのポインターを返します。

## <a name="see-also"></a>関連項目

[コムプター::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr::CComQIPtr](#ccomqiptr)<br/>
[クラス](../../atl/reference/ccomptrbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラスをクラス](../../atl/reference/ccomqiptrelementtraits-class.md)
