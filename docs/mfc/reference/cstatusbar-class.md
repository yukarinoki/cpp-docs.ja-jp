---
title: CStatusBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb5fb6b09ba6d27828c9f76a1b2ee21323197f6b
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122942"
---
# <a name="cstatusbar-class"></a>CStatusBar クラス
テキスト出力用のペインまたは "インジケーター" の行を持つコントロール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|`CStatusBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|指定したインジケーターの ID のインデックスを取得します。|  
|[CStatusBar::Create](#create)|ステータス バーを作成し、それにアタッチ、`CStatusBar`オブジェクト、および初期のフォントおよびバーの高さを設定します。|  
|[CStatusBar::CreateEx](#createex)|作成、 `CStatusBar` 、埋め込みの追加のスタイルを使用してオブジェクト`CStatusBarCtrl`オブジェクト。|  
|[CStatusBar::DrawItem](#drawitem)|オーナー描画ステータス バー コントロールの変更のビジュアルな部分ときに呼び出されます。|  
|[CStatusBar::GetItemID](#getitemid)|指定されたインデックスのインジケーターの ID を取得します。|  
|[CStatusBar::GetItemRect](#getitemrect)|取得には、指定されたインデックスの四角形が表示されます。|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|指定されたインデックスのインジケーターの ID、スタイル、および幅を取得します。|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|指定されたインデックスのインジケーターのスタイルを取得します。|  
|[CStatusBar::GetPaneText](#getpanetext)|指定されたインデックスのインジケーターのテキストを取得します。|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
|[CStatusBar::SetIndicators](#setindicators)|インジケーターの Id を設定します。|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|インジケーターの ID、スタイル、および指定されたインデックスの幅を設定します。|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|指定されたインデックスのインジケーターのスタイルを設定します。|  
|[CStatusBar::SetPaneText](#setpanetext)|指定されたインデックスのインジケーターのテキストを設定します。|  
  
## <a name="remarks"></a>Remarks  
 出力ペイン一般的な用途はメッセージ行およびステータス インジケーターとして使用します。 例としては、選択されたメニュー コマンドを簡単に説明するメニュー ヘルプ メッセージ行や SCROLL LOCK、NUM LOCK、およびその他のキーの状態を示すインジケーターです。  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)、メンバー関数は、新しい MFC 4.0 を取得できるようにのステータス バーのカスタマイズと追加の機能の Windows コモン コントロールのサポートを利用します。 `CStatusBar` メンバー関数は、Windows のコモン コントロール以外の機能のほとんどを与えるただし、呼び出す`GetStatusBarCtrl`、Windows 95/98 ステータス バーの特性の詳細も、ステータス バーを与えることができます。 呼び出すと`GetStatusBarCtrl`への参照が返されます、`CStatusBarCtrl`オブジェクト。 参照してください[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)詳細については、Windows のコモン コントロールを使用してツールバーを設計します。 コモン コントロールの概要については、次を参照してください。[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)Windows SDK に含まれています。  
  
 フレームワークは、0 の位置の左端のインジケーターの配列でインジケーターの情報を格納します。 ステータス バーを作成する場合は、フレームワークが、対応するインジケーターを関連付け Id の文字列の配列を使用します。 インジケーターにアクセスするのに、文字列 ID またはインデックスのいずれかを使用できます。  
  
 既定では、最初のインジケーターは"elastic": 実行されると、その他のウィンドウは、右側に配置されるため、他のインジケーター ペインで使用されていないステータス バーの長さをします。  
  
 ステータス バーを作成するには、次の手順を実行します。  
  
1.  構築、`CStatusBar`オブジェクト。  
  
2.  呼び出す、[作成](#create)(または[CreateEx](#createex))、ステータス バーのウィンドウを作成し、アタッチして、関数、`CStatusBar`オブジェクト。  
  
3.  呼び出す[SetIndicators](#setindicators)に関連付ける各インジケーターの文字列 ID です。  
  
 これには、ステータス バー ペインのテキストを更新する 3 つの方法があります。  
  
1.  呼び出す[とき](../../mfc/reference/cwnd-class.md#setwindowtext)ウィンドウ 0 のみのテキストを更新します。  
  
2.  呼び出す[CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext)ステータス バーの します。  
  
3.  呼び出す[SetPaneText](#setpanetext)を任意のウィンドウのテキストを更新します。  
  
 呼び出す[SetPaneStyle](#setpanestyle)をステータス バー ペインのスタイルを更新します。  
  
 使用する方法について`CStatusBar`、記事を参照して[MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)と[テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxext.h  
  
##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex  
 指定した ID のインジケーターのインデックスを取得します  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *始まり*  
 文字列を取得するインデックスを持つは、インジケーターの ID です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、インジケーターのインデックス成功しなかった場合は-1。  
  
### <a name="remarks"></a>Remarks  
 最初のインジケーターのインデックスは 0 です。  
  
##  <a name="create"></a>  CStatusBar::Create  
 ステータス バー (子ウィンドウ) を作成しに関連付けます、`CStatusBar`オブジェクト。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)ウィンドウ、ステータス バーの親であるオブジェクト。  
  
 *dwStyle*  
 ステータス バーのスタイルです。 標準の Windows だけでなく[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)、これらのスタイルがサポートされています。  
  
- フレーム ウィンドウの上部には、CBRS_TOP コントロール バーです。  
  
- フレーム ウィンドウの下部には、CBRS_BOTTOM コントロール バーです。  
  
- 親のサイズが変更されるときに CBRS_NOALIGN コントロール バーの位置を変更できません。  
  
 *nID*  
 ツールバーの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 初期のフォントを設定し、ステータス バーの高さを既定値です。  
  
##  <a name="createex"></a>  CStatusBar::CreateEx  
 この関数を作成し、ステータス バーの (子ウィンドウ) で、`CStatusBar`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)ウィンドウ、ステータス バーの親であるオブジェクト。  
  
 *ツール バー*  
 埋め込まれたを作成するための追加スタイル[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)オブジェクト。 既定値を指定せず、サイズ変更グリップまたはツールヒントのステータス バーをサポートします。 ステータス バーのスタイルがサポートされている次のとおりです。  
  
- SBARS_SIZEGRIP、ステータス バー コントロールには、ステータス バーの右端にあるサイズ変更グリップが含まれています。 サイズ変更グリップがサイズ変更境界線; に似ています。これは、ユーザーをクリックして親ウィンドウのサイズにドラッグされる四角形の領域です。  
  
- ステータス バーには、ツール ヒントがサポートされています。  
  
 これらのスタイルの詳細については、「 [CStatusBarCtrl の設定](../../mfc/settings-for-the-cstatusbarctrl.md)です。  
  
 *dwStyle*  
 ステータス バーのスタイル。 既定値は、フレーム ウィンドウの下部に表示されるステータス バーを作成することを指定します。 ステータス バーに表示されているコントロールのスタイルの任意の組み合わせを適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create)です。 ただし、このパラメーターは、WS_CHILD と WS_VISIBLE のスタイルを常に含める必要があります。  
  
 *nID*  
 ステータス バーの子ウィンドウ id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数も初期のフォントを設定し、設定、ステータス バーの高さを既定値です。  
  
 使用して`CreateEx`の代わりに[作成](#create)特定のスタイルが埋め込まれたステータス バー コントロールの作成中に存在する必要がある場合、します。 たとえば、設定*ツール バー*ステータス バーのオブジェクトにツールヒントを表示するにします。  
  
##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar  
 構築、`CStatusBar`オブジェクトは、必要に応じて、既定のステータス バーのフォントを作成し、フォントの特性を既定値に設定します。  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>  CStatusBar::DrawItem  
 このメンバー関数は、外観がオーナー描画ステータス バーの変更のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDrawItemStruct*  
 ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 `itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CStatusBar`オブジェクト。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバー関数の終了前にします。  
  
##  <a name="getitemid"></a>  CStatusBar::GetItemID  
 指定したインジケーターの ID を返します*nIndex*です。  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 ID を取得するインジケーターのインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインジケーターの ID *nIndex*です。  
  
##  <a name="getitemrect"></a>  CStatusBar::GetItemRect  
 指定したインジケーターの座標をコピー *nIndex*が指す構造体に*lpRect*です。  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 四角形の座標のインジケーターのインデックスでは、取得します。  
  
 *lpRect*  
 指す、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトで指定したインジケーターの座標を受け取る*nIndex*です。  
  
### <a name="remarks"></a>Remarks  
 座標は、ステータス バーの左上隅に対する相対 (ピクセル単位)。  
  
##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo  
 セット*nID*、 *nStyle*、および*cxWidth* ID、スタイル、およびによって指定された位置インジケーターのウィンドウの幅を*nIndex*です。  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 その情報を取得するペインのインデックス。  
  
 *nID*  
 ペインの ID に設定されている UINT への参照。  
  
 *nStyle*  
 ウィンドウのスタイルに設定されている UINT への参照。  
  
 *cxWidth*  
 ウィンドウの幅に設定されている整数への参照。  
  
##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle  
 ステータス バーのウィンドウのスタイルを取得するには、このメンバー関数を呼び出します。  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 スタイルを取得するペインのインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したステータス バー ペインのスタイル*nIndex*です。  
  
### <a name="remarks"></a>Remarks  
 ペインのスタイルは、ペインの表示方法を決定します。  
  
 ステータス バーで使用可能なスタイルの一覧は、次を参照してください。[作成](#create)です。  
  
##  <a name="getpanetext"></a>  CStatusBar::GetPaneText  
 ステータス バー ペインに表示されるテキストを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 テキストを取得するペインのインデックス。  
  
 *rString*  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得するテキストを表すオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A`CString`ペインのテキストを含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバーの 2 番目の形式の関数がいっぱいになった、`CString`文字列のテキストを持つオブジェクト。  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 このメンバー関数は、基になる一般的なコントロールに直接アクセスを許可します。  
  
```  
CStatusBarCtrl& GetStatusBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照が含まれています、 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 使用して`GetStatusBarCtrl`Windows ステータス バーのコモン コントロールの機能を活用して、サポートを活用するために[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)ステータス バーのカスタマイズを提供します。 コモン コントロールを使用すると、ステータス バーで、サイズ変更グリップを含むスタイルを指定するなど、ステータス バーを親ウィンドウのクライアント領域の上部に表示スタイルを指定することができます。  
  
 コモン コントロールの概要については、次を参照してください。[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)Windows SDK に含まれています。  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 各インジケーターの ID を配列の対応する要素で指定された値に設定*lpIDArray*各 ID で指定された文字列リソースを読み込み、およびインジケーターのテキストを文字列に設定します。  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpIDArray*  
 Id の配列へのポインター。  
  
 *nIDCount*  
 配列内の要素の数を指す*lpIDArray*です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 新しい ID、スタイル、および幅を指定したインジケーターのウィンドウを設定します。  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 スタイルを設定するインジケーター ペインのインデックス。  
  
 *nID*  
 インジケーター ペインの新しい ID です。  
  
 *nStyle*  
 インジケーター ペインの 新しいスタイル。  
  
 *cxWidth*  
 インジケーター ペインの新しい幅。  
  
### <a name="remarks"></a>Remarks  
 次のインジケーターのスタイルがサポートされています。  
  
- SBPS_NOBORDERS いいえ 3-D 枠線のウィンドウ。  
  
- テキスト「ポップ アウトします」ように罫線 SBPS_POPOUT 反転  
  
- SBPS_DISABLED テキストを描画しません。  
  
- 未使用のスペースを埋めます SBPS_STRETCH Stretch ウィンドウです。 ステータス バー ペインは 1 つだけでは、このスタイルを持つことができます。  
  
- SBPS_NORMAL いいえ stretch、罫線、またはポップアウトします。  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 ステータス バーのウィンドウのスタイルを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 スタイルを設定するペインのインデックス。  
  
 *nStyle*  
 スタイルを設定するペインのスタイルです。  
  
### <a name="remarks"></a>Remarks  
 ペインのスタイルは、ペインの表示方法を決定します。  
  
 ステータス バーで使用可能なスタイルの一覧は、次を参照してください。 [SetPaneInfo](#setpaneinfo)です。  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 ペインのテキストを指す文字列に設定するには、このメンバー関数を呼び出す*されている*です。  
  
```  
BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 設定するのには、テキストをウィンドウのインデックス。  
  
 *されています。*  
 新しいウィンドウ テキストへのポインター。  
  
 *b 更新*  
 TRUE の場合、テキストを設定した後、ウィンドウが無効にします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出した後`SetPaneText`、ステータス バーに新しいテキストを表示する UI 更新ハンドラーを追加する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [MFC サンプル DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl クラス](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
