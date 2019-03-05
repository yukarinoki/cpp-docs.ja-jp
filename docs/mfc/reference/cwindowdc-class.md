---
title: CWindowDC クラス
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 55a9ccfc496c95c9e7410cbd5645135ee555ff26
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289352"
---
# <a name="cwindowdc-class"></a>CWindowDC クラス

`CDC`の派生クラスです。

## <a name="syntax"></a>構文

```
class CWindowDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|`CWindowDC` オブジェクトを構築します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|この HWND`CWindowDC`がアタッチされています。|

## <a name="remarks"></a>Remarks

Windows 関数を呼び出す[GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)構築時に、 [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc)破棄時にします。 つまり、`CWindowDC`オブジェクト アクセスの全画面領域を[CWnd](../../mfc/reference/cwnd-class.md) (クライアントと非クライアント領域)。

使用しての詳細については`CWindowDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>必要条件

ヘッダー: afxwin.h

##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC

構築、`CWindowDC`の全画面領域 (クライアントと非クライアントの両方) にアクセスするオブジェクト、`CWnd`指すオブジェクト*我が物*します。

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
デバイス コンテキスト オブジェクトがアクセス クライアント領域を持つウィンドウです。

### <a name="remarks"></a>Remarks

コンス トラクターは、Windows の関数を呼び出します。 [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)します。

例外 (型の`CResourceException`) 場合にスローされる、Windows`GetWindowDC`呼び出しは失敗します。 Windows が既に割り当てられているすべての利用可能なデバイス コンテキストの場合は、デバイス コンテキストを使用しないことがあります。 アプリケーションは、共通のディスプレイ コンテキスト Windows の任意の時点でご利用いただけますの 5 つの競合します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd

HWND、`CWnd`ポインターが構築に使用される、`CWindowDC`オブジェクト。

```
HWND m_hWnd;
```

### <a name="remarks"></a>Remarks

`m_hWnd` HWND の種類の保護された変数。

### <a name="example"></a>例

  例をご覧ください[CWindowDC::CWindowDC](#cwindowdc)します。

## <a name="see-also"></a>関連項目

[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)
