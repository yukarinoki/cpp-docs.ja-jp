---
title: クラスクラス
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: e997d92adfa9df46c82dacbd297db495b037c6e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320902"
---
# <a name="ccomclassfactoryautothread-class"></a>クラスクラス

このクラスは[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装し、複数のアパートメントでオブジェクトを作成できるようにします。

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
|[を使用します。](#createinstance)|指定した CLSID のオブジェクトを作成します。|
|[クラスファクトリーオートスレッド::ロックサーバー](#lockserver)|クラス ファクトリをメモリ内でロックします。|

## <a name="remarks"></a>解説

`CComClassFactoryAutoThread`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)に似ていますが、複数のアパートメントでオブジェクトを作成できます。 このサポートを利用するには、EXE モジュールを[派生させます](../../atl/reference/ccomautothreadmodule-class.md)。

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには[、CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラス ファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)が含まれます。 を使用`CComClassFactoryAutoThread`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a>を使用します。

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*プンクアウター*<br/>
[in]オブジェクトが集約の一部として作成される場合 *、pUnkOuter*は外部不明である必要があります。 それ以外の場合は *、pUnkOuter*は NULL である必要があります。

*riid*<br/>
[in]要求されたインターフェイスの IID。 *pUnkOuter*が NULL 以外の場合は *、riid*を指定する必要があります`IID_IUnknown`。

*Ppvobj*<br/>
[アウト]*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObj*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

モジュールが[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)から派生している`CreateInstance`場合は、最初にスレッドを選択して、関連付けられたアパートメントにオブジェクトを作成します。

## <a name="ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a>クラスファクトリーオートスレッド::ロックサーバー

モジュールのロックカウントをそれぞれ、 と を呼び`_Module::Lock`出`_Module::Unlock`して、インクリメントとデクリメントします。

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
[in]TRUE の場合、ロックカウントはインクリメントされます。それ以外の場合、ロックカウントは減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

を使用`CComClassFactoryAutoThread`する`_Module`場合は、通常[、CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)のグローバル インスタンスを参照します。

呼`LockServer`び出しを使用すると、クライアントはクラス ファクトリを保持できるため、複数のオブジェクトを迅速に作成できます。

## <a name="see-also"></a>関連項目

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[クラス](../../atl/reference/ccomclassfactory2-class.md)<br/>
[シングルトンクラス](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[スレッドモデル](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
