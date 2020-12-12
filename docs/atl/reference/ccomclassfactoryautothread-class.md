---
description: '詳細情報: CComClassFactoryAutoThread クラス'
title: CComClassFactoryAutoThread クラス
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: 9d25303d4d40f695c68fdf09aae7d56e6f1e5fb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152283"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread クラス

このクラスは、 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) インターフェイスを実装し、複数のアパートメントでオブジェクトを作成できるようにします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComClassFactoryAutoThread:: CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|
|[CComClassFactoryAutoThread:: LockServer](#lockserver)|メモリ内のクラスファクトリをロックします。|

## <a name="remarks"></a>解説

`CComClassFactoryAutoThread` は [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)に似ていますが、複数のアパートメントでオブジェクトを作成することができます。 このサポートを利用するには、 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)から EXE モジュールを派生させます。

ATL オブジェクトは通常、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラスファクトリを取得します。 このクラスには、 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラスファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)が含まれています。 を使用するには `CComClassFactoryAutoThread` 、オブジェクトのクラス定義で [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a> CComClassFactoryAutoThread:: CreateInstance

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイスポインターを取得します。

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
からオブジェクトが集計の一部として作成されている場合、 *pUnkOuter* は外側の unknown である必要があります。 それ以外の場合、 *pUnkOuter* は NULL である必要があります。

*riid*<br/>
から要求されたインターフェイスの IID。 *PUnkOuter* が NULL 以外の場合、 *riid* はである必要があり `IID_IUnknown` ます。

*ppvObj*<br/>
入出力 *Riid* によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppvObj* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

モジュールが [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)から派生した場合、は `CreateInstance` まず、関連付けられているアパートメントにオブジェクトを作成するスレッドを選択します。

## <a name="ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a> CComClassFactoryAutoThread:: LockServer

とをそれぞれ呼び出して、モジュールのロックカウントをインクリメントおよびデクリメントし `_Module::Lock` `_Module::Unlock` ます。

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*fLock*<br/>
からTRUE の場合、ロック数がインクリメントされます。それ以外の場合は、ロック数が減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

を使用する場合 `CComClassFactoryAutoThread` 、 `_Module` 通常は [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)のグローバルインスタンスを参照します。

を呼び出すこと `LockServer` で、クライアントは、複数のオブジェクトをすばやく作成できるように、クラスファクトリに保持できます。

## <a name="see-also"></a>関連項目

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
