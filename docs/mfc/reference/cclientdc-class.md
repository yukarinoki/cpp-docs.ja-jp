---
title: CClientDC クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4f013589b509781d217e521b680f1d529189a0a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954267"
---
# <a name="cclientdc-class"></a>CClientDC クラス
Windows 関数の呼び出しを行います[GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)構築時に、 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920)破棄時にします。  
  
## <a name="syntax"></a>構文  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|構築、`CClientDC`に接続されているオブジェクト、`CWnd`です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND`対象のウィンドウの`CClientDC`は無効です。|  
  
## <a name="remarks"></a>Remarks  
 つまり、デバイス コンテキストに関連付けられている、`CClientDC`オブジェクトは、ウィンドウのクライアント領域。  
  
 詳細については`CClientDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cclientdc"></a>  CClientDC::CClientDC  
 構築、`CClientDC`のクライアント領域にアクセスするオブジェクト、 [CWnd](../../mfc/reference/cwnd-class.md)によって示される*pWnd*です。  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 デバイス コンテキスト オブジェクトがアクセス クライアント領域を持つウィンドウです。  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターは、Windows の関数を呼び出します。 [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)です。  
  
 例外 (型の`CResourceException`) 場合にスローされますが、Windows`GetDC`呼び出しは失敗します。 デバイス コンテキストは、Windows が既に割り当てられているすべての利用可能なデバイス コンテキストの場合に使用できない可能性があります。 アプリケーションは、共通のディスプレイ コンテキストで、Windows の特定の時点で利用可能なの 5 つに対して競合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CClientDC::m_hWnd  
 `HWND`の`CWnd`ポインターを構築するために使用、`CClientDC`オブジェクト。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Remarks  
 *m_hWnd*保護された変数です。  
  
### <a name="example"></a>例  
  例を参照して[CClientDC::CClientDC](#cclientdc)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)
