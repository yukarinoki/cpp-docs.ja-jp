---
description: '詳細情報: CWindowDC クラス'
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
ms.openlocfilehash: 1fc36614f5e6ded32a47146771991c3ab06998eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344927"
---
# <a name="cwindowdc-class"></a>CWindowDC クラス

`CDC` から派生。

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
|[CWindowDC:: m_hWnd](#m_hwnd)|このがアタッチされている HWND `CWindowDC` 。|

## <a name="remarks"></a>解説

構築時に Windows 関数 [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)を呼び出し、破棄時に [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) します。 これは、 `CWindowDC` オブジェクトが [CWnd](../../mfc/reference/cwnd-class.md) の画面領域全体 (クライアント領域と非クライアント領域の両方) にアクセスすることを意味します。

の使用方法の詳細につい `CWindowDC` ては、「 [デバイスコンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>要件

ヘッダー: afxwin.h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a> CWindowDC::CWindowDC

PWnd が `CWindowDC` 指すオブジェクトの画面領域全体 (クライアントと非クライアントの両方) にアクセスするオブジェクトを構築し `CWnd` ます。 

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
デバイスコンテキストオブジェクトがアクセスするクライアント領域があるウィンドウ。

### <a name="remarks"></a>解説

コンストラクターは、Windows 関数 [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)を呼び出します。

Windows の呼び出しが失敗した場合、例外 (型 `CResourceException` ) がスローされ `GetWindowDC` ます。 Windows によって使用可能なデバイスコンテキストがすべて既に割り当てられている場合、デバイスコンテキストを使用できない可能性があります。 アプリケーションは、Windows で任意の時点で使用可能な5つの共通表示コンテキストを競合しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a> CWindowDC:: m_hWnd

ポインターの HWND は、 `CWnd` オブジェクトを構築するために使用され `CWindowDC` ます。

```
HWND m_hWnd;
```

### <a name="remarks"></a>解説

`m_hWnd` は、HWND 型の保護された変数です。

### <a name="example"></a>例

  [CWindowDC:: CWindowDC](#cwindowdc)の例を参照してください。

## <a name="see-also"></a>関連項目

[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)
