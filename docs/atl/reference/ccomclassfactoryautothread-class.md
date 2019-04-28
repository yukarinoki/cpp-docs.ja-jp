---
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
ms.openlocfilehash: 473e697dfb0203b52713fcfb359ec4f56138f560
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246461"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread クラス

このクラスは、実装、 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイス、およびオブジェクトを複数のアパートメントを作成できます。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

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
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|指定した CLSID のオブジェクトを作成します。|
|[CComClassFactoryAutoThread::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|

## <a name="remarks"></a>Remarks

`CComClassFactoryAutoThread` ような[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)が複数のアパートメント内に作成するオブジェクトを許可します。 このサポートを利用する、EXE のモジュールから派生させる[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。

ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言する[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactoryAutoThread`、指定、 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)オブジェクトのクラス定義でマクロ。 例えば:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
[in]かどうか、オブジェクトがの作成、集計の一部として、 *pUnkOuter*不明な外部にある必要があります。 それ以外の場合、 *pUnkOuter* NULL にする必要があります。

*riid*<br/>
[in]要求されたインターフェイスの IID。 場合*pUnkOuter* NULL 以外の場合は、 *riid*あります`IID_IUnknown`します。

*ppvObj*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObj* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

モジュールがから派生している場合[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)、`CreateInstance`スレッドに関連付けられているアパートメント オブジェクトを作成する、最初に選択します。

##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer

インクリメントおよびデクリメントはモジュールのロックを呼び出すことによってカウント`_Module::Lock`と`_Module::Unlock`、それぞれします。

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*fLock*<br/>
[in]TRUE の場合、ロック数がインクリメントされます。それ以外の場合、ロック数は減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

使用する場合`CComClassFactoryAutoThread`、`_Module`は通常のグローバル インスタンスを指します[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。

呼び出す`LockServer`により、クライアントは複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持します。

## <a name="see-also"></a>関連項目

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
