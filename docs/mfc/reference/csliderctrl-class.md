---
title: CSliderCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c26df378c500b8c1384f7a357b93693b215ca10
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079617"
---
# <a name="csliderctrl-class"></a>CSliderCtrl クラス
Windows コモン スライダー コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|`CSliderCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|スライダー コントロールの現在の選択をクリアします。|  
|[CSliderCtrl::ClearTics](#cleartics)|スライダー コントロールから現在の目盛りを削除します。|  
|[CSliderCtrl::Create](#create)|スライダー コントロールを作成し、それにアタッチ、`CSliderCtrl`オブジェクト。|  
|[CSliderCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでスライダー コントロールを作成しにアタッチ、`CSliderCtrl`オブジェクト。|  
|[CSliderCtrl::GetBuddy](#getbuddy)|特定の場所のスライダー コントロールの連動ウィンドウへのハンドルを取得します。|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|スライダー コントロールのチャネルのサイズを取得します。|  
|[CSliderCtrl::GetLineSize](#getlinesize)|スライダー コントロールの行サイズを取得します。|  
|[CSliderCtrl::GetNumTics](#getnumtics)|スライダー コントロールの目盛りの数を取得します。|  
|[CSliderCtrl::GetPageSize](#getpagesize)|スライダー コントロールのページ サイズを取得します。|  
|[CSliderCtrl::GetPos](#getpos)|スライダーの現在の位置を取得します。|  
|[CSliderCtrl::GetRange](#getrange)|スライダーの最小値と最大位置を取得します。|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|スライダーの最大の位置を取得します。|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|スライダーの最小の位置を取得します。|  
|[CSliderCtrl::GetSelection](#getselection)|現在の選択範囲を取得します。|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|現在の trackbar コントロールのスライダーの長さを取得します。|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|スライダー コントロールのつまみのサイズを取得します。|  
|[CSliderCtrl::GetTic](#gettic)|指定された目盛りの位置を取得します。|  
|[CSliderCtrl::GetTicArray](#getticarray)|スライダー コントロールの目盛りの位置の配列を取得します。|  
|[CSliderCtrl::GetTicPos](#getticpos)|クライアント座標で指定された目盛りの位置を取得します。|  
|[CSliderCtrl::GetToolTips](#gettooltips)|存在する場合は、スライダー コントロールに割り当てられているツールヒント コントロールへのハンドルを取得します。|  
|[CSliderCtrl::SetBuddy](#setbuddy)|スライダー コントロールの連動ウィンドウとして、ウィンドウを割り当てます。|  
|[CSliderCtrl::SetLineSize](#setlinesize)|スライダー コントロールの行サイズを設定します。|  
|[CSliderCtrl::SetPageSize](#setpagesize)|スライダー コントロールのページ サイズを設定します。|  
|[CSliderCtrl::SetPos](#setpos)|スライダーの現在の位置を設定します。|  
|[CSliderCtrl::SetRange](#setrange)|スライダーの最小値と最大位置を設定します。|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|スライダーの最大の位置を設定します。|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|スライダーの最小の位置を設定します。|  
|[CSliderCtrl::SetSelection](#setselection)|現在の選択範囲を設定します。|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|現在の trackbar コントロールのスライダーの長さを設定します。|  
|[CSliderCtrl::SetTic](#settic)|指定された目盛りの位置を設定します。|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|スライダー コントロールの増分ごとに目盛りの間隔を設定します。|  
|[CSliderCtrl::SetTipSide](#settipside)|Trackbar コントロールで使用するツール ヒント コントロールを位置。|  
|[CSliderCtrl::SetToolTips](#settooltips)|スライダー コントロールにツールヒント コントロールを割り当てます。|  
  
## <a name="remarks"></a>Remarks  
 「スライダー コントロール」(trackbar とも呼ばれます) は、スライダーと省略可能な目盛りを含むウィンドウ。 ユーザーは、スライダーを移動し、マウスまたは方向キーを使用して、コントロールは、変更を示す通知メッセージを送信します。  
  
 スライダー コントロールは、ユーザーを範囲に、不連続値または一連の連続する値を選択する場合に便利です。 たとえば、スライダー コントロールを使用して、特定の目盛りをスライダーを移動することによって、キーボードのリピート間隔を設定するユーザーを許可する可能性があります。  
  
 このコントロール (したがって、`CSliderCtrl`クラス) は、Windows 95/98 および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 作成するときに指定する単位で、スライダーが移動します。 たとえば、スライダーが 5 の範囲を指定する場合、スライダー 6 つの位置: スライダー コントロールと、範囲内でインクリメントごとに 1 つの位置の左側に位置します。 通常、これらの各位置が、目盛りによって識別されます。  
  
 コンス トラクターを使用して、スライダーを作成して、`Create`のメンバー関数`CSliderCtrl`です。 スライダー コントロールを作成した後にメンバー関数を使用することができます`CSliderCtrl`多くのプロパティを変更します。 変更行うことができますにはには、スライダーの最小値と最大位置を設定、目盛りを描画、選択範囲の設定、スライダーの位置が含まれます。  
  
 使用する方法について`CSliderCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="clearsel"></a>  CSliderCtrl::ClearSel  
 スライダー コントロールの現在の選択をクリアします。  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bRedraw*  
 フラグを再描画します。 このパラメーターは場合**TRUE**スライダーが、選択が解除された後に再描画されます。 それ以外の場合、スライダーが再描画されません。  
  
##  <a name="cleartics"></a>  CSliderCtrl::ClearTics  
 スライダー コントロールから現在の目盛りを削除します。  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bRedraw*  
 フラグを再描画します。 このパラメーターが場合**TRUE**スライダーが目盛りがクリアされた後に再描画されます。 それ以外の場合、スライダーが再描画されません。  
  
##  <a name="create"></a>  CSliderCtrl::Create  
 スライダー コントロールを作成し、それにアタッチ、`CSliderCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 スライダー コントロールのスタイルを指定します。 任意の組み合わせを適用[スライダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)コントロールに、Windows SDK に記述されている。  
  
 *rect*  
 スライダー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 *pParentWnd*  
 通常、スライダー コントロールの親ウィンドウを指定します、`CDialog`です。 なければなりません**NULL**です。  
  
 *nID*  
 スライダー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CSliderCtrl` 2 つの手順でします。 最初に、コンス トラクターを呼び出しておよびを呼び出す`Create`、スライダー コントロールを作成しにアタッチする、`CSliderCtrl`オブジェクト。  
  
 設定値は、によって`dwStyle`、スライダー コントロールは垂直または水平方向の方向を持つことができます。 いずれかの側では、目盛りが持てる側、またはどちらもします。 連続値の範囲を指定するも使用できます。  
  
 スライダー コントロールに拡張ウィンドウ スタイルを適用するには、呼び出す[CreateEx](#createex)の代わりに`Create`です。  
  
##  <a name="createex"></a>  CSliderCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成しに関連付けます、`CSliderCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 *dwStyle*  
 スライダー コントロールのスタイルを指定します。 任意の組み合わせを適用[スライダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)コントロールに、Windows SDK に記述されている。  
  
 *rect*  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体*pParentWnd*です。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl  
 `CSliderCtrl` オブジェクトを構築します。  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy  
 特定の場所のスライダー コントロールの連動ウィンドウへのハンドルを取得します。  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *fLocation*  
 2 つの関連ウィンドウ ハンドルを取得するを示すブール値。 次のいずれかの値になります。  
  
- **TRUE**つまみの左側にある関連ウィンドウ ハンドルを取得します。 スライダー コントロールで使用する場合、`TBS_VERT`スタイル、スライダーの上にある関連メッセージを取得します。  
  
- **FALSE**つまみの右側にある関連ウィンドウ ハンドルを取得します。 スライダー コントロールで使用する場合、`TBS_VERT`スタイル、スライダーを下にある関連メッセージを取得します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)が連動ウィンドウによって指定された位置であるオブジェクトを`fLocation`、または**NULL**関連ウィンドウがその場所に存在しない場合。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178)Windows SDK で説明されている。 スライダー コントロールのスタイルの説明は、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)Windows SDK に含まれています。  
  
##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect  
 スライダー コントロールのチャネルの外接する四角形の位置とサイズを取得します。  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lprc*  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)チャネルの位置とサイズを格納しているオブジェクトの外接する四角形、関数が戻るときにします。  
  
### <a name="remarks"></a>Remarks  
 チャネルは、スライダーが移動すると、範囲を選択すると、強調表示を含む領域です。  
  
##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize  
 スライダー コントロールの行のサイズを取得します。  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールの行のサイズ。  
  
### <a name="remarks"></a>Remarks  
 行サイズに影響をどの程度スライダーが移動、 **TB_LINEUP**と**TB_LINEDOWN**通知します。 行サイズの既定の設定は 1 です。  
  
##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics  
 スライダー コントロールの目盛りの数を取得します。  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールでの目盛りの数。  
  
##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize  
 スライダー コントロールのページのサイズを取得します。  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールのページのサイズ。  
  
### <a name="remarks"></a>Remarks  
 ページ サイズに影響をどの程度スライダーが移動、 **TB_PAGEUP**と**TB_PAGEDOWN**通知します。  
  
##  <a name="getpos"></a>  CSliderCtrl::GetPos  
 スライダー コントロールのスライダーの現在位置を取得します。  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在位置を返します。  
  
##  <a name="getrange"></a>  CSliderCtrl::GetRange  
 スライダー コントロールのスライダーの最大と最小の位置を取得します。  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nMin*  
 最小の位置を受け取る整数への参照。  
  
 *nMax*  
 最大の位置を受け取る整数への参照。  
  
### <a name="remarks"></a>Remarks  
 この関数によって参照される整数に値をコピーする*nMin*と*nMax*です。  
  
##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax  
 スライダー コントロールのスライダーの最大の位置を取得します。  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの最大の位置。  
  
##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin  
 スライダー コントロールのスライダーの最小位置を取得します。  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの最小位置。  
  
##  <a name="getselection"></a>  CSliderCtrl::GetSelection  
 スライダー コントロールの現在の選択範囲の開始と終了位置を取得します。  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nMin*  
 現在の選択範囲の開始位置を受け取る整数への参照。  
  
 *nMax*  
 現在の選択範囲の終了位置を受け取る整数への参照。  
  
##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength  
 現在の trackbar コントロールのスライダーの長さを取得します。  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、スライダーの長さ。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) Windows SDK で説明するメッセージ。  
  
##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect  
 スライダー コントロールのスライダー (つまみ) に外接する四角形の位置とサイズを取得します。  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lprc*  
 ポインター、`CRect`関数が返す場合、スライダーの外接する四角形を格納しているオブジェクト。  
  
##  <a name="gettic"></a>  CSliderCtrl::GetTic  
 スライダー コントロールの目盛りの位置を取得します。  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *返します*  
 目盛りを識別する 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された目盛りまたは場合は、1 の位置*返します*有効なインデックスが指定されていません。  
  
##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray  
 スライダー コントロールの目盛りの位置を格納する配列のアドレスを取得します。  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールの目盛りの位置を格納する配列のアドレス。  
  
##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos  
 ティックのスライダー コントロール内の物理の現在位置を取得します。  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *返します*  
 目盛りを識別する 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された目盛りまたは場合は、1 のクライアント座標で物理的な位置。*返します*有効なインデックスが指定されていません。  
  
##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips  
 存在する場合は、スライダー コントロールに割り当てられているツールヒント コントロールへのハンドルを取得します。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクト、または**NULL**ツール ヒントが使用されていない場合。 スライダー コントロールを使用しない場合、 **TBS_TOOLTIPS**スタイル、戻り値は**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209)Windows SDK で説明されている。 このメンバー関数によって返される注、`CToolTipCtrl`コントロールへのハンドルではなくオブジェクト。  
  
 スライダー コントロールのスタイルの説明は、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)Windows SDK に含まれています。  
  
##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy  
 スライダー コントロールの連動ウィンドウとして、ウィンドウを割り当てます。  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndBuddy*  
 ポインター、`CWnd`スライダー コントロールのメンバーとして設定されるオブジェクト。  
  
 *fLocation*  
 関連ウィンドウを表示する場所を指定する値。 この値は、次のいずれかになります。  
  
- **TRUE** trackbar コントロールで使用する場合、つまみの左側に表示されます、`TBS_HORZ`スタイル。 トラック バーで使用する場合、`TBS_VERT`スタイルを trackbar コントロールの上に表示されます。  
  
- **FALSE** trackbar コントロールで使用する場合、つまみの右側に表示されます、`TBS_HORZ`スタイル。 トラック バーで使用する場合、`TBS_VERT`スタイルを trackbar コントロールの下に表示されます。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)その場所にあるスライダー コントロールに割り当てられていたオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213)Windows SDK で説明されている。 このメンバー関数へのポインターを使用して`CWnd`戻り値とパラメーターの両方のウィンドウ ハンドルではなく、オブジェクトです。  
  
 スライダー コントロールのスタイルの説明は、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)Windows SDK に含まれています。  
  
##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize  
 スライダー コントロールの行のサイズを設定します。  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSize*  
 スライダー コントロールの新しい行のサイズ。  
  
### <a name="return-value"></a>戻り値  
 前の行サイズ。  
  
### <a name="remarks"></a>Remarks  
 行サイズに影響をどの程度スライダーが移動、 **TB_LINEUP**と**TB_LINEDOWN**通知します。  
  
##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize  
 スライダー コントロールのページのサイズを設定します。  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSize*  
 スライダー コントロールの新しいページ サイズです。  
  
### <a name="return-value"></a>戻り値  
 前のページ サイズ。  
  
### <a name="remarks"></a>Remarks  
 ページ サイズに影響をどの程度スライダーが移動、 **TB_PAGEUP**と**TB_PAGEDOWN**通知します。  
  
##  <a name="setpos"></a>  CSliderCtrl::SetPos  
 スライダー コントロールのスライダーの現在の位置を設定します。  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPos*  
 新しいスライダー位置を指定します。  
  
##  <a name="setrange"></a>  CSliderCtrl::SetRange  
 スライダー コントロールのスライダーの範囲 (最小値と最大位置) を設定します。  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMin*  
 最小のスライダーの位置。  
  
 *nMax*  
 スライダーの最大の位置。  
  
 *bRedraw*  
 再描画フラグ。 このパラメーターが場合**TRUE**スライダーが再描画される範囲を設定した後です。 それ以外の場合、スライダーが再描画されません。  
  
##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax  
 スライダー コントロールのスライダーの最大範囲を設定します。  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMax*  
 スライダーの最大の位置。  
  
 *bRedraw*  
 再描画フラグ。 このパラメーターが場合**TRUE**スライダーが再描画される範囲を設定した後です。 それ以外の場合、スライダーが再描画されません。  
  
##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin  
 スライダー コントロールのスライダーの最小の範囲を設定します。  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMin*  
 最小のスライダーの位置。  
  
 *bRedraw*  
 再描画フラグ。 このパラメーターが場合**TRUE**スライダーが再描画される範囲を設定した後です。 それ以外の場合、スライダーが再描画されません。  
  
##  <a name="setselection"></a>  CSliderCtrl::SetSelection  
 スライダー コントロールの現在の選択範囲の開始と終了位置を設定します。  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMin*  
 スライダーの位置を開始しています。  
  
 *nMax*  
 スライダーの位置を終了しています。  
  
##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength  
 現在の trackbar コントロールのスライダーの長さを設定します。  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*されて*|ピクセル単位で、スライダーの長さです。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、trackbar コントロールに設定されている必要があります[TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147)スタイル。  
  
 このメソッドは、送信、 [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_sliderCtrl`、つまり現在 trackbar コントロールにアクセスするために使用します。 また、変数が定義されています`thumbLength`、つまり trackbar コントロールのつまみのコンポーネントの既定の長さを格納するために使用します。 これらの変数は、次の例で使用されます。  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例は、trackbar コントロールのつまみのコンポーネントを既定の長さ 2 倍に設定します。  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>  CSliderCtrl::SetTic  
 スライダー コントロールの目盛りの位置を設定します。  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>パラメーター  
 *返します*  
 目盛りの位置。 このパラメーターは、正の値を指定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 目盛りが設定されている場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq  
 スライダーの目盛りでマークの表示頻度を設定します。  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFreq*  
 目盛りの頻度です。  
  
### <a name="remarks"></a>Remarks  
 たとえば、頻度が 2 に設定されている場合、スライダーの範囲内の他のすべての増分の目盛りが表示されます。 頻度が 1 の既定の設定 (つまり、範囲のすべての増分値が目盛りに関連付けられて)。  
  
 コントロールを作成する必要があります、`TBS_AUTOTICKS`この関数を使用するスタイルです。 詳細については、次を参照してください。 [CSliderCtrl::Create](#create)です。  
  
##  <a name="settipside"></a>  CSliderCtrl::SetTipSide  
 Trackbar コントロールで使用するツール ヒント コントロールを位置。  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>パラメーター  
 *nLocation*  
 ツール ヒント コントロールを表示する位置を表す値。 使用可能な値の一覧は、Win32 メッセージを参照してください。 [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240)Windows SDK で説明されている。  
  
### <a name="return-value"></a>戻り値  
 ツール ヒント コントロールの以前の場所を表す値。 戻り値では、可能な値のいずれかと等しい*nLocation*です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して**TBM_SETTIPSIDE**Windows SDK で説明されている。 スライダー コントロールを使用する、 **TBS_TOOLTIPS**ツールヒントの表示スタイルを設定します。 スライダー コントロールのスタイルの説明は、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)Windows SDK に含まれています。  
  
##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips  
 スライダー コントロールにツールヒント コントロールを割り当てます。  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndTip*  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)スライダー コントロールで使用するツール ヒントを含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242)Windows SDK で説明されている。 スライダー コントロールを作成すると、 **TBS_TOOLTIPS**スタイル、スライダーの現在の位置を表示する、スライダーの横に表示される既定のツールヒント コントロールを作成します。 スライダー コントロールのスタイルの説明は、次を参照してください。 [Trackbar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760147)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl クラス](../../mfc/reference/cprogressctrl-class.md)
