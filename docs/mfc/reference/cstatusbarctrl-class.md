---
title: CStatusBarCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b89f51fbcb3ca46afdb5ad56a6e162e7fe42cf0d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122896"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl クラス
Windows コモン ステータス バー コントロール の機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|`CStatusBarCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBarCtrl::Create](#create)|ステータス バー コントロールを作成し、それにアタッチ、`CStatusBarCtrl`オブジェクト。|  
|[CStatusBarCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでステータス バー コントロールを作成しにアタッチ、`CStatusBarCtrl`オブジェクト。|  
|[CStatusBarCtrl::DrawItem](#drawitem)|オーナー描画ステータス バー コントロールの変更のビジュアルな部分ときに呼び出されます。|  
|[CStatusBarCtrl::GetBorders](#getborders)|現在のステータス バー コントロールの水平方向および垂直の罫線の幅を取得します。|  
|[CStatusBarCtrl::GetIcon](#geticon)|現在のステータス バー コントロールの一部 (ウィンドウとも呼ばれます) のアイコンを取得します。|  
|[CStatusBarCtrl::GetParts](#getparts)|ステータス バー コントロールの部分の数を取得します。|  
|[CStatusBarCtrl::GetRect](#getrect)|ステータス バー コントロール内のパーツの外接する四角形を取得します。|  
|[Cstatusbarctrl::gettext](#gettext)|ステータス バー コントロールの特定の部分からテキストを取得します。|  
|[Cstatusbarctrl::gettextlength](#gettextlength)|ステータス バー コントロールの特定の部分からのテキストの文字の長さを取得します。|  
|[CStatusBarCtrl::GetTipText](#gettiptext)|ステータス バー内のウィンドウのツールヒントのテキストを取得します。|  
|[CStatusBarCtrl::IsSimple](#issimple)|簡易モードでは、ステータス ウィンドウ コントロールを確認します。|  
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|ステータス バーの背景色を設定します。|  
|[CStatusBarCtrl::SetIcon](#seticon)|ステータス バーで、ウィンドウのアイコンを設定します。|  
|[CStatusBarCtrl::SetMinHeight](#setminheight)|バーのコントロールの描画領域、ステータスの最小の高さを設定します。|  
|[CStatusBarCtrl::SetParts](#setparts)|ステータス バー コントロールと各部分の右端の座標の部分の数を設定します。|  
|[CStatusBarCtrl::SetSimple](#setsimple)|ステータス バー コントロールが単純なテキストを表示するか、設定を以前の呼び出しによってすべてのコントロール パーツが表示されるかどうかを指定`SetParts`です。|  
|[CStatusBarCtrl::SetText](#settext)|ステータス バー コントロールの特定の部分にテキストを設定します。|  
|[CStatusBarCtrl::SetTipText](#settiptext)|ステータス バーで、ウィンドウのツールヒント テキストを設定します。|  
  
## <a name="remarks"></a>Remarks  
 「ステータス バー コントロール」は、水平方向のウィンドウで、通常、アプリケーションがさまざまな種類のステータス情報を表示できます、親ウィンドウの下部に表示されます。 ステータス バー コントロールは、情報の 2 つ以上の種類を表示する部分に分けることができます。  
  
 このコントロール (したがって、`CStatusBarCtrl`クラス) は、Windows 95/98 および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 使用する方法についての`CStatusBarCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="create"></a>  CStatusBarCtrl::Create  
 ステータス バー コントロールを作成し、それにアタッチ、`CStatusBarCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 ステータス バー コントロールのスタイルを指定します。 ステータス バーに表示されているコントロールのスタイルの任意の組み合わせを適用[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)Windows SDK に含まれています。 このパラメーターは、WS_CHILD スタイルを指定する必要があります。 WS_VISIBLE スタイルする必要があります。  
  
 *rect*  
 ステータス バー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 *pParentWnd*  
 ステータス バー コントロールの親ウィンドウを通常を指定します、`CDialog`です。 NULL は指定できません。  
  
 *nID*  
 ステータス バー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CStatusBarCtrl` 2 つの手順でします。 最初に、コンス トラクターを呼び出しておよびを呼び出す`Create`、ステータス バー コントロールを作成しにアタッチする、`CStatusBarCtrl`オブジェクト。  
  
 親ウィンドウの下部では、ステータス ウィンドウの既定の位置が親ウィンドウのクライアント領域の上部に表示させる CCS_TOP スタイルを指定することができます。 ステータス ウィンドウの右端にあるサイズ変更グリップを含める SBARS_SIZEGRIP スタイルを指定することができます。 システム ステータス ウィンドウで描画場合でも、結果のサイズ変更グリップが機能していないため、CCS_TOP と SBARS_SIZEGRIP のスタイルを組み合わせることはお勧めできません。  
  
 拡張ウィンドウ スタイルを使用して、ステータス バーを作成するには、呼び出す[CStatusBarCtrl::CreateEx](#createex)の代わりに`Create`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CStatusBarCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成しに関連付けます、`CStatusBarCtrl`オブジェクト。  
  
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
 ステータス バー コントロールのスタイルを指定します。 ステータス バーに表示されているコントロールのスタイルの任意の組み合わせを適用[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)Windows SDK に含まれています。 このパラメーターは、WS_CHILD スタイルを指定する必要があります。 WS_VISIBLE スタイルする必要があります。  
  
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
  
##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl  
 `CStatusBarCtrl` オブジェクトを構築します。  
  
```  
CStatusBarCtrl();
```  
  
##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem  
 オーナー描画ステータス バー コントロールの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDrawItemStruct*  
 Long ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 `itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数では何も行いません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CStatusBarCtrl`オブジェクト。  
  
 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*関数はこのメンバーの前に終了します。  
  
##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders  
 水平および垂直の罫線および四角形の間の空白のステータス バー コントロールの現在の幅を取得します。  
  
```  
BOOL GetBorders(int* pBorders) const;  
  
BOOL GetBorders(
    int& nHorz,  
    int& nVert,  
    int& nSpacing) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pBorders*  
 3 つの要素を持つ整数配列のアドレスです。 最初の要素が水平方向の境界線の幅を受け取る、2 番目が垂直方向の境界線の幅を受け取るおよび四角形の間の境界線の幅を受け取ります。  
  
 *nHorz*  
 水平方向の境界線の幅を受け取る整数への参照。  
  
 *nVert*  
 垂直方向の境界線の幅を受け取る整数への参照。  
  
 *nSpacing*  
 四角形の間の境界線の幅を受け取る整数への参照。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 これらの罫線は、コントロールの端やテキストを含むコントロール内で四角形の間隔を決定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]  
  
##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon  
 現在のステータス バー コントロールの一部 (ウィンドウとも呼ばれます) のアイコンを取得します。  
  
```  
HICON GetIcon(int iPart) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*iPart*|取得するアイコンを含む部分の 0 から始まるインデックス。 このパラメーターが-1 の場合、ステータス バーは簡易モードのステータス バーと見なされます。|  
  
### <a name="return-value"></a>戻り値  
 アイコンへのハンドル場合、メソッドが成功しました。それ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [SB_GETICON](http://msdn.microsoft.com/library/windows/desktop/bb760744) Windows SDK で説明するメッセージ。  
  
 ステータス バー コントロールは、パーツとも呼ばれますテキスト出力ペインの行で構成されます。 ステータス バーの詳細については、次を参照してください。 [MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)と[CStatusBarCtrl オブジェクトのモードの設定](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_statusBar`、つまり現在のステータス バー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在のステータス バー コントロールの 2 つのペインにアイコンをコピーします。 前のセクションのコード例は、3 つのペインで、ステータス バー コントロールを作成し、最初のウィンドウにアイコンを追加します。 この例では、最初のウィンドウからアイコンを取得し、2 番目と 3 番目のウィンドウに追加されます。  
  
 [!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]  
  
##  <a name="getparts"></a>  CStatusBarCtrl::GetParts  
 ステータス バー コントロールの部分の数を取得します。  
  
```  
int GetParts(
    int nParts,  
    int* pParts) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nParts*  
 座標を取得する対象の部分の数。 このパラメーターがコントロール内の部分の数よりも大きい場合は、メッセージは、既存のパーツのみの座標を取得します。  
  
 *pParts*  
 指定された部分の数と同じ数の要素を持つ整数配列のアドレス*nParts*です。 配列内の各要素は、対応する部分の右端からのクライアント座標を受け取ります。 要素に設定されている場合、1 の部分の右端の位置までのステータス バーの右端です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、コントロール内の部分の数。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、また部分の指定した数値の右端の座標を取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]  
  
##  <a name="getrect"></a>  CStatusBarCtrl::GetRect  
 ステータス バー コントロール内のパーツの外接する四角形を取得します。  
  
```  
BOOL GetRect(
    int nPane,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nPane*  
 外接する四角形を取得する部分の 0 から始まるインデックス。  
  
 *lpRect*  
 アドレス、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]  
  
##  <a name="gettext"></a>  Cstatusbarctrl::gettext  
 ステータス バー コントロールの特定の部分からテキストを取得します。  
  
```  
CString GetText(
    int nPane,  
    int* pType = NULL) const;  
  
int GetText(
    LPCTSTR lpszText,  
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 テキストを受け取るバッファーのアドレス。 このパラメーターは、null で終わる文字列です。  
  
 *nPane*  
 テキストを取得する対象の部分の 0 から始まるインデックス。  
  
 *p 入力してください。*  
 型情報を受け取る整数へのポインター。 型には、これらの値のいずれかを指定できます。  
  
- **0**ステータス バーの平面より下位に表示する罫線とテキストを描画します。  
  
- 境界のない SBT_NOBORDERS テキストが描画されます。  
  
- SBT_POPOUT テキストがステータス バーの平面より上に表示する境界線が描画されます。  
  
- SBT_OWNERDRAW 場合、テキストが図面の種類、SBT_OWNERDRAW *p 入力してください*はこのメッセージを受信し、長さと操作の型ではなくテキストに関連付けられている 32 ビット値を返します。  
  
### <a name="return-value"></a>戻り値  
 テキストの文字の長さまたは[CString](../../atl-mfc-shared/reference/cstringt-class.md)現在のテキストを格納します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]  
  
##  <a name="gettextlength"></a>  Cstatusbarctrl::gettextlength  
 ステータス バー コントロールの特定の部分からのテキストの文字の長さを取得します。  
  
```  
int GetTextLength(
    int nPane,  
    int* pType = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nPane*  
 テキストを取得する対象の部分の 0 から始まるインデックス。  
  
 *p 入力してください。*  
 型情報を受け取る整数へのポインター。 型には、これらの値のいずれかを指定できます。  
  
- **0**ステータス バーの平面より下位に表示する罫線とテキストを描画します。  
  
- 境界のない SBT_NOBORDERS テキストが描画されます。  
  
- 親ウィンドウによって SBT_OWNERDRAW テキストが描画されます。  
  
- SBT_POPOUT テキストがステータス バーの平面より上に表示する境界線が描画されます。  
  
### <a name="return-value"></a>戻り値  
 テキストの文字の長さ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]  
  
##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText  
 ステータス バー内のウィンドウのツールヒントのテキストを取得します。  
  
```  
CString GetTipText(int nPane) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nPane*  
 ツールヒントのテキストが表示されるステータス バー ペインの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ツールヒントで使用するテキストを含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_GETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760751)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]  
  
##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple  
 簡易モードでは、ステータス ウィンドウ コントロールを確認します。  
  
```  
BOOL IsSimple() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ステータス ウィンドウのコントロールが単純なモードである場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_ISSIMPLE](http://msdn.microsoft.com/library/windows/desktop/bb760753)Windows SDK で説明されている。  
  
##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor  
 ステータス バーの背景色を設定します。  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 *cr*  
 新しい背景色を指定する COLORREF 値。 既定の背景色を使用して、ステータス バーが発生するときの値を指定します。  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)を前の既定の背景色を表す値です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760754)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]  
  
##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon  
 ステータス バーで、ウィンドウのアイコンを設定します。  
  
```  
BOOL SetIcon(
    int nPane,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPane*  
 アイコンを受信するペインの 0 から始まるインデックス。 このパラメーターが-1 の場合、ステータス バーは簡易ステータス バーと見なされます。  
  
 *hIcon*  
 設定するアイコンのハンドルです。 この値が NULL の場合は、アイコンが部分から削除されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_SETICON](http://msdn.microsoft.com/library/windows/desktop/bb760755)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CStatusBarCtrl::SetBkColor](#setbkcolor)です。  
  
##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight  
 バーのコントロールの描画領域、ステータスの最小の高さを設定します。  
  
```  
void SetMinHeight(int nMin);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMin*  
 最小の高さ (ピクセル単位) コントロールです。  
  
### <a name="remarks"></a>Remarks  
 高さの最小値の合計は、 *nMin*と (ピクセル単位)、ステータス バー コントロールの垂直方向の境界線の幅 2 回クリックします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]  
  
##  <a name="setparts"></a>  CStatusBarCtrl::SetParts  
 ステータス バー コントロールと各部分の右端の座標の部分の数を設定します。  
  
```  
BOOL SetParts(
    int nParts,  
    int* pWidths);
```  
  
### <a name="parameters"></a>パラメーター  
 *nParts*  
 設定する部分の数。 部分の数は 255 より大きい値にすることはできません。  
  
 *pWidths*  
 指定された部分と同じ数の要素を持つ整数配列のアドレス*nParts*です。 配列内の各要素は、対応する部分の右端の位置をクライアント座標を指定します。 要素には、1、その部分の右端の位置は、コントロールの右端に拡張します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]  
  
##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple  
 ステータス バー コントロールが単純なテキストを表示するか、設定を以前の呼び出しによってすべてのコントロール パーツが表示されるかどうかを指定[呼び出した](#setparts)です。  
  
```  
BOOL SetSimple(BOOL bSimple = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bSimple*  
 表示型のフラグ。 コントロールが単純なテキストを表示するこのパラメーターが TRUE の場合FALSE の場合は、複数の部分が表示されます。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションが変更された場合、ステータス バー コントロールから非単純単純なまたはその逆システムにはすぐに、コントロールが再描画します。  
  
##  <a name="settext"></a>  CStatusBarCtrl::SetText  
 ステータス バー コントロールの特定の部分にテキストを設定します。  
  
```  
BOOL SetText(
    LPCTSTR lpszText,  
    int nPane,  
    int nType);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 設定されるテキストを指定する null で終わる文字列のアドレス。 場合*タイプ*は SBT_OWNERDRAW、 *lpszText* 32 ビットのデータを表します。  
  
 *nPane*  
 設定される部分の 0 から始まるインデックス。 この値が 255 の場合、ステータス バー コントロールは 1 つの部分のみで構成される単純なコントロールと見なされます。  
  
 *タイプ*  
 描画操作の種類。 参照してください[SB_SETTEXT メッセージ](http://msdn.microsoft.com/library/bb760758\(vs.85\).aspx)使用可能な値の一覧についてはします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 メッセージには、テキストを表示する、新しいコントロールが WM_PAINT メッセージを次に受信され、変更されたコントロールの一部が無効になります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]  
  
##  <a name="settiptext"></a>  CStatusBarCtrl::SetTipText  
 ステータス バーで、ウィンドウのツールヒント テキストを設定します。  
  
```  
void SetTipText(
    int nPane,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPane*  
 ツールヒントのテキストが表示されるステータス バー ペインの 0 から始まるインデックス。  
  
 *pszTipText*  
 ツールヒント テキストを含む文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[SB_SETTIPTEXT](http://msdn.microsoft.com/library/windows/desktop/bb760759)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)
