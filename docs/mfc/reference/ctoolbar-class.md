---
title: CToolBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
dev_langs:
- C++
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a80ea4cb188d879b9af0a7901ffbe89b8673df6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ctoolbar-class"></a>CToolBar クラス
一連のビットマップ ボタンおよびオプションの区切り記号を含むコントロール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CToolBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CToolBar::CToolBar](#ctoolbar)|`CToolBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](#commandtoindex)|指定されたコマンド ID を持つボタンのインデックスを返します|  
|[用意されて](#create)|Windows ツールバーを作成し、それにアタッチ、`CToolBar`オブジェクト。|  
|[CToolBar::CreateEx](#createex)|作成、 `CToolBar` 、埋め込みの追加のスタイルを使用してオブジェクト`CToolBarCtrl`オブジェクト。|  
|[CToolBar::GetButtonInfo](#getbuttoninfo)|ID、スタイル、およびボタンのイメージ数を取得します。|  
|[CToolBar::GetButtonStyle](#getbuttonstyle)|ボタンのスタイルを取得します。|  
|[CToolBar::GetButtonText](#getbuttontext)|ボタンに表示されるテキストを取得します。|  
|[CToolBar::GetItemID](#getitemid)|ボタンまたは指定したインデックスに区切り線のコマンド ID を返します。|  
|[CToolBar::GetItemRect](#getitemrect)|指定したインデックス位置にある項目を表示する四角形を取得します。|  
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
|[CToolBar::LoadBitmap](#loadbitmap)|ビットマップ ボタンの画像を含むビットマップを読み込みます。|  
|[CToolBar::LoadToolBar](#loadtoolbar)|リソース エディターで作成されたツール バー リソースを読み込みます。|  
|[CToolBar::SetBitmap](#setbitmap)|ビットマップ イメージを設定します。|  
|[CToolBar::SetButtonInfo](#setbuttoninfo)|ID、スタイル、およびボタンのイメージ数を設定します。|  
|[CToolBar::SetButtons](#setbuttons)|ボタンのスタイルとボタンのイメージ、ビットマップ内のインデックスを設定します。|  
|[CToolBar::SetButtonStyle](#setbuttonstyle)|ボタンのスタイルを設定します。|  
|[CToolBar::SetButtonText](#setbuttontext)|ボタンに表示されるテキストを設定します。|  
|[CToolBar::SetHeight](#setheight)|ツールバーの高さを設定します。|  
|[CToolBar::SetSizes](#setsizes)|ボタンとビットマップのサイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 ボタンは、プッシュ ボタン、チェック ボックス ボタン、またはオプション ボタンのように動作します。 `CToolBar` オブジェクトはクラスから派生したフレーム ウィンドウ オブジェクトの通常の埋め込みメンバー [CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)です。  
  
 [CToolBar::GetToolBarCtrl](#gettoolbarctrl)、メンバー関数は、新しい MFC 4.0 を取得できるようにのツールバーをカスタマイズし、追加の機能の Windows コモン コントロールのサポートを利用します。 `CToolBar` メンバー関数は、Windows のコモン コントロール以外の機能のほとんどを与えるただし、呼び出す`GetToolBarCtrl`、Windows 95/98 ツールバーの特性のツールバーを与えることができます。 呼び出すと`GetToolBarCtrl`への参照が返されます、`CToolBarCtrl`オブジェクト。 参照してください[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)詳細については、Windows のコモン コントロールを使用してツールバーを設計します。 コモン コントロールの概要については、次を参照してください。[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)Windows SDK に含まれています。  
  
 Visual C は、ツールバーを作成する 2 つのメソッドを提供します。 リソース エディターを使用してツール バー リソースを作成するには、次の手順を実行します。  
  
1.  ツール バー リソースを作成します。  
  
2.  構築、`CToolBar`オブジェクト。  
  
3.  呼び出す、[作成](#create)(または[CreateEx](#createex)) を Windows ツールバーを作成し、アタッチして、`CToolBar`オブジェクト。  
  
4.  呼び出す[LoadToolBar](#loadtoolbar)ツール バー リソースを読み込めません。  
  
 それ以外の場合、これらの手順に従います。  
  
1.  構築、`CToolBar`オブジェクト。  
  
2.  呼び出す、[作成](#create)(または[CreateEx](#createex)) を Windows ツールバーを作成し、アタッチして、`CToolBar`オブジェクト。  
  
3.  呼び出す[LoadBitmap](#loadbitmap)ツール バー ボタンのイメージを含むビットマップを読み込めません。  
  
4.  呼び出す[SetButtons](#setbuttons)をボタンのスタイルを設定して、各ボタンをビットマップ内のイメージに関連付けます。  
  
 ツールバー内のすべてのボタン イメージは、各ボタンの 1 つのイメージを含める必要がありますが、1 つのビットマップから取得されます。 すべてのイメージが同じサイズにする必要があります。既定では 16 ピクセル、高さ 15 ピクセルです。 イメージはビットマップでサイド バイ サイドでなければなりません。  
  
 `SetButtons`関数はコントロール Id と、配列内の要素の数を指定する整数の配列へのポインターを受け取ります。 関数は、配列の対応する要素の値を各ボタンの ID を設定し、各ボタンにビットマップのボタンの画像の位置を指定するイメージのインデックスを割り当てます。 配列の要素が値を持つ場合**として**イメージのインデックスが割り当てられていません。  
  
 ビットマップ内のイメージの順序は、通常、画面に描画されますが、使用することができます、[です](#setbuttoninfo)イメージ順序と描画順序との間のリレーションシップを変更する関数。  
  
 ツールバー内のすべてのボタンは、同じサイズです。 既定値は、に従って 24 x 22 ピクセル*ソフトウェア設計のための Windows インターフェイス ガイドライン*です。 イメージとボタンのディメンション間で追加の空白を使用して、イメージの周囲に罫線を形成します。  
  
 各ボタンには、1 つのイメージがあります。 ボタンの状態のさまざまなおり、その 1 つのイメージからスタイル (押された状態で、ダウン、無効になっている、ダウン、無効になっており不確定) が生成されます。 ビットマップできますが、任意の色は黒、灰色の網掛けでの画像の最良の結果を実現できます。  
  
> [!WARNING]
> `CToolBar` 最大 16 色のビットマップをサポートしています。 ツール バー エディターからイメージを読み込むときに、Visual Studio は自動的に、必要な場合は 16 色のビットマップにイメージを変換し、イメージが変換された場合、警告メッセージが表示されます。 (、画像を編集するには外部エディターを使用して) 以上の 16 色でイメージを使用する場合、アプリケーションが予期しない動作があります。  
  
 ツール バー ボタンは、既定では、プッシュ ボタンを模倣します。 ただし、チェック ボックス ボタンまたはラジオ ボタンのツール バー ボタンを模倣もできます。 チェック ボックス ボタンにある 3 つの状態: チェック、消去、および不確定です。 ラジオ ボタンにある 2 つの状態: オンおよびオフにします。  
  
 配列を指すことがなく、個々 のボタンまたは区分線のスタイルを設定するには、呼び出す[に](#getbuttonstyle)、スタイルを取得し、呼び出す[SetButtonStyle](#setbuttonstyle)の代わりに`SetButtons`です。 `SetButtonStyle` 実行時に、ボタンのスタイルを変更するときに最も役立ちます。  
  
 ボタンに表示するテキストを割り当てるを呼び出す[GetButtonText](#getbuttontext) 、ボタンに表示し、呼び出すテキストを取得する[に](#setbuttontext)テキストを設定します。  
  
 チェック ボックス ボタンを作成するには、それを代入スタイル**TBBS_CHECKBOX**を使用して、または、`CCmdUI`オブジェクトの`SetCheck`でメンバー関数、`ON_UPDATE_COMMAND_UI`ハンドラー。 呼び出す`SetCheck`チェック ボックス ボタンにプッシュ ボタンをオンにします。 渡す`SetCheck`引数 0 オフ、1、または 2 の不確定です。  
  
 ラジオ ボタンを作成するには、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトの[SetRadio](../../mfc/reference/ccmdui-class.md#setradio)からのメンバー関数、`ON_UPDATE_COMMAND_UI`ハンドラー。 渡す`SetRadio`チェック以外に対して 0 の引数。 無線グループの相互に排他的な動作を提供するためにする必要があります`ON_UPDATE_COMMAND_UI`グループ内のボタンのすべてのハンドラー。  
  
 使用する方法についての`CToolBar`、記事を参照して[MFC ツールバーの実装](../../mfc/mfc-toolbar-implementation.md)と[テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex  
 このメンバー関数は、最初のツールバーのボタンの位置 0 から始まるコマンド ID と一致するインデックスを返します`nIDFind`です。  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFind`  
 ツール バー ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 ボタン、またはボタンは指定されたコマンド ID を持たない場合は-1 のインデックス  
  
##  <a name="create"></a>  用意されて  
 このメンバー関数は、Windows ツールバー (子ウィンドウ) を作成しに関連付けます、`CToolBar`オブジェクト。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ツールバーの親であるウィンドウへのポインター。  
  
 `dwStyle`  
 ツールバーのスタイル。 追加のスタイルは次のとおりです。  
  
- `CBRS_TOP` フレーム ウィンドウの上部には、コントロール バーです。  
  
- `CBRS_BOTTOM` フレーム ウィンドウの下部には、コントロール バーです。  
  
- `CBRS_NOALIGN` 親のサイズが変更されるときにコントロール バーの位置を変更できません。  
  
- `CBRS_TOOLTIPS` コントロール バーには、ツール ヒントが表示されます。  
  
- **CBRS_SIZE_DYNAMIC**コントロール バーは動的です。  
  
- **CBRS_SIZE_FIXED**コントロール バーを固定します。  
  
- **CBRS_FLOATING**コントロール バーがフローティング状態です。  
  
- `CBRS_FLYBY` ステータス バーには、ボタンについての情報が表示されます。  
  
- **CBRS_HIDE_INPLACE**コントロール バーは、ユーザーに表示されません。  
  
 `nID`  
 ツールバーの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 また、ツールバーの高さを既定値に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]  
  
##  <a name="createex"></a>  CToolBar::CreateEx  
 Windows ツールバー (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CToolBar`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,  
    CRect rcBorders = CRect(
    0, 
    0, 
    0, 
    0), 
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ツールバーの親であるウィンドウへのポインター。  
  
 `dwCtrlStyle`  
 埋め込まれたを作成するための追加スタイル[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)オブジェクト。 既定では、この値に設定**TBSTYLE_FLAT**です。 ツール バー スタイルの一覧については、次を参照してください。`dwStyle`です。  
  
 `dwStyle`  
 ツールバーのスタイル。 参照してください[ツール バー コントロールとボタンのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)適切なスタイルの一覧については、Windows SDK に含まれています。  
  
 *rcBorders*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md)ツールバー ウィンドウの境界線の幅を定義するオブジェクト。 これらの罫線は、既定では、これにより ツールバーでのウィンドウ枠線なしの結果として得られる 0,0,0,0 に設定されます。  
  
 `nID`  
 ツールバーの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 また、ツールバーの高さを既定値に設定します。  
  
 使用して`CreateEx`の代わりに[作成](#create)特定のスタイルは、埋め込みのツール バー コントロールの作成中に存在する必要がある場合、します。 たとえば、設定`dwCtrlStyle`に**TBSTYLE_FLAT&#124;バーオブジェクト**Internet Explorer 4 ツールバーに似たツールバーを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]  
  
##  <a name="ctoolbar"></a>  CToolBar::CToolBar  
 このメンバー関数を作成、`CToolBar`オブジェクトし、既定のサイズを設定します。  
  
```  
CToolBar();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、[作成](#create)ツールバー ウィンドウを作成するメンバー関数。  
  
##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo  
 このメンバー関数は、コントロールの ID、スタイル、およびツールバーのボタンまたはで指定された場所に区切り線のイメージのインデックスを取得します。 *nIndex です。*  
  
```  
void GetButtonInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& iImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ツール バー ボタンまたはその情報を取得する区切り記号のインデックス。  
  
 `nID`  
 参照、 **UINT**ボタンのコマンド ID に設定されています。  
  
 `nStyle`  
 参照、 **UINT**ボタンのスタイルに設定されています。  
  
 `iImage`  
 ビットマップ内のボタンのイメージのインデックスに設定されている整数への参照。  
  
### <a name="remarks"></a>コメント  
 これらの値がによって参照される変数に割り当てられた`nID`、 `nStyle`、および`iImage`です。 イメージのインデックスは、すべてのツール バー ボタンのイメージを含む、ビットマップ内の画像の位置です。 最初のイメージは、位置 0 です。  
  
 場合`nIndex`、区切り記号を指定`iImage`区切り記号の幅 (ピクセル単位) に設定されています。  
  
##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle  
 ボタンまたはツールバーの区分線のスタイルを取得するには、このメンバー関数を呼び出します。  
  
```  
UINT GetButtonStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得するツールバーのボタンまたは区切り記号のスタイルのインデックス。  
  
### <a name="return-value"></a>戻り値  
 ボタンまたはで指定された区切り記号のスタイル`nIndex`です。  
  
### <a name="remarks"></a>コメント  
 ボタンのスタイルは、ボタンの表示方法と、ユーザー入力に応答する方法を決定します。 参照してください[SetButtonStyle](#setbuttonstyle)ボタンのスタイルの例についてはします。  
  
##  <a name="getbuttontext"></a>  CToolBar::GetButtonText  
 ボタンに表示されるテキストを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetButtonText(int nIndex) const;  
  
void GetButtonText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得するテキストのインデックス。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得するテキストを格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A`CString`ボタンのテキストを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバーの 2 番目の形式の関数がいっぱいになった、`CString`文字列のテキストを持つオブジェクト。  
  
##  <a name="getitemid"></a>  CToolBar::GetItemID  
 このメンバー関数は、ボタンまたはで指定された区切り記号のコマンド ID を返します`nIndex`です。  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ID を取得する項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 ボタンまたはで指定された区切り記号のコマンド ID`nIndex`です。  
  
### <a name="remarks"></a>コメント  
 区切り記号を返す**として**です。  
  
##  <a name="getitemrect"></a>  CToolBar::GetItemRect  
 このメンバー関数、`RECT`にそのアドレスが含まれている構造`lpRect`ボタンまたはで指定された区切り記号の座標を持つ`nIndex`します。  
  
```  
virtual void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 四角形の座標の項目 (ボタンまたは区切り記号) のインデックスでは、取得します。  
  
 `lpRect`  
 アドレス、 [RECT](../../mfc/reference/rect-structure1.md)アイテムの座標を格納する構造。  
  
### <a name="remarks"></a>コメント  
 座標は、ツールバーの左上隅に対する相対 (ピクセル単位)。  
  
 使用して`GetItemRect`コンボ ボックスまたは他のコントロールを置換する区切り記号の座標を取得します。  
  
### <a name="example"></a>例  
  例を参照して[CToolBar::SetSizes](#setsizes)です。  
  
##  <a name="gettoolbarctrl"></a>  CToolBar::GetToolBarCtrl  
 このメンバー関数は、基になる一般的なコントロールに直接アクセスを許可します。  
  
```  
CToolBarCtrl& GetToolBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CToolBarCtrl` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 使用して`GetToolBarCtrl`Windows ツール バー コモン コントロールの機能を活用して、サポートを活用するために[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)ツールバーのカスタマイズを提供します。  
  
 コモン コントロールの使い方の詳細については、記事を参照してください。[コントロール](../../mfc/controls-mfc.md)と[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]  
  
##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap  
 このメンバー関数で指定されたビットマップを読み込む`lpszResourceName`または`nIDResource`です。  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 読み込まれるビットマップのリソース名へのポインター。  
  
 `nIDResource`  
 読み込まれる、ビットマップのリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、ツールバーのボタンごとに 1 つのイメージを含める必要があります。 イメージがない場合、標準のサイズ (16 ピクセル、高さ 15 ピクセル) の呼び出し[SetSizes](#setsizes)ボタンのサイズと、イメージを設定します。  
  
> [!WARNING]
> `CToolBar` 最大 16 色のビットマップをサポートしています。 ツール バー エディターからイメージを読み込むときに、Visual Studio は自動的に、必要な場合は 16 色のビットマップにイメージを変換し、イメージが変換された場合、警告メッセージが表示されます。 (、画像を編集するには外部エディターを使用して) 以上の 16 色でイメージを使用する場合、アプリケーションが予期しない動作があります。  
  
##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar  
 このメンバー関数で指定されたツールバーを読み込む`lpszResourceName`または`nIDResource`です。  
  
```  
BOOL LoadToolBar(LPCTSTR lpszResourceName);  
BOOL LoadToolBar(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 読み込まれる、ツールバーのリソース名へのポインター。  
  
 `nIDResource`  
 読み込まれる、ツールバーのリソース ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[ツール バー エディター](../../windows/toolbar-editor.md)の詳細については、ツール バー リソースを作成します。  
  
### <a name="example"></a>例  
  例を参照して[CToolBar::CreateEx](#createex)です。  
  
##  <a name="setbitmap"></a>  CToolBar::SetBitmap  
 ツールバーのビットマップ イメージを設定するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetBitmap(HBITMAP hbmImageWell);
```  
  
### <a name="parameters"></a>パラメーター  
 *hbmImageWell*  
 ツールバーに関連付けられているビットマップ イメージのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、呼び出す`SetBitmap`をユーザーが文書でボタンの動作を変更するアクションを実行した後は、ビットマップ イメージを変更します。  
  
##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo  
 ボタンのコマンド ID、スタイル、およびイメージの数を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetButtonInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int iImage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ボタンまたは情報を設定する対象の区切り記号の 0 から始まるインデックス。  
  
 `nID`  
 ボタンのコマンド ID が設定される値です。  
  
 `nStyle`  
 新しいボタンのスタイル。 次のボタンのスタイルがサポートされています。  
  
- **TBBS_BUTTON**標準プッシュ ボタン (既定値)  
  
- **TBBS_SEPARATOR**区切り記号  
  
- **TBBS_CHECKBOX**自動チェック ボックス ボタン  
  
- **TBBS_GROUP**ボタンのグループの開始をマーク  
  
- **TBBS_CHECKGROUP**チェック ボックス ボタンのグループの開始をマーク  
  
- **TBBS_DROPDOWN**ドロップダウン リストのボタンを作成します。  
  
- **TBBS_AUTOSIZE**ボタンのテキストではなく、イメージのサイズに基づくボタンの幅を計算します。  
  
- **TBBS_NOPREFIX**ボタンのテキストには、関連付けられているアクセラレータ プレフィックスはありません。  
  
 `iImage`  
 ボタンのイメージ、ビットマップ内の新しいインデックス。  
  
### <a name="remarks"></a>コメント  
 スタイルが設定されて区切り記号、 **TBBS_SEPARATOR**、この関数では、区切り記号の幅を設定に格納された値をピクセル単位で`iImage`です。  
  
> [!NOTE]
>  使用してボタンの状態を設定することも、`nStyle`パラメーターですただし、ボタンの状態がによって制御されるため、 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)ハンドラー、いずれかのステータスを使用して設定する`SetButtonInfo`は、次の中に失われますアイドル状態。処理しています。 参照してください[ユーザー インターフェイス オブジェクトの更新方法](../../mfc/how-to-update-user-interface-objects.md)と[TN031: コントロール バー](../../mfc/tn031-control-bars.md)詳細についてはします。  
  
 ビットマップ イメージとボタンについては、次を参照してください。、 [CToolBar](../../mfc/reference/ctoolbar-class.md)の概要と[CToolBar::LoadBitmap](#loadbitmap)です。  
  
##  <a name="setbuttons"></a>  CToolBar::SetButtons  
 このメンバー関数では、各ツール バー ボタンのコマンド ID を配列の対応する要素で指定された値に設定`lpIDArray`です。  
  
```  
BOOL SetButtons(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpIDArray`  
 コマンド Id の配列へのポインター。 できます**NULL**を空のボタンを割り当てます。  
  
 `nIDCount`  
 配列内の要素の数を指す`lpIDArray`です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 配列の要素が値を持つ場合**として**、区切り記号は、ツールバーの対応する位置に作成します。 この関数各ボタンのスタイルを設定するも**TBBS_BUTTON**と各区切り記号のスタイルを**TBBS_SEPARATOR**、し、各ボタンにイメージのインデックスを割り当てます。 イメージのインデックスは、ビットマップ内のボタンの画像の位置を指定します。  
  
 この関数は区切り記号にイメージのインデックスを割り当てませんため、ビットマップ内の区切り記号に対応する必要はありません。 場合は、ツールバーのボタン 0 の位置にある、1、および 3 および位置 2、イメージ、ビットマップ内の位置 0、1、および 2 の区切り記号がそれぞれ割り当てられてボタンの位置の 0、1、および 3 にします。  
  
 場合`lpIDArray`は**NULL**、この関数で指定された項目の数の領域が割り当てられます`nIDCount`です。 使用して[です](#setbuttoninfo)各項目の属性を設定します。  
  
##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle  
 ボタンまたは区切り記号、またはボタンをグループ化のスタイルを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ボタンまたはその情報を設定する区切り記号のインデックス。  
  
 `nStyle`  
 ボタンのスタイル。 次のボタンのスタイルがサポートされています。  
  
- **TBBS_BUTTON**標準プッシュ ボタン (既定値)  
  
- **TBBS_SEPARATOR**区切り記号  
  
- **TBBS_CHECKBOX**自動チェック ボックス ボタン  
  
- **TBBS_GROUP**ボタンのグループの開始をマーク  
  
- **TBBS_CHECKGROUP**チェック ボックス ボタンのグループの開始をマーク  
  
- **TBBS_DROPDOWN**ドロップダウン リストのボタンを作成  
  
- **TBBS_AUTOSIZE**ボタンの幅は、ボタンのテキストではなく、イメージのサイズに基づく計算します。  
  
- **TBBS_NOPREFIX**ボタンのテキストには、関連付けられているアクセラレータ プレフィックスはありません。  
  
### <a name="remarks"></a>コメント  
 ボタンのスタイルは、ボタンの表示方法と、ユーザー入力に応答する方法を決定します。  
  
 呼び出しの前に`SetButtonStyle`を呼び出し、[に](#getbuttonstyle)ボタンまたは区切り記号のスタイルを取得します。  
  
> [!NOTE]
>  使用してボタンの状態を設定することも、`nStyle`パラメーターですただし、ボタンの状態がによって制御されるため、 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)ハンドラー、いずれかのステータスを使用して設定する`SetButtonStyle`は、次の中に失われますアイドル状態。処理しています。 参照してください[ユーザー インターフェイス オブジェクトの更新方法](../../mfc/how-to-update-user-interface-objects.md)と[TN031: コントロール バー](../../mfc/tn031-control-bars.md)詳細についてはします。  
  
##  <a name="setbuttontext"></a>  CToolBar::SetButtonText  
 ボタンのテキストを設定するには、この関数を呼び出します。  
  
```  
BOOL SetButtonText(
    int nIndex,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 テキストを設定するボタンのインデックス。  
  
 `lpszText`  
 ボタンに設定するテキストを指します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CToolBar::GetToolBarCtrl](#gettoolbarctrl)です。  
  
##  <a name="setheight"></a>  CToolBar::SetHeight  
 このメンバー関数では、ツールバーの高さを設定 (ピクセル単位) で指定された値に`cyHeight`です。  
  
```  
void SetHeight(int cyHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `cyHeight`  
 ツールバーのピクセル単位の高さ。  
  
### <a name="remarks"></a>コメント  
 呼び出した後[SetSizes](#setsizes)、標準ツールバーの高さをオーバーライドするこのメンバー関数を使用します。 高さが小さすぎる場合は、下部にあるボタンがクリップされます。  
  
 この関数が呼び出されない場合、フレームワークは、ツールバーの高さを決定する、ボタンのサイズを使用します。  
  
##  <a name="setsizes"></a>  CToolBar::SetSizes  
 ツールバーのボタンをピクセル単位で指定された単位のサイズに設定するには、このメンバー関数を呼び出す*sizeButton*です。  
  
```  
void SetSizes(
    SIZE sizeButton,  
    SIZE sizeImage);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizeButton*  
 各ボタンのピクセル単位のサイズ。  
  
 `sizeImage`  
 各イメージのピクセル単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 `sizeImage`パラメーターは、ツールバーのビットマップのイメージのピクセル単位のサイズを含める必要があります。 内のディメンション*sizeButton*イメージと 7 ピクセル幅と 6 ピクセルの高さを保持するのに十分である必要があります。 この関数では、ボタンの高さにツールバーの高さも設定します。  
  
 このメンバー関数の呼び出しのみに従っていないツールバー*ソフトウェア設計のための Windows インターフェイス ガイドライン*ボタンおよびイメージのサイズに関する推奨事項です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [MFC サンプル DLGCBR32](../../visual-cpp-samples.md)   
 [MFC サンプル DOCKTOOL](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
