---
title: CClientDC クラス
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: 5304fa322c62f67ed075be7912697f8c87b27392
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643834"
---
# <a name="cclientdc-class"></a>CClientDC クラス

Windows 関数の呼び出しを行います[GetDC](/windows/desktop/api/winuser/nf-winuser-getdc)構築時に、 [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc)破棄時にします。

## <a name="syntax"></a>構文

```
class CClientDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CClientDC::CClientDC](#cclientdc)|構築、`CClientDC`オブジェクトに接続されている、`CWnd`します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CClientDC::m_hWnd](#m_hwnd)|このウィンドウの HWND`CClientDC`は有効です。|

## <a name="remarks"></a>Remarks

こうすることに関連付けられているデバイス コンテキスト、`CClientDC`オブジェクトは、ウィンドウのクライアント領域。

詳細については`CClientDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cclientdc"></a>  CClientDC::CClientDC

構築、`CClientDC`のクライアント領域にアクセスするオブジェクト、 [CWnd](../../mfc/reference/cwnd-class.md)によって示される*我が物*します。

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
デバイス コンテキスト オブジェクトがアクセス クライアント領域を持つウィンドウです。

### <a name="remarks"></a>Remarks

コンス トラクターは、Windows の関数を呼び出します。 [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc)します。

例外 (型の`CResourceException`) 場合にスローされる、Windows`GetDC`呼び出しは失敗します。 Windows が既に割り当てられているすべての利用可能なデバイス コンテキストの場合は、デバイス コンテキストを使用しないことがあります。 アプリケーションは、共通のディスプレイ コンテキスト Windows の任意の時点でご利用いただけますの 5 つの競合します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CClientDC::m_hWnd

`HWND`の`CWnd`ポインターの構築に使用される、`CClientDC`オブジェクト。

```
HWND m_hWnd;
```

### <a name="remarks"></a>Remarks

*m_hWnd*は保護された変数です。

### <a name="example"></a>例

  例をご覧ください[CClientDC::CClientDC](#cclientdc)します。

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)
