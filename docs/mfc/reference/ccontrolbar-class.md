---
title: CControlBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
dev_langs:
- C++
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 443e55ab69bc9585a780374a82d5d99b0fd9eef9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ccontrolbar-class"></a>CControlBar Class
コントロール バー クラスの基底クラス[CStatusBar](../../mfc/reference/cstatusbar-class.md)、 [CToolBar](../../mfc/reference/ctoolbar-class.md)、 [CDialogBar](../../mfc/reference/cdialogbar-class.md)、 [CReBar](../../mfc/reference/crebar-class.md)、および[COleResizeBar](../../mfc/reference/coleresizebar-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|`CControlBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|としてダイナミック コントロール バーのサイズを返します、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|としてコントロール バーのサイズを返します、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|境界線を含むコントロール バー領域の現在のディメンションを返します。|  
|[CControlBar::DoPaint](#dopaint)|コントロール バーの境界線およびグリップをレンダリングします。|  
|[CControlBar::DrawBorders](#drawborders)|コントロール バーの境界線をレンダリングします。|  
|[CControlBar::DrawGripper](#drawgripper)|コントロール バーのグリップをレンダリングします。|  
|[CControlBar::EnableDocking](#enabledocking)|コントロール バーをドッキングまたはフローティングできるようにします。|  
|[したとき](#getbarstyle)|コントロール バーのスタイル設定を取得します。|  
|[CControlBar::GetBorders](#getborders)|コントロール バーの境界線の値を取得します。|  
|[CControlBar::GetCount](#getcount)|以外の数を返します`HWND`コントロール バー内の要素。|  
|[CControlBar::GetDockingFrame](#getdockingframe)|コントロール バーがドッキングされるフレームへのポインターを返します。|  
|[CControlBar::IsFloating](#isfloating)|対象のコントロール バーがフローティング コントロール バーである場合に、ゼロ以外の値を返します。|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|コマンド UI ハンドラーを呼び出します。|  
|[CControlBar::SetBarStyle](#setbarstyle)|コントロール バーのスタイル設定を変更します。|  
|[CControlBar::SetBorders](#setborders)|コントロール バーの境界線の値を設定します。|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|コントロール バーのインプレース所有者を変更します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|コントロール バーのインプレース所有者です。|  
  
## <a name="remarks"></a>コメント  
 通常、コントロール バーは、フレーム ウィンドウの左側または右側にアラインされるウィンドウです。 いずれかである子項目が含まれて`HWND`ベースを生成し、Windows メッセージ、または非対応であるコントロールの使用方法の`HWND`のウィンドウではなく、アプリケーション コードまたはフレームワーク コードによって管理されるアイテムのベースします。 リスト ボックスやエディット コントロールの例については、 `HWND`- に基づいてコントロール以外の場合はステータス バー ペインやビットマップ ボタンは非の例 - `HWND`-コントロールに基づきます。  
  
 通常、コントロール バーのウィンドウは親フレーム ウィンドウの子ウィンドウであり、通常はクライアント ビューまたはフレーム ウィンドウの MDI クライアントの兄弟です。 `CControlBar` オブジェクトは、親ウィンドウのクライアント領域の四角形に関する情報を使用して、それ自体を配置します。 次に、親ウィンドウのクライアント領域においてどの程度の未割り当て領域が残っているかについて、親ウィンドウに通知します。  
  
 `CControlBar` の詳細については、次を参照してください。  
  
- [コントロール バー](../../mfc/control-bars.md)  
  
- [テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)です。  
  
-   サポート技術情報の文書 Q242577「PRB: Update Command UI Handlers Do Not Work for Menu Attached to a Dialog Box」  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="calcdynamiclayout"></a>  CControlBar::CalcDynamicLayout  
 フレームワークは、動的なツールバーのサイズを計算するには、このメンバー関数を呼び出します。  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLength`  
 コントロール バー、に応じて、縦線または横線の要求されたディメンション`dwMode`です。  
  
 `nMode`  
 次の定義済みフラグは、ダイナミック コントロール バーの幅と高さを決定に使用されます。 ビットごとの OR を使用して (&#124;) フラグを結合する演算子です。  
  
|レイアウト モード フラグ|その意味|  
|-----------------------|-------------------|  
|`LM_STRETCH`|コントロール バーをフレームのサイズを拡大するかどうかを示します。 バーがドッキング バー (ドッキングは使用できません) ではない場合に設定します。 場合設定されません、バーがドッキングまたはフローティング (ドッキング使用可能)。 場合設定、`LM_STRETCH`無視`nLength`に基づいてディメンションを返します、`LM_HORZ`状態です。 `LM_STRETCH` 動作と同じように、`bStretch`で使用されるパラメーター [CalcFixedLayout](#calcfixedlayout); 拡大と印刷の向きの関係の詳細については、メンバー関数を参照してください。|  
|`LM_HORZ`|バーが水平方向または垂直方向であることを示します。 バーが水平方向および垂直方向の場合、これが設定されていない場合に設定します。 `LM_HORZ` 動作と同じように、`bHorz`で使用されるパラメーター [CalcFixedLayout](#calcfixedlayout); 拡大と印刷の向きの関係の詳細については、メンバー関数を参照してください。|  
|**LM_MRUWIDTH**|動的な幅最近使用します。 無視`nLength`パラメーターと使用して、記憶された最も最近の幅を使用します。|  
|`LM_HORZDOCK`|水平方向には、ディメンションがドッキングされています。 無視`nLength`パラメーターを最大の幅と動的なサイズを返します。|  
|`LM_VERTDOCK`|垂直方向には、ディメンションがドッキングされています。 無視`nLength`パラメーターを最大の高さの動的なサイズを返します。|  
|`LM_LENGTHY`|場合設定`nLength`幅ではなく高さ (Y 方向) を示します。|  
|`LM_COMMIT`|リセット**LM_MRUWIDTH**フローティング コントロール バーの現在の幅にします。|  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのサイズ (ピクセル単位) の[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 派生したクラスで、独自の動的レイアウトを提供するには、このメンバー関数をオーバーライド`CControlBar`です。 派生した MFC クラス`CControlBar`など[CToolbar](../../mfc/reference/ctoolbar-class.md)、このメンバー関数をオーバーライドし、独自の実装を提供します。  
  
##  <a name="calcfixedlayout"></a>  CControlBar::CalcFixedLayout  
 コントロール バーの水平方向のサイズを計算するには、このメンバー関数を呼び出します。  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 `bStretch`  
 フレームのサイズ、バーを拡大するかどうかを示します。 `bStretch`と、バー ドッキング バー (ドッキングは使用できません) ではない場合は 0 は、ドッキングまたはフローティング (ドッキング使用可能) は、パラメーターが 0 以外の値。  
  
 `bHorz`  
 バーが水平方向または垂直方向であることを示します。 `bHorz`バーが水平方向および垂直方向である場合は 0 の場合は、パラメーターが 0 以外。  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのサイズ (ピクセル単位) の`CSize`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 ツールバーなどのコントロール バーが水平方向にストレッチできます。 または垂直方向にボタンに合わせて、コントロール バーに含まれています。  
  
 場合`bStretch`は**TRUE**、によって提供される向きに沿って寸法をストレッチ`bHorz`です。 つまり場合、`bHorz`は**FALSE**、コントロール バーが垂直方向に拡大されます。 場合`bStretch`は**FALSE**stretch が行われません。 次の表は、の可能な順列は、および結果として得られるコントロール バーのスタイルを示しています。`bStretch`と`bHorz`です。  
  
|bStretch|bHorz|拡大|[方向]|非ドッキングとドッキング|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**場合は TRUE。**|**場合は TRUE。**|水平方向の拡大|横方向|非ドッキング|  
|**場合は TRUE。**|**FALSE**|垂直方向の拡大|垂直方向|非ドッキング|  
|**FALSE**|**場合は TRUE。**|伸縮しません。|横方向|ドッキング|  
|**FALSE**|**FALSE**|伸縮しません。|垂直方向|ドッキング|  
  
##  <a name="calcinsiderect"></a>  CControlBar::CalcInsideRect  
 フレームワークは、コントロール バーのクライアント領域を計算するには、この関数を呼び出します。  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 コントロール バーの現在のディメンションが含まれます罫線を含むです。  
  
 `bHorz`  
 バーが水平方向または垂直方向であることを示します。 `bHorz`バーが水平方向および垂直方向である場合は 0 の場合は、パラメーターが 0 以外。  
  
### <a name="remarks"></a>コメント  
 コントロール バーが描画前に、この関数が呼び出されます。  
  
 枠線とコントロール バーのグリッパー バーの表示をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="ccontrolbar"></a>  CControlBar::CControlBar  
 `CControlBar` オブジェクトを構築します。  
  
```  
CControlBar();
```  
  
##  <a name="dopaint"></a>  CControlBar::DoPaint  
 枠線とコントロール バーのグリッパー バーを表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 枠線とコントロール バーのグリップを描画に使用するためにデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 コントロール バーの描画の動作をカスタマイズするには、この関数をオーバーライドします。  
  
 他のカスタマイズの方法は、オーバーライドする、`DrawBorders`と`DrawGripper`関数し、境界線およびグリップをカスタム描画コードを追加します。 既定では、これらのメソッドが呼び出されるため`DoPaint`メソッドは、のオーバーライド`DoPaint`は必要ありません。  
  
##  <a name="drawborders"></a>  CControlBar::DrawBorders  
 コントロール バーの境界線を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コントロール バーの境界線の描画に使用するためにデバイス コンテキストへのポインター。  
  
 `rect`  
 A`CRect`コントロール バーのディメンションを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 コントロール バーの境界線の外観をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="drawgripper"></a>  CControlBar::DrawGripper  
 コントロール バーのグリップをレンダリングするためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コントロール バーのグリップを描画に使用するためにデバイス コンテキストへのポインター。  
  
 `rect`  
 A`CRect`コントロール バーのグリップのディメンションを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 コントロール バーのグリップの外観をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="enabledocking"></a>  CControlBar::EnableDocking  
 ドッキング コントロール バーを有効にするには、この関数を呼び出します。  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDockStyle`  
 サポートされている場合は、コントロール バーがドッキングをサポートするかどうかとするコントロール バーをドッキングできる、親ウィンドウの辺を指定します。 次の 1 つ以上を指定できます。  
  
- `CBRS_ALIGN_TOP` クライアント領域の上部にドッキングできます。  
  
- `CBRS_ALIGN_BOTTOM` クライアント領域の下部にドッキングできます。  
  
- `CBRS_ALIGN_LEFT` クライアント領域の左側にドッキングできます。  
  
- `CBRS_ALIGN_RIGHT` クライアント領域の右側にドッキングできます。  
  
- `CBRS_ALIGN_ANY` クライアント領域の任意の辺にドッキングできます。  
  
- `CBRS_FLOAT_MULTI` フロートするか、1 つのミニフレーム ウィンドウ内に複数のコントロール バーを使用できます。  
  
 0 の場合 (つまり、フラグを示すなし)、コントロール バーがドッキングされます。  
  
### <a name="remarks"></a>コメント  
 指定した辺が先フレーム ウィンドウのドッキングできる辺のいずれかに一致する必要がありますか、そのフレーム ウィンドウにコントロール バーをドッキングすることはできません。  
  
##  <a name="getbarstyle"></a>  したとき  
 決定するためには、この関数を呼び出す**cbrs _** (コントロール バーのスタイル) の設定は、コントロール バーに現在設定されています。  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>戻り値  
 現在**cbrs _** コントロール バーの (コントロール バーのスタイル) 設定します。 参照してください[CControlBar::SetBarStyle](#setbarstyle)使用可能なスタイルの完全な一覧についてはします。  
  
### <a name="remarks"></a>コメント  
 処理しない**ws _** (ウィンドウ スタイル) のスタイル。  
  
##  <a name="getborders"></a>  CControlBar::GetBorders  
 コントロール バーの現在の境界線の値を返します。  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`コントロール バー オブジェクトのそれぞれの側の現在の幅をピクセル単位) を含むオブジェクトです。 たとえばの値、 `left` 、メンバーの[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト、左の境界線の幅は、します。  
  
##  <a name="getcount"></a>  CControlBar::GetCount  
 以外の数を返します`HWND`上の項目、`CControlBar`オブジェクト。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 非数`HWND`上の項目、`CControlBar`オブジェクト。 この関数に 0 を返します、 [CDialogBar](../../mfc/reference/cdialogbar-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 項目の種類によって異なります、派生オブジェクト: ペインについて[CStatusBar](../../mfc/reference/cstatusbar-class.md)オブジェクト、およびボタンおよび区切り記号の[CToolBar](../../mfc/reference/ctoolbar-class.md)オブジェクト。  
  
##  <a name="getdockingframe"></a>  CControlBar::GetDockingFrame  
 コントロール バーがドッキングされている現在のフレーム ウィンドウへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、フレーム ウィンドウへのポインターそれ以外の場合**NULL**です。  
  
 場合 (つまり、コントロール バーが固定されていない) 場合に、コントロール バーがフレーム ウィンドウにドッキングされていない、この関数は、親へのポインターを返します[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なコントロール バーの詳細については、次を参照してください。 [CControlBar::EnableDocking](#enabledocking)と[CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)です。  
  
##  <a name="isfloating"></a>  CControlBar::IsFloating  
 コントロール バーが浮動小数点またはドッキングされているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バーがフローティング状態以外の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 浮動小数点へのドッキング コントロール バーの状態を変更するを呼び出す[切り離すには](../../mfc/reference/cframewnd-class.md#floatcontrolbar)します。  
  
##  <a name="m_bautodelete"></a>  CControlBar::m_bAutoDelete  
 ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>コメント  
 `m_bAutoDelete` 型のパブリック変数**BOOL**です。  
  
 コントロール バー オブジェクトは通常、フレーム ウィンドウ オブジェクトに埋め込まれます。 この場合、 `m_bAutoDelete` 0 は、フレーム ウィンドウが破棄されると、埋め込まれたコントロール バー オブジェクトが破棄されるためです。  
  
 割り当てる場合、この変数を 0 以外の値を設定、`CControlBar`ヒープでオブジェクトする予定がない呼び出し**削除**です。  
  
##  <a name="m_pinplaceowner"></a>  CControlBar::m_pInPlaceOwner  
 コントロール バーのインプレース所有者です。  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="onupdatecmdui"></a>  CControlBar::OnUpdateCmdUI  
 このメンバー関数は、ツールバーまたはステータス バーの状態を更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pTarget`  
 アプリケーションのメイン フレーム ウィンドウへのポインター。 このポインターは、更新プログラムのメッセージのルーティングに使用されます。  
  
 `bDisableIfNoHndler`  
 更新ハンドラーがないコントロールが無効として自動的に表示されるかどうかを示すフラグです。  
  
### <a name="remarks"></a>コメント  
 更新するには、各ボタンまたはペインを使用して、`ON_UPDATE_COMMAND_UI`更新ハンドラーを適切に設定する、メッセージ マップにマクロです。 参照してください[ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)詳細については、このマクロを使用します。  
  
 `OnUpdateCmdUI` アプリケーションがアイドル状態のときに、フレームワークによって呼び出されます。 フレーム ウィンドウを更新する必要がありますできない、子ウィンドウを直接には、少なくとも表示されるフレーム ウィンドウの。 `OnUpdateCmdUI` 高度なオーバーライド可能です。  
  
##  <a name="setbarstyle"></a>  CControlBar::SetBarStyle  
 この関数を呼び出して、必要な設定**cbrs _** コントロール バーのスタイル。  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 コントロール バーのスタイルを指定します。 次の 1 つ以上を指定できます。  
  
- `CBRS_ALIGN_TOP` フレーム ウィンドウのクライアント領域の上部にドッキングするコントロール バーを使用できます。  
  
- `CBRS_ALIGN_BOTTOM` フレーム ウィンドウのクライアント領域の下部にドッキングするコントロール バーを使用できます。  
  
- `CBRS_ALIGN_LEFT` フレーム ウィンドウのクライアント領域の左側にドッキングするコントロール バーを使用できます。  
  
- `CBRS_ALIGN_RIGHT` フレーム ウィンドウのクライアント領域の右側にドッキングするコントロール バーを使用できます。  
  
- `CBRS_ALIGN_ANY` フレーム ウィンドウのクライアント領域の任意の辺にドッキングするコントロール バーを使用できます。  
  
- `CBRS_BORDER_TOP` 表示されるときに、コントロール バーの上端に描画される境界線が発生します。  
  
- `CBRS_BORDER_BOTTOM` 表示されるときに、コントロール バーの下端で描画される境界線が発生します。  
  
- `CBRS_BORDER_LEFT` 表示されるときにコントロール バーの左のエッジに描画される境界線が発生します。  
  
- `CBRS_BORDER_RIGHT` 表示されるときに、コントロール バーの右端に描画される境界線が発生します。  
  
- `CBRS_FLOAT_MULTI` フロートするか、1 つのミニフレーム ウィンドウ内に複数のコントロール バーを使用できます。  
  
- `CBRS_TOOLTIPS` コントロール バーに表示されるツール ヒントが発生します。  
  
- `CBRS_FLYBY` ツール ヒントと同時に更新するメッセージのテキストをによりします。  
  
- **CBRS_GRIPPER**グリッパー、バンドに使用されるような原因、 **CReBar** 、描画するオブジェクトを任意の`CControlBar`-クラスを派生します。  
  
### <a name="remarks"></a>コメント  
 影響しません、 **ws _** (ウィンドウ スタイル) 設定します。  
  
##  <a name="setborders"></a>  CControlBar::SetBorders  
 コントロール バーの境界線のサイズを設定するには、この関数を呼び出します。  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxLeft*  
 コントロール バーの左罫線の幅をピクセル単位で。  
  
 *cyTop*  
 コントロール バーの上罫線の高さをピクセル単位で。  
  
 *cxRight*  
 コントロール バーの右罫線の幅をピクセル単位で。  
  
 *cyBottom*  
 コントロール バーの下罫線の高さをピクセル単位で。  
  
 `lpRect`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)コントロール バー オブジェクトの各境界の現在の幅をピクセル単位) を含むオブジェクトです。  
  
### <a name="example"></a>例  
 次のコード例は、5 (ピクセル単位) をコントロール バーの上部と下部の境界線および左と右の境界線を 2 ピクセルに設定します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="setinplaceowner"></a>  CControlBar::SetInPlaceOwner  
 コントロール バーのインプレース所有者を変更します。  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、`CWnd`オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar クラス](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)   
 [CReBar クラス](../../mfc/reference/crebar-class.md)
