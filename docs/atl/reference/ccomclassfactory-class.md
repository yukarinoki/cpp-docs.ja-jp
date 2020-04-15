---
title: クラスクラス
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 041575339906b83488697f1db5a7f8b08b53070e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321022"
---
# <a name="ccomclassfactory-class"></a>クラスクラス

このクラスは[、IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装します。

## <a name="syntax"></a>構文

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インスタンスの作成](#createinstance)|指定した CLSID のオブジェクトを作成します。|
|[クラスファクトリー::ロックサーバー](#lockserver)|クラス ファクトリをメモリ内でロックします。|

## <a name="remarks"></a>解説

`CComClassFactory`は、特定の CLSID のオブジェクトを作成するためのメソッドを含む[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装し、クラス ファクトリをメモリにロックして、新しいオブジェクトをより迅速に作成できるようにします。 `IClassFactory`は、システム レジストリに登録し、CLSID を割り当てるすべてのクラスに対して実装する必要があります。

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには、既定[DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)のクラス ファクトリ`CComClassFactory`として宣言されるマクロ DECLARE_CLASSFACTORY が含まれます。 このデフォルトをオーバーライドするには、クラス定義で`DECLARE_CLASSFACTORY` *XXX*マクロのいずれかを指定します。 たとえば[、DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex)マクロは、クラス ファクトリに対して指定されたクラスを使用します。

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

上記のクラス定義は、`CMyClassFactory`オブジェクトの既定のクラス ファクトリとして使用されることを指定します。 `CMyClassFactory`を派生`CComClassFactory`し、オーバーライド`CreateInstance`する必要があります。

ATL には、クラス ファクトリを宣言する他の 3 つのマクロが用意されています。

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)ライセンスを使用して作成を制御する[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)を使用します。

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)複数のアパートメントにオブジェクトを作成する[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)を使用します。

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton)単一の CCom オブジェクトグローバル オブジェクトを構築する[CCom](../../atl/reference/ccomobjectglobal-class.md) [クラスファクトリーシングルトン](../../atl/reference/ccomclassfactorysingleton-class.md)を使用します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomclassfactorycreateinstance"></a><a name="createinstance"></a>インスタンスの作成

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

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

## <a name="ccomclassfactorylockserver"></a><a name="lockserver"></a>クラスファクトリー::ロックサーバー

モジュールのロックカウントをそれぞれ、 と を呼び`_Module::Lock`出`_Module::Unlock`して、インクリメントとデクリメントします。

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
[in]TRUE の場合、ロックカウントはインクリメントされます。それ以外の場合、ロックカウントは減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`_Module`[CComModule](../../atl/reference/ccommodule-class.md)のグローバル インスタンス、またはそこから派生したクラスを指します。

呼`LockServer`び出しを使用すると、クライアントはクラス ファクトリを保持できるため、複数のオブジェクトを短時間で作成できます。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[スレッドモデル](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
