---
title: CAtlPreviewCtrlImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 926076115a19b8c9669ec03958d841f08417e89c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362188"
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl クラス
このクラスは、ATL リッチ プレビュー用にシェルによって提供されるホスト ウィンドウに配置されているウィンドウの実装です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|プレビュー コントロール オブジェクトを破棄します。|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|プレビュー コントロール オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Windows のウィンドウを作成する豊富なプレビュー ハンドラーによって呼び出されます。|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|このコントロールを破棄する必要があるときに、豊富なプレビュー ハンドラーによって呼び出されます。|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|このコントロールにフォーカスが入力を設定します。|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|WM_PAINT メッセージを処理します。|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|このコントロールを再描画するように指示します。|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|このコントロールの新しい親を設定します。|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|によって呼び出されますリッチ プレビュー ハンドラーのリッチ プレビューでのビジュアルを設定する必要があるときにコンテンツ。|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|このコントロールの新しい外接する四角形を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|プレビューを表示するためにフレームワークによって呼び出されます。|  
  
### <a name="protected-constants"></a>プロテクト コンス トラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|プレビュー ウィンドウでテキストを表示するために使用するフォントです。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|プレビュー ウィンドウの背景色です。|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|プレビュー ウィンドウのテキストの色。|  

  
## <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlpreviewctrlimpl.h  
  
##  <a name="catlpreviewctrlimpl"></a>  CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 プレビュー コントロール オブジェクトを構築します。  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dtor"></a>  CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 プレビュー コントロール オブジェクトを破棄します。  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>  CAtlPreviewCtrlImpl::Create  
 Windows のウィンドウを作成する豊富なプレビュー ハンドラーによって呼び出されます。  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 リッチ プレビュー用にシェルによって提供される、ホスト ウィンドウへのハンドル。  
  
 `prc`  
 初期サイズとウィンドウの位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="destroy"></a>  CAtlPreviewCtrlImpl::Destroy  
 このコントロールを破棄する必要があるときに、豊富なプレビュー ハンドラーによって呼び出されます。  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dopaint"></a>  CAtlPreviewCtrlImpl::DoPaint  
 プレビューを表示するためにフレームワークによって呼び出されます。  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>パラメーター  
 `hdc`  
 描画のデバイス コンテキストへのハンドル。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="focus"></a>  CAtlPreviewCtrlImpl::Focus  
 このコントロールにフォーカスが入力を設定します。  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_clrback"></a>  CAtlPreviewCtrlImpl::m_clrBack  
 プレビュー ウィンドウの背景色です。  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_clrtext"></a>  CAtlPreviewCtrlImpl::m_clrText  
 プレビュー ウィンドウのテキストの色。  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_plf"></a>  CAtlPreviewCtrlImpl::m_plf  
 プレビュー ウィンドウでテキストを表示するために使用するフォントです。  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onpaint"></a>  CAtlPreviewCtrlImpl::OnPaint  
 WM_PAINT メッセージを処理します。  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 WM_PAINT に設定されます。  
  
 `wParam`  
 このパラメーターは使用されません。  
  
 `lParam`  
 このパラメーターは使用されません。  
  
 `bHandled`  
 この関数が戻るときに、格納`TRUE`です。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="redraw"></a>  CAtlPreviewCtrlImpl::Redraw  
 このコントロールを再描画するように指示します。  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sethost"></a>  CAtlPreviewCtrlImpl::SetHost  
 このコントロールの新しい親を設定します。  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 新しい親ウィンドウへのハンドル。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpreviewvisuals"></a>  CAtlPreviewCtrlImpl::SetPreviewVisuals  
 によって呼び出されますリッチ プレビュー ハンドラーのリッチ プレビューでのビジュアルを設定する必要があるときにコンテンツ。  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrBack`  
 プレビュー ウィンドウの背景色です。  
  
 `clrText`  
 プレビュー ウィンドウのテキストの色。  
  
 `plf`  
 プレビュー ウィンドウでテキストを表示するために使用するフォントです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setrect"></a>  CAtlPreviewCtrlImpl::SetRect  
 このコントロールの新しい外接する四角形を設定します。  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>パラメーター  
 `prc`  
 新しいサイズとプレビュー コントロールの位置を指定します。  
  
 `bRedraw`  
 コントロールを再描画されるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
