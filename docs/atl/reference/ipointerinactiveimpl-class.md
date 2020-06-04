---
title: イポインター非アクティブImpl クラス
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
ms.openlocfilehash: 229b8c6803aa7b3817cb3d95474bde0502829f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326442"
---
# <a name="ipointerinactiveimpl-class"></a>イポインター非アクティブImpl クラス

このクラスは、`IUnknown`実装し[、IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive)インターフェイス メソッドです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPointerInactiveImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イポインター非アクティブなImpl::取得アクティブ化ポリシー](#getactivationpolicy)|オブジェクトの現在のアクティブ化ポリシーを取得します。 ATL の実装はE_NOTIMPL返します。|
|[イポインター非アクティブインプラブ::オンイアクティブマウスムーブ](#oninactivemousemove)|マウス ポインターがマウス ポインターの上に移動したことをオブジェクトに通知します。 ATL の実装はE_NOTIMPL返します。|
|[イポインター非アクティブなImpl::アクティブなセットカーソル](#oninactivesetcursor)|アクティブでないオブジェクトのマウス ポインタを設定します。 ATL の実装はE_NOTIMPL返します。|

## <a name="remarks"></a>解説

非アクティブなオブジェクトは、単にロードまたは実行されるオブジェクトです。 アクティブなオブジェクトとは異なり、アクティブでないオブジェクトは Windows のマウスメッセージやキーボード メッセージを受信できません。 したがって、非アクティブなオブジェクトはリソースを少なくし、通常はより効率的です。

[IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive)インターフェイスを使用すると、オブジェクトは、アクティブでない状態でマウス操作の最小レベルをサポートできます。 この機能は、コントロールに特に便利です。

クラス`IPointerInactiveImpl`は、E_NOTIMPL`IPointerInactive`返すだけでメソッドを実装します。 ただし、デバッグ ビルド`IUnknown`でダンプ デバイスに情報を送信することで実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a>イポインター非アクティブなImpl::取得アクティブ化ポリシー

オブジェクトの現在のアクティブ化ポリシーを取得します。

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IPointer 非アクティブ::ライセンス認証ポリシー](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) 」を参照してください。

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a>イポインター非アクティブインプラブ::オンイアクティブマウスムーブ

マウス ポインターがマウス ポインターの上に移動したことをオブジェクトに通知します。

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

Windows SDK[の「IPointer 非アクティブ::OnInactiveマウス移動](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove)」を参照してください。

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a>イポインター非アクティブなImpl::アクティブなセットカーソル

アクティブでないオブジェクトのマウス ポインタを設定します。

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

Windows SDK[の「IPointer 非アクティブ::アクティブなセットカーソル](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
