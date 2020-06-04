---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: c190f495e284e98b27a6c6dc2099a8dfc4b1693d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327613"
---
# <a name="ccomobjectnolock-class"></a>クラス

このクラスは`IUnknown`、非集約オブジェクトを実装しますが、コンストラクターのモジュール ロック カウントはインクリメントしません。

## <a name="syntax"></a>構文

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
[CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCom オブジェクトノロック::CCom オブジェクトノロック](#ccomobjectnolock)|コンストラクターです。|
|[CCom オブジェクトノロック::~CCom オブジェクトノロック](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCom オブジェクトノロック::追加参照](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[をクリックします。](#queryinterface)|要求されたインターフェイスへのポインターを返します。|
|[CComオブジェクトノロック::リリース](#release)|オブジェクトの参照カウントを減算します。|

## <a name="remarks"></a>解説

`CComObjectNoLock`は、非集約オブジェクトに対して[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装するという点で[CComObject](../../atl/reference/ccomobject-class.md)に似ています。ただし、`CComObjectNoLock`コンストラクター内のモジュール ロックカウントはインクリメントしません。

ATL`CComObjectNoLock`はクラス ファクトリに内部的に使用します。 一般に、このクラスを直接使用することはできません。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomobjectnolockaddref"></a><a name="addref"></a>CCom オブジェクトノロック::追加参照

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="ccomobjectnolock"></a>CCom オブジェクトノロック::CCom オブジェクトノロック

コンストラクターです。 [CComObject](../../atl/reference/ccomobject-class.md)とは異なり、モジュールロックカウントはインクリメントしません。

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>パラメーター

<em>void\*</em><br/>
[in]この名前のないパラメーターは使用されません。 他`CComXXXObjectXXX`のコンストラクタとの対称性のために存在します。

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="dtor"></a>CCom オブジェクトノロック::~CCom オブジェクトノロック

デストラクターです。

```
~CComObjectNoLock();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出します。

## <a name="ccomobjectnolockqueryinterface"></a><a name="queryinterface"></a>をクリックします。

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの識別子。

*オブジェクト*<br/>
[アウト]*iid*で識別されるインターフェイス ポインタへのポインタ。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObject*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomobjectnolockrelease"></a><a name="release"></a>CComオブジェクトノロック::リリース

オブジェクトの参照カウントを減算します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドでは`Release`、診断やテストに役立つ値を返します。 非デバッグ ビルドでは、`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
