---
title: CPrintInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1da952e14158ab92d888a703aa8451c0ca39406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376588"
---
# <a name="cprintinfo-structure"></a>CPrintInfo 構造体
印刷または印刷プレビュー ジョブに関する情報を格納します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|最初に印刷されるページ数を返します。|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|ドキュメントの最後のページ数を返します。|  
|[CPrintInfo::GetMinPage](#getminpage)|ドキュメントの最初のページ数を返します。|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|結合された DocObject 印刷ジョブで印刷する DocObject 項目の最初のページの前のページ数を返します。|  
|[CPrintInfo::GetToPage](#gettopage)|印刷する最後のページ数を返します。|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|ドキュメントの最後のページの数を設定します。|  
|[CPrintInfo::SetMinPage](#setminpage)|ドキュメントの最初のページの数を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|フレームワークが印刷ループを続行するかどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_bDirect](#m_bdirect)|使用せずに直接印刷 ダイアログ ボックスを表示するには) ドキュメントの印刷されているかどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|印刷中のドキュメントが DocObject かどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_bPreview](#m_bpreview)|ドキュメントがプレビューされているかどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|DocObject 印刷操作を指定します。|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|ユーザーが作成した構造体へのポインターが含まれています。|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|現在印刷中のページの数を識別します。|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|現在の印刷ジョブのオペレーティング システムによって割り当てられたジョブの数を指定します|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|プレビュー ウィンドウに表示されるページの数を指定します。1 または 2 のいずれか。|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|結合された DocObject 印刷ジョブでは、特定 DocObject の最初のページのオフセットを指定します。|  
|[CPrintInfo::m_pPD](#m_ppd)|ポインターが含まれています、`CPrintDialog`印刷 ダイアログ ボックスを使用するオブジェクト。|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|現在の使用可能なページ領域を定義する四角形を指定します。|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|ページ番号の表示の書式指定文字列が含まれています。|  
  
## <a name="remarks"></a>コメント  
 `CPrintInfo` 構造体は、基本クラスではありません。  
  
 オブジェクトを作成するために、フレームワーク`CPrintInfo`たびに、印刷または印刷プレビュー を選択して、コマンドが完了した時に破棄します。  
  
 `CPrintInfo` 印刷するページの範囲など、全体として印刷ジョブと現在印刷中のページなど、印刷ジョブの現在の状態の両方について説明します。 一部の情報が格納されている、関連する[CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトです。 このオブジェクトには、[印刷] ダイアログ ボックスで、ユーザーによって入力された値が含まれています。  
  
 A`CPrintInfo`オブジェクトは、印刷処理中に、フレームワークとビュー クラス間で渡され、2 つの情報を交換するために使用します。 たとえば、フレームワークに通知ビュー クラスの値を割り当てることによって印刷するドキュメントのページ、`m_nCurPage`のメンバー`CPrintInfo`以外の場合は、ビュー クラスは、値を取得し、指定したページの印刷を実行します。  
  
 別の例は、印刷されるまで、ドキュメントの長さは認識されません。 このような状況では、ビュー クラスが印刷されるたびをドキュメントの終わりをテストします。 最後に達すると、ビュー クラスを設定、`m_bContinuePrinting`のメンバー`CPrintInfo`に**FALSE**です。 これにより、印刷のループを停止するフレームワークです。  
  
 `CPrintInfo` メンバー関数によって使用される`CView`一覧表示 」も参照します"。 Microsoft Foundation Class ライブラリによって提供される印刷のアーキテクチャの詳細については、次を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)と[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と記事[。印刷](../../mfc/printing.md)と[印刷: マルチページ ドキュメント](../../mfc/multipage-documents.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CPrintInfo`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage  
 この関数では、最初のページを印刷する数を取得します。  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 印刷する最初のページの数。  
  
### <a name="remarks"></a>コメント  
 これは、[印刷] ダイアログ ボックスでユーザーが指定された値に格納されている、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバー。 ユーザーが値を指定していない場合は、既定では、ドキュメントの最初のページです。  
  
##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage  
 ドキュメントの最後のページの数を取得するには、この関数を呼び出します。  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの最後のページの数。  
  
### <a name="remarks"></a>コメント  
 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバー。  
  
##  <a name="getminpage"></a>  CPrintInfo::GetMinPage  
 ドキュメントの最初のページの数を取得するには、この関数を呼び出します。  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの最初のページの数。  
  
### <a name="remarks"></a>コメント  
 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバー。  
  
##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage  
 DocObject クライアントから複数の DocObject 項目を印刷する場合のオフセットを取得するには、この関数を呼び出します。  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 結合された DocObject 印刷ジョブで印刷する DocObject 項目の最初のページの前のページの数。  
  
### <a name="remarks"></a>コメント  
 この値がによって参照される、**される場合**メンバー。 ドキュメントの最初のページ番号になります、**される場合**値 + 1 の他のアクティブなドキュメント DocObject として印刷されたときにします。 **される場合**メンバーは有効な場合にのみ、 **m_bDocObject**値は**TRUE**です。  
  
##  <a name="gettopage"></a>  CPrintInfo::GetToPage  
 印刷する最後のページの数を取得するには、この関数を呼び出します。  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 印刷する最後のページの数。  
  
### <a name="remarks"></a>コメント  
 これは、[印刷] ダイアログ ボックスでユーザーが指定された値に格納されている、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバー。 ユーザーが値を指定していない場合は、既定では、ドキュメントの最後のページです。  
  
##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting  
 フレームワークが印刷ループを続行するかどうかを示すフラグが含まれています。  
  
### <a name="remarks"></a>コメント  
 印刷時の改ページを実行する場合このメンバーを設定することができます**FALSE**のオーバーライドで`CView::OnPrepareDC`ドキュメントの末尾に達しているとします。 使用して、印刷ジョブの開始時に、ドキュメントの長さを指定した場合、この変数を変更する必要はありません、`SetMaxPage`メンバー関数。 `m_bContinuePrinting`メンバーは型のパブリック変数**BOOL**です。  
  
##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect  
 フレームワークでは、このメンバーを設定**TRUE**印刷 ダイアログ ボックスは直接印刷をバイパスする場合**FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 シェルから、または印刷が終わったときに印刷するとき、印刷 ダイアログ ボックスがバイパスされる通常のコマンド ID を使用して**ID_FILE_PRINT_DIRECT**です。  
  
 通常、このメンバーしますが、変更した場合は、変更する前に呼び出し[しません](../../mfc/reference/cview-class.md#doprepareprinting)のオーバーライドで[き](../../mfc/reference/cview-class.md#onprepareprinting)です。  
  
##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject  
 印刷中のドキュメントが DocObject かどうかを示すフラグが含まれています。  
  
### <a name="remarks"></a>コメント  
 データ メンバー`m_dwFlags`と**される場合**は、このフラグがない限り、有効な**TRUE**です。  
  
##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview  
 ドキュメントがプレビューされているかどうかを示すフラグが含まれています。  
  
### <a name="remarks"></a>コメント  
 これは、ユーザーのコマンドを実行するに応じてフレームワークによって設定されます。 印刷 ダイアログ ボックスは、印刷プレビュー ジョブには表示されません。 **されます**メンバーは型のパブリック変数**BOOL**です。  
  
##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags  
 DocObject 印刷操作を指定するフラグの組み合わせが含まれています。  
  
### <a name="remarks"></a>コメント  
 有効な場合にのみデータ メンバー **m_bDocObject**は**TRUE**です。  
  
 フラグは、次の値の 1 つ以上を指定できます。  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData  
 ユーザーが作成した構造体へのポインターが含まれています。  
  
### <a name="remarks"></a>コメント  
 ビュー クラスに保存したくない印刷に固有のデータを格納するのにには、これを使用できます。 **M_lpUserData**メンバーは型のパブリック変数**LPVOID**です。  
  
##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage  
 現在のページの数が含まれています。  
  
### <a name="remarks"></a>コメント  
 フレームワークによって`CView::OnPrepareDC`と`CView::OnPrint`1 回; たびにこのメンバーの別の値を指定する、ドキュメントの各ページの範囲の値によって返される値`GetFromPage`により返された`GetToPage`です。 このメンバーを使用して`CView::OnPrepareDC`と`CView::OnPrint`ドキュメントの指定したページを印刷します。  
  
 プレビュー モードが最初に呼び出されたときに、フレームワークは、最初にプレビューするドキュメントのページを決定するには、このメンバーの値を読み取ります。 このメンバーの値を設定するには、オーバーライド`CView::OnPreparePrinting`プレビュー モードに入るときに、ドキュメント内のユーザーの現在位置を維持するためにします。 `m_nCurPage`メンバーは型のパブリック変数**UINT**です。  
  
##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber  
 現在の印刷ジョブのオペレーティング システムによって割り当てられたジョブの数を示します。  
  
### <a name="remarks"></a>コメント  
 この値は、 **SP_ERROR**場合は、ジョブがまだ印刷 (されている場合、`CPrintInfo`オブジェクトが新しく構築され、印刷に使用されていない)、またはジョブを開始でエラーが発生しました。  
  
##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages  
 プレビュー モードで表示されるページの数が含まれています1 または 2 のいずれかを指定できます。  
  
### <a name="remarks"></a>コメント  
 **M_nNumPreviewPages**メンバーは型のパブリック変数**UINT**です。  
  
##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage  
 結合された DocObject 印刷ジョブ内の特定 DocObject の最初のページの前のページ数が含まれています。  
  
##  <a name="m_ppd"></a>  CPrintInfo::m_pPD  
 ポインターが含まれています、`CPrintDialog`印刷ジョブの印刷 ダイアログ ボックスを表示するために使用します。  
  
### <a name="remarks"></a>コメント  
 `m_pPD`メンバーはパブリック変数へのポインターとして宣言されている`CPrintDialog`です。  
  
##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw  
 論理座標で、ページの使用可能な描画領域を指定します。  
  
### <a name="remarks"></a>コメント  
 オーバーライドでこれを参照することも`CView::OnPrint`します。 このメンバーは、ヘッダーとフッターを印刷した後、どのような領域が使えるの追跡に使用できます。 **M_rectDraw**メンバーは型のパブリック変数`CRect`です。  
  
##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc  
 印刷プレビュー中にページ番号を表示するために使用する書式指定文字列が含まれていますこの文字列は、単一ページの表示用と '\n' 文字で終了それぞれ二重ページ表示用の 2 つの部分文字列で構成されます。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、既定値として"ページ %u\npages%u-%u\n"を使用します。 オーバーライドで、書式指定文字列を指定する場合は、別の形式は、ページ番号を`CView::OnPreparePrinting`です。 **関数**メンバーは型のパブリック変数`CString`です。  
  
##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage  
 この関数では、ドキュメントの最後のページの数を指定します。  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMaxPage*  
 ドキュメントの最後のページの数。  
  
### <a name="remarks"></a>コメント  
 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバー。 印刷前に、ドキュメントの長さがわかっている場合は、この関数をオーバーライドから呼び出す`CView::OnPreparePrinting`です。 ドキュメントの長さは、[印刷] ダイアログ ボックスで、ユーザーによって指定された設定に依存する場合は、この関数をオーバーライドから呼び出す`CView::OnBeginPrinting`です。 不明な場合、ドキュメントの長さが印刷されるまでを使用して、`m_bContinuePrinting`印刷ループを制御するメンバー。  
  
### <a name="example"></a>例  
  例を参照して[き](../../mfc/reference/cview-class.md#onprepareprinting)です。  
  
##  <a name="setminpage"></a>  CPrintInfo::SetMinPage  
 この関数では、ドキュメントの最初のページの数を指定します。  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMinPage*  
 ドキュメントの最初のページの数。  
  
### <a name="remarks"></a>コメント  
 通常、ページ番号は 1 から始まります。 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバー。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [値](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [付け](../../mfc/reference/cview-class.md#onpreparedc)   
 [関数](../../mfc/reference/cview-class.md#onprepareprinting)   
 [のみ](../../mfc/reference/cview-class.md#onprint)



