---
description: '詳細情報: CClientDC クラス'
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
ms.openlocfilehash: 27735929734388ccb25eaf178e49d63884beed0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122461"
---
# <a name="cclientdc-class"></a>CClientDC クラス

は、構築時に Windows functions [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) を呼び出し、破棄時に [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) を行います。

## <a name="syntax"></a>構文

```
class CClientDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CClientDC:: CClientDC](#cclientdc)|`CClientDC`に接続されたオブジェクトを構築 `CWnd` します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CClientDC:: m_hWnd](#m_hwnd)|この `CClientDC` が有効なウィンドウの HWND。|

## <a name="remarks"></a>解説

これは、オブジェクトに関連付けられているデバイスコンテキスト `CClientDC` がウィンドウのクライアント領域であることを意味します。

の詳細につい `CClientDC` ては、「 [デバイスコンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a> CClientDC:: CClientDC

PWnd が `CClientDC` 指す[CWnd](../../mfc/reference/cwnd-class.md)のクライアント領域にアクセスするオブジェクトを構築します。

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
デバイスコンテキストオブジェクトがアクセスするクライアント領域があるウィンドウ。

### <a name="remarks"></a>解説

コンストラクターは、Windows 関数 [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)を呼び出します。

Windows の呼び出しが失敗した場合、例外 (型 `CResourceException` ) がスローされ `GetDC` ます。 Windows によって使用可能なデバイスコンテキストがすべて既に割り当てられている場合、デバイスコンテキストを使用できない可能性があります。 アプリケーションは、Windows で任意の時点で使用可能な5つの共通表示コンテキストを競合しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a> CClientDC:: m_hWnd

`HWND` `CWnd` オブジェクトを構築するために使用するポインターの `CClientDC` 。

```
HWND m_hWnd;
```

### <a name="remarks"></a>解説

*m_hWnd* は保護された変数です。

### <a name="example"></a>例

  [Cclientdc:: cclientdc](#cclientdc)の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)
