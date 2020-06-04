---
title: シングルトンクラス
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: ec860f7ef59b7d3289bf2e18fea0f0e064a7c8f9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320826"
---
# <a name="ccomclassfactorysingleton-class"></a>シングルトンクラス

このクラスは[、CCom クラスファクトリー](../../atl/reference/ccomclassfactory-class.md)から派生し、単一のオブジェクトを構築するのに[は、CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を使用します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
あなたのクラス。

`CComClassFactorySingleton`から[派生し、](../../atl/reference/ccomclassfactory-class.md)単一のオブジェクトを構築するために[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を使用します。 メソッドを`CreateInstance`呼び出すたびに、このオブジェクトにインターフェイス ポインターを照会するだけです。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[シングルトンを作成します。](#createinstance)|インターフェイス`m_spObj`ポインターのクエリ。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[シングルトン::m_spObj](#m_spobj)|によって[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)構築された`CComClassFactorySingleton`オブジェクトです。|

## <a name="remarks"></a>解説

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには、既定[DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)のクラス ファクトリ`CComClassFactory`として宣言されるマクロ DECLARE_CLASSFACTORY が含まれます。 を使用`CComClassFactorySingleton`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[コムクラスファクトリー](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a>シングルトンを作成します。

インターフェイス`QueryInterface`ポインターを取得する[m_spObj](#m_spobj)を呼び出します。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
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

## <a name="ccomclassfactorysingletonm_spobj"></a><a name="m_spobj"></a>シングルトン::m_spObj

によって[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)構築された`CComClassFactorySingleton`オブジェクトです。

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>解説

[CreateInstance](#createinstance)メソッドを呼び出すたびに、このオブジェクトにインターフェイス ポインターを照会するだけです。

現在の形式のの`m_spObj`ATL の以前のバージョンで`CComClassFactorySingleton`動作した方法とは異なった変更点があることに注意してください。 以前のバージョンでは`CComClassFactorySingleton`、オブジェクトは、サーバーの初期化中にクラス ファクトリと同時に作成されました。 Visual C++.NET 2003 以降では、オブジェクトは最初の要求で、遅い方法で作成されます。 この変更により、初期の初期化に依存するプログラムでエラーが発生する可能性があります。

## <a name="see-also"></a>関連項目

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[クラス](../../atl/reference/ccomclassfactory2-class.md)<br/>
[クラスクラス](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[スレッドモデル](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
