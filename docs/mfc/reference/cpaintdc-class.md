---
title: CPaintDC クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9f83c36a9c1a0d334e3b4a75724521d5711123e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cpaintdc-class"></a>CPaintDC クラス
デバイス コンテキスト クラスから派生[CDC](../../mfc/reference/cdc-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|構築、`CPaintDC`を指定した接続[CWnd](../../mfc/reference/cwnd-class.md)です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|含まれています、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)クライアント領域を描画するために使用します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|`HWND`先である`CPaintDC`オブジェクトをアタッチします。|  
  
## <a name="remarks"></a>コメント  
 実行、 [cwnd::beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)構築時に、 [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint)破棄時にします。  
  
 A`CPaintDC`オブジェクトに応答する場合にのみ使用できます、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージ、通常の`OnPaint`メッセージ ハンドラー メンバー関数。  
  
 使用する方法についての`CPaintDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC  
 構築、`CPaintDC`オブジェクトは、ペイントするため、アプリケーション ウィンドウを準備し、格納、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)構造体、[塗りつぶす対象となる](#m_ps)メンバー変数。  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 指す、`CWnd`オブジェクトを`CPaintDC`オブジェクトが属しています。  
  
### <a name="remarks"></a>コメント  
 例外 (型の`CResourceException`) 場合にスローされますが、Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)呼び出しは失敗します。 デバイス コンテキストは、Windows が既に割り当てられているすべての利用可能なデバイス コンテキストの場合に使用できない可能性があります。 アプリケーションは、共通のディスプレイ コンテキストで、Windows の特定の時点で利用可能なの 5 つに対して競合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd  
 `HWND`先である`CPaintDC`オブジェクトをアタッチします。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hWnd` 保護された型の変数は、`HWND`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>  CPaintDC::m_ps  
 `m_ps` 型のパブリック メンバー変数は、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)です。  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>コメント  
 `PAINTSTRUCT`に渡され、記入するは[cwnd::beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)です。  
  
 `PAINTSTRUCT`に関連付けられているウィンドウのクライアント領域を塗りつぶすために、アプリケーションが使用される情報が含まれています、`CPaintDC`オブジェクト。  
  
 使ってデバイス コンテキスト ハンドルにアクセスできることに注意してください、`PAINTSTRUCT`です。 ただしを使って直接ハンドルをアクセスすることができます、`m_hDC`メンバー変数を`CPaintDC`から継承`CDC`です。  
  
### <a name="example"></a>例  
  例を参照して[CPaintDC::m_hWnd](#m_hwnd)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



