---
title: CComClassFactorySingleton クラス
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: 480b4c2a6e052e8e0823b97b548fc5d07b55230f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260176"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton クラス

このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 1 つのオブジェクトを構築します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラス。

`CComClassFactorySingleton` 派生した[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 1 つのオブジェクトを構築します。 呼び出しごとに、`CreateInstance`メソッドは単にインターフェイス ポインターをこのオブジェクトを照会します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|クエリ`m_spObj`にインターフェイス ポインター。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)によって構築されたオブジェクト`CComClassFactorySingleton`します。|

## <a name="remarks"></a>Remarks

ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言する`CComClassFactory`既定のクラス ファクトリとして。 使用する`CComClassFactorySingleton`、指定、 [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton)オブジェクトのクラス定義でマクロ。 例えば:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance

呼び出し`QueryInterface`を通じて[m_spObj](#m_spobj)インターフェイス ポインターを取得します。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
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

##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj

[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)によって構築されたオブジェクト`CComClassFactorySingleton`します。

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Remarks

呼び出しごとに、 [CreateInstance](#createinstance)メソッドは単にインターフェイス ポインターをこのオブジェクトを照会します。

なお、現在のフォームの`m_spObj`方法から重大な変更を表示しますを`CComClassFactorySingleton`ATL の以前のバージョンで動作 以前のバージョンで、`CComClassFactorySingleton`オブジェクトは、サーバーの初期化中に、クラス ファクトリと同時に作成されました。 Visual C .NET 2003年では、最初の要求で、オブジェクトが遅れて、作成されます。 この変更の初期化に依存するプログラムでエラーが発生する可能性があります。

## <a name="see-also"></a>関連項目

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
