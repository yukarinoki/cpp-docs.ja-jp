---
description: '詳細情報: IObjectSafetyImpl クラス'
title: IObjectSafetyImpl クラス
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
ms.openlocfilehash: ac19fe24d12d7d09968b3e2d76f77741e83e1f81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139465"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl クラス

このクラスは、 `IObjectSafety` クライアントがオブジェクトの安全性レベルを取得および設定できるようにするインターフェイスの既定の実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IObjectSafetyImpl` 。

*dwSupportedSafety*<br/>
コントロールに対してサポートされている安全性オプションを指定します。 次の値のいずれかです。

- [Setinterface Afetyoptions](#setinterfacesafetyoptions)パラメーターによって識別されるインターフェイスは、 `riid` スクリプトに対して安全にする必要が INTERFACESAFE_FOR_UNTRUSTED_CALLER ます。

- パラメーターによって識別されるインターフェイスは、 `SetInterfaceSafetyOptions` `riid` 初期化中に信頼されていないデータに対して安全である必要が INTERFACESAFE_FOR_UNTRUSTED_DATA ます。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IObjectSafetyImpl:: Getのインタフェース Afetyoptions](#getinterfacesafetyoptions)|オブジェクトによってサポートされる安全性オプションと、オブジェクトに対して現在設定されている安全性オプションを取得します。|
|[IObjectSafetyImpl:: Setのインタフェース Afetyoptions](#setinterfacesafetyoptions)|オブジェクトを初期化またはスクリプトに対して安全にします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[IObjectSafetyImpl:: m_dwCurrentSafety](#m_dwcurrentsafety)|オブジェクトの現在の安全性レベルを格納します。|

## <a name="remarks"></a>解説

クラス `IObjectSafetyImpl` は、の既定の実装を提供 `IObjectSafety` します。 `IObjectSafety`インターフェイスを使用すると、クライアントはオブジェクトの安全性レベルを取得および設定できます。 たとえば、web ブラウザーはを呼び出して、 `IObjectSafety::SetInterfaceSafetyOptions` コントロールの初期化やスクリプト作成を安全に行うことができます。

CATID_SafeForScripting および CATID_SafeForInitializing コンポーネントのカテゴリで [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) マクロを使用すると、コンポーネントが安全であることを指定する別の方法が提供されることに注意してください。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a> IObjectSafetyImpl:: Getのインタフェース Afetyoptions

オブジェクトによってサポートされる安全性オプションと、オブジェクトに対して現在設定されている安全性オプションを取得します。

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>解説

の実装では、オブジェクトのの実装でサポートされているインターフェイスに対して、適切な値が返され `IUnknown::QueryInterface` ます。

> [!IMPORTANT]
> をサポートするすべてのオブジェクト `IObjectSafety` は、自身のセキュリティを担当し、それがデリゲートするオブジェクトのものです。 プログラマは、ユーザーのコンテキストでのコードの実行、クロスサイトスクリプティング、適切なゾーンチェックの実行に起因する問題を考慮する必要があります。

Windows SDK の「 [IObjectSafety:: Getのインタフェース Afetyoptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) 」を参照してください。

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a> IObjectSafetyImpl:: m_dwCurrentSafety

オブジェクトの現在の安全性レベルを格納します。

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a> IObjectSafetyImpl:: Setのインタフェース Afetyoptions

[M_dwCurrentSafety](#m_dwcurrentsafety)メンバーを適切な値に設定することにより、オブジェクトを初期化またはスクリプトに対して安全にします。

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>解説

この実装は、オブジェクトのの実装でサポートされていないインターフェイスの E_NOINTERFACE を返し `IUnknown::QueryInterface` ます。

> [!IMPORTANT]
> をサポートするすべてのオブジェクト `IObjectSafety` は、自身のセキュリティを担当し、それがデリゲートするオブジェクトのものです。 プログラマは、ユーザーのコンテキストでのコードの実行、クロスサイトスクリプティング、適切なゾーンチェックの実行に起因する問題を考慮する必要があります。

Windows SDK の「 [IObjectSafety:: Set Afetyoptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) 」を参照してください。

## <a name="see-also"></a>関連項目

[IObjectSafety インターフェイス](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[クラスの概要](../../atl/atl-class-overview.md)
