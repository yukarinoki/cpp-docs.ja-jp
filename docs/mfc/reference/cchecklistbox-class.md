---
title: CCheckListBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
dev_langs:
- C++
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 998a2124d80a03946df1cfeeb4a0223ccbf55b24
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956568"
---
# <a name="cchecklistbox-class"></a>CCheckListBox クラス
Windows のチェックリスト ボックスの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[サンプル](#cchecklistbox)|`CCheckListBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Windows のチェックリスト ボックスを作成し、それにアタッチ、`CCheckListBox`オブジェクト。|  
|[:Drawitem](#drawitem)|オーナー描画リスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CCheckListBox::Enable](#enable)|有効またはチェックリスト ボックスの項目を無効にします。|  
|[CCheckListBox::GetCheck](#getcheck)|項目のチェック ボックスの状態を取得します。|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|コントロールのチェック ボックスのスタイルを取得します。|  
|[CCheckListBox::IsEnabled](#isenabled)|アイテムが有効になっているかどうかを判断します。|  
|[CCheckListBox::MeasureItem](#measureitem)|オーナー描画スタイルをリスト ボックスが作成されるときに、フレームワークによって呼び出されます。|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|項目のチェック ボックスの位置を取得するためにフレームワークによって呼び出されます。|  
|[CCheckListBox::SetCheck](#setcheck)|項目のチェック ボックスの状態を設定します。|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|コントロールのチェック ボックスのスタイルを設定します。|  
  
## <a name="remarks"></a>Remarks  
 「チェックリスト ボックス」には、ファイル名などのアイテムの一覧が表示されます。 リスト内の各項目は、ユーザーがオンまたはオフを隣のチェック ボックスがします。  
  
 `CCheckListBox` オーナー描画コントロールに対してのみ、一覧に含まれるテキスト文字列を超えるためです。 簡単に言うと、チェックリスト ボックスにはテキスト文字列とチェック ボックスが含まれていますが、すべてのテキストにする必要はありません。 たとえば、一連の各項目の横にあるチェック ボックスが小さいビットマップのことができます。  
  
 独自のチェックリスト ボックスを作成する必要がありますから独自のクラスを派生させる`CCheckListBox`です。 独自のクラスを派生させる記述するには、派生クラスのコンス トラクターを呼び出す`Create`です。  
  
 リスト ボックスからその親に送信される Windows の通知メッセージを処理する場合 (通常から派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。  
  
 各メッセージ マップ エントリは次の形式になります。  
  
 **On _** 通知 **(**`id`、 `memberFxn` **)**  
  
 ここで`id`通知を送信するコントロールの子ウィンドウ ID を指定し、`memberFxn`通知の処理を記述した親メンバー関数の名前を指定します。  
  
 親の関数プロトタイプは次のとおりです。  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 特に関連する 1 つだけのメッセージ マップ エントリがある`CCheckListBox`(メッセージ マップのエントリも参照してください。 しかし、 [CListBox](../../mfc/reference/clistbox-class.md))。  
  
- **ON_CLBN_CHKCHANGE**ユーザーが項目のチェック ボックスをオンの状態を変更します。  
  
 既定値を使用することができます、チェックリスト ボックスが既定のチェックリスト ボックス (それぞれの左側に既定のサイズのチェック ボックスを使用した文字列の一覧) の場合は、 [:drawitem](#drawitem)チェックリスト ボックスを描画します。 それ以外の場合、オーバーライドする必要があります、 [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem)関数および[:drawitem](#drawitem)と[CCheckListBox::MeasureItem](#measureitem)関数。  
  
 チェックリスト ボックスは、ダイアログ テンプレートから、またはコードで直接作成できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cchecklistbox"></a>  サンプル  
 `CCheckListBox` オブジェクトを構築します。  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CCheckListBox` 2 つのステップ内のオブジェクト。 最初から派生するクラスを定義`CCheckListBox`、まず`Create`、Windows のチェックリスト ボックスの初期化し、にアタッチする、`CCheckListBox`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>  CCheckListBox::Create  
 Windows のチェックリスト ボックスを作成し、それにアタッチ、`CCheckListBox`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 チェックリスト ボックスのスタイルを指定します。 スタイルである必要があります**LBS_HASSTRINGS** 、 **LBS_OWNERDRAWFIXED** (リスト内のすべての項目は、同じ高さ) または**LBS_OWNERDRAWVARIABLE** (リスト内の項目ではさまざまな高さ)。 このスタイルは、その他と組み合わせることができます[リスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)を除く**LBS_USETABSTOPS**です。  
  
 *rect*  
 チェックリスト ボックスのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 *pParentWnd*  
 チェックリスト ボックスの親ウィンドウを指定します (通常、`CDialog`オブジェクト)。 なければなりません**NULL**です。  
  
 *nID*  
 チェックリスト ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CCheckListBox` 2 つのステップ内のオブジェクト。 派生するクラスを最初に、定義`CcheckListBox`し`Create`、Windows のチェックリスト ボックスの初期化し、にアタッチする、`CCheckListBox`です。 参照してください[サンプル](#cchecklistbox)サンプルについてはします。  
  
 ときに`Create`を実行する Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)チェックリスト ボックス コントロールするメッセージです。  
  
 既定では、これらのメッセージが処理されます、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、メッセージ マップを追加、派生クラスとメンバー関数が、前のメッセージ ハンドラーをオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)チェックリスト ボックス コントロールに。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_VSCROLL**垂直スクロール バーを追加するには  
  
- **WS_HSCROLL**水平スクロール バーを追加するには  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**コントロールのタブ オーダーを許可するには  
  
##  <a name="drawitem"></a>  :Drawitem  
 オーナー描画のチェックリスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDrawItemStruct*  
 Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 **ItemAction**と**itemState**のメンバー、`DRAWITEMSTRUCT`構造体は、実行するのには、描画の動作を定義します。  
  
 既定では、この関数は、左側に既定のサイズのチェック ボックスに文字列ごとの一覧から成る既定 チェック ボックスの一覧を描画します。 チェック ボックスの一覧のサイズは、1 つで指定された[作成](#create)です。  
  
 チェックリスト ボックスされない文字列リスト、可変サイズの項目、または、左上にいないチェック ボックスなど、既定ではないオーナー描画チェックリスト ボックスの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバー関数の終了前にします。  
  
 チェックリスト ボックス スタイルのチェックリスト ボックスの項目はすべて同じ高さではない場合、(で指定された`Create`) する必要があります**一定**、オーバーライドする必要がありますと、 [MeasureItem](#measureitem)関数。  
  
##  <a name="enable"></a>  CCheckListBox::Enable  
 有効にするにまたはチェックリスト ボックスの項目を無効にするには、この関数を呼び出します。  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 有効にするチェックリスト ボックスの項目のインデックス。  
  
 *bEnabled*  
 項目が有効になっているかどうかを指定します。  
  
##  <a name="getcheck"></a>  CCheckListBox::GetCheck  
 指定されたチェック ボックスの状態を取得します。  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 リスト ボックスに含まれているチェック ボックスの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定されたチェック ボックスの状態。 次の表は、使用可能な値を一覧表示します。  
  
|[値]|説明|  
|-----------|-----------------|  
|`BST_CHECKED`|チェック ボックスをオンします。|  
|`BST_UNCHECKED`|チェック ボックスはチェックされません。|  
|`BST_INDETERMINATE`|チェック ボックスをオン状態が不定になります。|  
  
##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle  
 この関数では、チェックリスト ボックスのスタイルを取得します。  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのチェック ボックスのスタイルです。  
  
### <a name="remarks"></a>Remarks  
 可能なスタイルのについては、次を参照してください。[有効なスタイル](#setcheckstyle)です。  
  
##  <a name="isenabled"></a>  CCheckListBox::IsEnabled  
 アイテムが有効になっているかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 項目が有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="measureitem"></a>  CCheckListBox::MeasureItem  
 既定以外のスタイルのチェックリスト ボックスが作成されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMeasureItemStruct*  
 Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。  
  
### <a name="remarks"></a>Remarks  
 既定では、このメンバー関数では何も行いません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`チェックリスト ボックスの項目のサイズの Windows に通知する構造体。 チェックリスト ボックスがで作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)リスト ボックス内の各項目のスタイル、フレームワークからこのメンバー関数。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。  
  
##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition  
 フレームワークは、項目のチェック ボックスのサイズと位置を取得するには、この関数を呼び出します。  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectItem*  
 位置とリスト アイテムのサイズ。  
  
 *rectCheckBox*  
 既定の位置とサイズ、項目のチェック ボックスをオンします。  
  
### <a name="return-value"></a>戻り値  
 位置と項目のチェック ボックスのサイズ。  
  
### <a name="remarks"></a>Remarks  
 既定の実装は、既定の位置とサイズのチェック ボックスにのみを返します ( `rectCheckBox`)。 既定は、チェック ボックスは、アイテムの左上隅に配置し、標準のチェック ボックスのサイズです。 場合、右側のチェック ボックスまたはチェック ボックスを拡大または縮小した位置である可能性があります。 このような場合は、オーバーライド`OnGetCheckPosition` チェック ボックスの位置とサイズ内に項目を変更します。  
  
##  <a name="setcheck"></a>  CCheckListBox::SetCheck  
 指定されたチェック ボックスの状態を設定します。  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 リスト ボックスに含まれているチェック ボックスの 0 から始まるインデックス。  
  
 *nCheck*  
 指定されたチェック ボックスのボタンの状態。 使用可能な値は、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 次の表に、可能な値、 *nCheck*パラメーター。  
  
|[値]|説明|  
|-----------|-----------------|  
|**BST_CHECKED**|指定されたチェック ボックスを選択します。|  
|**設定されています。**|指定されたチェック ボックスをオフにします。|  
|**BST_INDETERMINATE**|不確定なチェック ボックスを指定した状態に設定します。<br /><br /> この状態は、チェック ボックスのスタイルが場合にのみ`BS_AUTO3STATE`または`BS_3STATE`です。 詳細については、次を参照してください。[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。|  
  
##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle  
 チェックリスト ボックスのチェック ボックスのスタイルを設定するには、この関数を呼び出します。  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStyle*  
 チェックリスト ボックスのチェック ボックスのスタイルを決定します。  
  
### <a name="remarks"></a>Remarks  
 有効なスタイルは次のとおりです。  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 詳細については、これらのスタイルは、次を参照してください。[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル TSTCON](../../visual-cpp-samples.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)
