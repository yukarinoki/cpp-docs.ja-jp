---
title: IObject セーフティインプル クラス
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: 6eee7585bc3c5587e106ab6b0cefb4b7129df59f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329662"
---
# <a name="iobjectsafetyimpl-class"></a>IObject セーフティインプル クラス

このクラスは、クライアントがオブジェクトの`IObjectSafety`安全レベルを取得および設定できるようにするインターフェイスの既定の実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IObjectSafetyImpl`。

*dw サポートされているセーフティ*<br/>
コントロールでサポートされている安全オプションを指定します。 次の値のいずれかです。

- INTERFACESAFE_FOR_UNTRUSTED_CALLER [SetInterfaceSafetyOptions](#setinterfacesafetyoptions)パラメーター`riid`で識別されるインターフェイスは、スクリプトを実行しても安全に行う必要があります。

- INTERFACESAFE_FOR_UNTRUSTED_DATA`SetInterfaceSafetyOptions`パラメーター`riid`で識別されるインターフェイスは、初期化中に信頼できないデータに対して安全にする必要があります。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IObject セーフティインプル::インターフェイスセーフティオプション](#getinterfacesafetyoptions)|オブジェクトでサポートされている安全オプションと、オブジェクトに現在設定されている安全オプションを取得します。|
|[IObject セーフティインプル::設定インターフェイスセーフティオプション](#setinterfacesafetyoptions)|初期化またはスクリプトを実行しても、オブジェクトを安全に使用できるようにします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[IObject セーフティインプル::m_dwCurrentSafety](#m_dwcurrentsafety)|オブジェクトの現在の安全レベルを格納します。|

## <a name="remarks"></a>解説

クラス`IObjectSafetyImpl`は、 の既定`IObjectSafety`の実装を提供します。 この`IObjectSafety`インターフェイスを使用すると、クライアントはオブジェクトの安全レベルを取得および設定できます。 たとえば、Web ブラウザーを呼び`IObjectSafety::SetInterfaceSafetyOptions`出して、コントロールを初期化しても安全に、またはスクリプトを実行しても安全にできます。

IMPLEMENTED_CATEGORY[マクロを](category-macros.md#implemented_category)CATID_SafeForScriptingおよびCATID_SafeForInitializingコンポーネント カテゴリと共に使用すると、コンポーネントが安全であることを指定する別の方法が提供されます。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a>IObject セーフティインプル::インターフェイスセーフティオプション

オブジェクトでサポートされている安全オプションと、オブジェクトに現在設定されている安全オプションを取得します。

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>解説

この実装は、オブジェクトの実装でサポートされているインターフェイスに対して適切な値`IUnknown::QueryInterface`を返します。

> [!IMPORTANT]
> サポート`IObjectSafety`するオブジェクトは、自身のセキュリティと、それが委任するオブジェクトのセキュリティを担当します。 プログラマは、ユーザーのコンテキストでコードを実行し、クロスサイト スクリプティングを実行して、適切なゾーン チェックを実行することから生じる問題を考慮に入れる必要があります。

Windows SDK[の「IObject セーフティ::GetInterface セーフティオプション」](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\))を参照してください。

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a>IObject セーフティインプル::m_dwCurrentSafety

オブジェクトの現在の安全レベルを格納します。

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a>IObject セーフティインプル::設定インターフェイスセーフティオプション

[m_dwCurrentSafety](#m_dwcurrentsafety)メンバーを適切な値に設定することにより、初期化またはスクリプトを実行しても安全なオブジェクトになります。

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>解説

この実装は、オブジェクトの実装でサポートされていないインターフェイスのE_NOINTERFACE`IUnknown::QueryInterface`を返します。

> [!IMPORTANT]
> サポート`IObjectSafety`するオブジェクトは、自身のセキュリティと、それが委任するオブジェクトのセキュリティを担当します。 プログラマは、ユーザーのコンテキストでコードを実行し、クロスサイト スクリプティングを実行して、適切なゾーン チェックを実行することから生じる問題を考慮に入れる必要があります。

Windows SDK[の「IObject セーフティ::設定インターフェイスセーフティオプション](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\))」を参照してください。

## <a name="see-also"></a>関連項目

[IObject セーフティ インターフェイス](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[クラスの概要](../../atl/atl-class-overview.md)
