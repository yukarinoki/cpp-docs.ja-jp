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
ms.openlocfilehash: 89a822280ddebca942016f9a3a334a7128d8456a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371977"
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
|[CウィンドウDC:CウィンドウDC](#cwindowdc)|`CWindowDC` オブジェクトを構築します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CウィンドウDC:m_hWnd](#m_hwnd)|これが`CWindowDC`アタッチされている HWND。|

## <a name="remarks"></a>解説

Windows 関数[GetWindowDC を](/windows/win32/api/winuser/nf-winuser-getwindowdc)構築時に呼び出し、破棄時に[DC を解放](/windows/win32/api/winuser/nf-winuser-releasedc)します。 つまり、オブジェクトは`CWindowDC` [CWnd](../../mfc/reference/cwnd-class.md)の画面領域全体 (クライアント領域と非クライアント領域の両方) にアクセスします。

の詳細`CWindowDC`については、「 デバイス[コンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>必要条件

ヘッダー: afxwin.h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a>CウィンドウDC:CウィンドウDC

*pWnd*が指す`CWindowDC`オブジェクトの画面領域全体 (クライアントと非クライアントの両方`CWnd`) にアクセスするオブジェクトを構築します。

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
デバイス コンテキスト オブジェクトがアクセスするクライアント領域のウィンドウ。

### <a name="remarks"></a>解説

コンストラクターは、Windows 関数[を呼](/windows/win32/api/winuser/nf-winuser-getwindowdc)び出します。

Windows`GetWindowDC`呼び出`CResourceException`しが失敗した場合は、(種類の) 例外がスローされます。 Windows が使用可能なすべてのデバイス コンテキストを既に割り当て済みの場合、デバイス コンテキストは使用できない可能性があります。 アプリケーションは、Windows でいつでも利用可能な 5 つの一般的な表示コンテキストを競合します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a>CウィンドウDC:m_hWnd

オブジェクトの構築には、`CWnd`ポインタの HWND`CWindowDC`が使用されます。

```
HWND m_hWnd;
```

### <a name="remarks"></a>解説

`m_hWnd`は、HWND 型の保護変数です。

### <a name="example"></a>例

  [CWindowDC::CWindowDC](#cwindowdc)の例を参照してください。

## <a name="see-also"></a>関連項目

[CDCクラス](../../mfc/reference/cdc-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDCクラス](../../mfc/reference/cdc-class.md)
