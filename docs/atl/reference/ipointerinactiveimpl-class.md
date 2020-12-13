---
description: '詳細情報: IPointerInactiveImpl クラス'
title: IPointerInactiveImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 0ee5c103582ff68c80edd36316179b47a1b7931d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139309"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl クラス

このクラス `IUnknown` は、および [Iポインター非アクティブ](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) インターフェイスメソッドを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IPointerInactiveImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|オブジェクトの現在のアクティブ化ポリシーを取得します。 ATL 実装は E_NOTIMPL を返します。|
|[IPointerInactiveImpl:: OnInactiveMouseMove](#oninactivemousemove)|マウスポインターがその上に移動したことをオブジェクトに通知し、オブジェクトがマウスイベントを発生させることができることを示します。 ATL 実装は E_NOTIMPL を返します。|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|非アクティブなオブジェクトのマウスポインターを設定します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>解説

非アクティブなオブジェクトとは、単に読み込まれるか、または実行されるオブジェクトのことです。 アクティブなオブジェクトとは異なり、非アクティブなオブジェクトは Windows のマウスおよびキーボードメッセージを受け取ることができません。 したがって、非アクティブなオブジェクトは使用するリソースが減り、通常はより効率的です。

[Iポインタ inactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive)インターフェイスを使用すると、オブジェクトは最小限のマウス操作をサポートしながら、非アクティブな状態を維持できます。 この機能は、特にコントロールに役立ちます。

クラス `IPointerInactiveImpl` は、 `IPointerInactive` 単に E_NOTIMPL を返すことによってメソッドを実装します。 ただし、 `IUnknown` デバッグビルドのダンプデバイスに情報を送信することによってが実装されます。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a> IPointerInactiveImpl::GetActivationPolicy

オブジェクトの現在のアクティブ化ポリシーを取得します。

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [Iポインター inactive:: GetActivationPolicy](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) 」を参照してください。

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a> IPointerInactiveImpl:: OnInactiveMouseMove

マウスポインターがその上に移動したことをオブジェクトに通知し、オブジェクトがマウスイベントを発生させることができることを示します。

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [Iポインター inactive:: OnInactiveMouseMove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) 」を参照してください。

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a> IPointerInactiveImpl::OnInactiveSetCursor

非アクティブなオブジェクトのマウスポインターを設定します。

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [Iポインター inactive:: OnInactiveSetCursor](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) 」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
