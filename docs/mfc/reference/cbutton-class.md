---
title: CButton クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
dev_langs:
- C++
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edcf6fd613231567cbb54b95c8be924919d93269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cbutton-class"></a>CButton クラス
Windows のボタン コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|`CButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CButton::Create](#create)|Windows ボタン コントロールを作成し、それにアタッチ、`CButton`オブジェクト。|  
|[CButton::DrawItem](#drawitem)|オーナー描画を描画する上書き`CButton`オブジェクト。|  
|[CButton::GetBitmap](#getbitmap)|以前のビットマップのハンドルを取得[SetBitmap](#setbitmap)です。|  
|[CButton::GetButtonStyle](#getbuttonstyle)|ボタン コントロールのスタイルに関する情報を取得します。|  
|[CButton::GetCheck](#getcheck)|ボタン コントロールのチェックの状態を取得します。|  
|[CButton::GetCursor](#getcursor)|カーソルのイメージのハンドルが以前に設定と取得[以前](#setcursor)です。|  
|[CButton::GetIcon](#geticon)|既に設定アイコンのハンドルを取得[SetIcon](#seticon)です。|  
|[CButton::GetIdealSize](#getidealsize)|ボタン コントロールの適切なサイズを取得します。|  
|[CButton::GetImageList](#getimagelist)|ボタン コントロールのイメージ リストを取得します。|  
|[CButton::GetNote](#getnote)|現在のコマンド リンク コントロールの注釈のコンポーネントを取得します。|  
|[CButton::GetNoteLength](#getnotelength)|現在のコマンド リンク コントロールの注釈テキストの長さを取得します。|  
|[CButton::GetSplitGlyph](#getsplitglyph)|現在の分割ボタン コントロールに関連付けられたグリフを取得します。|  
|[CButton::GetSplitImageList](#getsplitimagelist)|現在の分割ボタン コントロールのイメージ リストを取得します。|  
|[CButton::GetSplitInfo](#getsplitinfo)|現在の分割ボタン コントロールを定義する情報を取得します。|  
|[CButton::GetSplitSize](#getsplitsize)|現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を取得します。|  
|[CButton::GetSplitStyle](#getsplitstyle)|現在の分割ボタン コントロールを定義する分割ボタン スタイルを取得します。|  
|[CButton::GetState](#getstate)|状態の確認、強調表示状態、およびボタン コントロールのフォーカス状態を取得します。|  
|[CButton::GetTextMargin](#gettextmargin)|ボタン コントロールのテキストの余白を取得します。|  
|[CButton::SetBitmap](#setbitmap)|ボタンに表示されるビットマップを指定します。|  
|[CButton::SetButtonStyle](#setbuttonstyle)|ボタンのスタイルを変更します。|  
|[CButton::SetCheck](#setcheck)|ボタン コントロールのチェックの状態を設定します。|  
|[CButton::SetCursor](#setcursor)|ボタンに表示されるカーソル イメージを指定します。|  
|[CButton::SetDropDownState](#setdropdownstate)|現在の分割ボタン コントロールのドロップダウンの状態を設定します。|  
|[CButton::SetIcon](#seticon)|ボタンに表示されるアイコンを指定します。|  
|[CButton::SetImageList](#setimagelist)|ボタン コントロールのイメージ リストを設定します。|  
|[CButton::SetNote](#setnote)|現在のコマンド リンク コントロールの注釈を設定します。|  
|[CButton::SetSplitGlyph](#setsplitglyph)|指定されたグリフを現在の分割ボタン コントロールに関連付けます。|  
|[CButton::SetSplitImageList](#setsplitimagelist)|イメージ リストを現在の分割ボタン コントロールに関連付けます。|  
|[CButton::SetSplitInfo](#setsplitinfo)|現在の分割ボタン コントロールを定義する情報を指定します。|  
|[CButton::SetSplitSize](#setsplitsize)|現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を設定します。|  
|[CButton::SetSplitStyle](#setsplitstyle)|現在の分割ボタン コントロールのスタイルを設定します。|  
|[CButton::SetState](#setstate)|ボタン コントロールの強調表示の状態を設定します。|  
|[CButton::SetTextMargin](#settextmargin)|ボタン コントロールのテキストの余白を設定します。|  
  
## <a name="remarks"></a>コメント  
 ボタン コントロールは、オンとオフのクリックして可能な小さな四角形の子ウィンドウです。 ボタンは、1 人またはグループに使用することができますとラベルを付けることができますか、またはテキストなしで表示されます。 ボタンは、ユーザーがクリックしたときに通常の外観を変更します。  
  
 一般的なボタンは、チェック ボックス、ラジオ ボタンとプッシュ ボタンです。 A`CButton`オブジェクトは、次のいずれかになることができますによると、[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)によって初期化時に指定された、[作成](#create)メンバー関数。  
  
 さらに、 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)から派生したクラス`CButton`ボタン コントロールのラベルがテキストではなくビットマップ イメージの作成をサポートします。 A`CBitmapButton`ボタンの下、重点を置いて、および状態を無効になっているは、個別のビットマップを持つことができます。  
  
 ダイアログ テンプレートから、またはコードで直接、ボタン コントロールを作成できます。 どちらの場合、コンス トラクターを呼び出して最初`CButton`構築するために、`CButton`オブジェクトです。 まず、**作成**、ウィンドウを作成するメンバー関数は、コントロールのボタンをクリックし、添付、`CButton`オブジェクト。  
  
 派生したクラスで、1 つプロセスは、構築`CButton`です。 呼び出しと派生クラスのコンス トラクターを記述**作成**から、コンス トラクター内で。  
  
 Windows のボタン コントロールからその親に送信される通知メッセージを処理する場合 (通常から派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。  
  
 各メッセージ マップ エントリは次の形式になります。  
  
 **On _** 通知 **(**`id`、 `memberFxn` **)**  
  
 ここで`id`通知を送信するコントロールの子ウィンドウ ID を指定し、`memberFxn`通知の処理を記述した親メンバー関数の名前を指定します。  
  
 親の関数プロトタイプは次のとおりです。  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 潜在的なメッセージ マップ エントリは次のとおりです。  
  
|マップのエントリ|親のときに送信しています.|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|ユーザーは、ボタンをクリックします。|  
|**ON_BN_DOUBLECLICKED**|ユーザーは、ボタンをダブルクリックします。|  
  
 作成する場合、`CButton`ダイアログ リソースからのオブジェクト、 `CButton`  ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CButton`ウィンドウ内でオブジェクトを破棄する必要があります。 作成する場合、`CButton`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**ボタン コントロールをユーザーがウィンドウを閉じるときに破棄するオブジェクト。 作成する場合、`CButton`スタック、またはそのオブジェクトが親ダイアログ オブジェクトに埋め込まれては自動的に破棄します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cbutton"></a>  CButton::CButton  
 `CButton` オブジェクトを構築します。  
  
```  
CButton();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="create"></a>  CButton::Create  
 Windows ボタン コントロールを作成し、それにアタッチ、`CButton`オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszCaption`  
 ボタン コントロールのテキストを指定します。  
  
 `dwStyle`  
 ボタン コントロールのスタイルを指定します。 任意の組み合わせを適用[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)ボタンにします。  
  
 `rect`  
 ボタン コントロールのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。  
  
 `pParentWnd`  
 通常、ボタン コントロールの親ウィンドウを指定します、`CDialog`です。 なければなりません**NULL**です。  
  
 `nID`  
 ボタン コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CButton` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出す**作成**、Windows ボタン コントロールを作成しにアタッチする、`CButton`オブジェクト。  
  
 場合、 **WS_VISIBLE**スタイルが与えられると、Windows は、ボタン コントロールをアクティブ化し、ボタンを表示するために必要なすべてのメッセージを送信します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)ボタン コントロールに。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**タブ移動順序に、ボタンを含める  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CButton::DrawItem  
 オーナー描画ボタンの外観が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)構造体。 構造体には、描画される項目および必要な図面の種類に関する情報が含まれています。  
  
### <a name="remarks"></a>コメント  
 なオーナー描画ボタンが、 **BS_OWNERDRAW**セットのスタイルを設定します。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CButton`オブジェクト。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はメンバーの前に終了します。  
  
 参照してください、[うち](../../mfc/reference/styles-used-by-mfc.md#button-styles)値のスタイルを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="getbitmap"></a>  CButton::GetBitmap  
 以前、ビットマップのハンドルを取得するには、このメンバー関数を呼び出す[SetBitmap](#setbitmap)、つまりボタンに関連付けられています。  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップへのハンドル。 **NULL**ビットマップが既に指定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle  
 ボタン コントロールのスタイルに関する情報を取得します。  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このボタンのスタイルを返します`CButton`オブジェクト。 この関数はだけを返す、[うち](../../mfc/reference/styles-used-by-mfc.md#button-styles)スタイル値は、任意の他のウィンドウ スタイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="getcheck"></a>  CButton::GetCheck  
 オプション ボタンまたはチェック ボックスのチェックの状態を取得します。  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタン コントロールからの戻り値が作成された、 **BS_AUTOCHECKBOX**、 **BS_AUTORADIOBUTTON**、 **BS_AUTO3STATE**、 **BS_CHECKBOX**、 **BS_RADIOBUTTON**、または**BS_3STATE**スタイルは、次の値のいずれか。  
  
|[値]|説明|  
|-----------|-------------|  
|**設定されています。**|ボタンの状態がオフになっています。|  
|**BST_CHECKED**|ボタンの状態がチェックされます。|  
|**BST_INDETERMINATE**|ボタンの状態が不定になります (にこのボタンは場合にのみ適用されます、 **BS_3STATE**または**BS_AUTO3STATE**スタイル)。|  
  
 その他のスタイルにこのボタンには場合、戻り値は**設定されている**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="getcursor"></a>  CButton::GetCursor  
 以前、カーソルのハンドルを取得するには、このメンバー関数を呼び出す[以前](#setcursor)、つまりボタンに関連付けられています。  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>戻り値  
 カーソル イメージへのハンドル。 **NULL**以前にカーソルが指定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="geticon"></a>  CButton::GetIcon  
 以前、アイコンのハンドルを取得するには、このメンバー関数を呼び出す[SetIcon](#seticon)、つまりボタンに関連付けられています。  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイコンにへのハンドル。 **NULL**以前にアイコンが指定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="getidealsize"></a>  CButton::GetIdealSize  
 ボタン コントロールの適切なサイズを取得します。  
  
```  
BOOL GetIdealSize(SIZE* psize);
```  
  
### <a name="parameters"></a>パラメーター  
 *psize*  
 ボタンの現在のサイズへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_GETIDEALSIZE**メッセージ、」の説明に従って、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)Windows SDK の「します。  
  
##  <a name="getimagelist"></a>  CButton::GetImageList  
 ボタン コントロールからのイメージ リストを取得するには、このメソッドを呼び出します。  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbuttonImagelist`  
 イメージ リストへのポインター、`CButton`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_GETIMAGELIST**メッセージ、」の説明に従って、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)Windows SDK の「します。  
  
##  <a name="getnote"></a>  CButton::GetNote  
 現在のコマンド リンク コントロールに関連付けられているメモのテキストを取得します。  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `lpszNote`|呼び出し元が割り当てと解放を担当する、バッファーへのポインター。 場合は、戻り値は`true`バッファーには、それ以外の現在のコマンド リンク コントロールに関連付けられている注釈のテキストが含まれています、バッファーは変更されません。|  
|[入力、出力] `cchNote`|符号なし整数の変数へのポインター。<br /><br /> 変数がで指定したバッファーのサイズを含むこのメソッドが呼び出されたときに、`lpszNote`パラメーター。<br /><br /> このメソッドが返す場合、戻り値が場合`true`変数には、現在のコマンド リンク コントロールに関連付けられている注釈のサイズが含まれています。 場合は、戻り値は`false`変数には、メモの格納に必要なバッファー サイズが含まれています。|  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロード、 [CString](../../atl-mfc-shared/using-cstring.md)を現在のコマンド リンク コントロールに関連付けられているメモのテキストを含むオブジェクト。  
  
 - または -  
  
 2 番目のオーバー ロードで`true`このメソッドが成功した、それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_COMMANDLINK`または`BS_DEFCOMMANDLINK`です。  
  
 このメソッドは、送信、 [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) Windows SDK で説明するメッセージ。  
  
##  <a name="getnotelength"></a>  CButton::GetNoteLength  
 現在のコマンド リンク コントロールの注釈テキストの長さを取得します。  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のコマンド リンク制御用の 16 ビット Unicode 文字で、メモのテキストの長さ。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_COMMANDLINK`または`BS_DEFCOMMANDLINK`です。  
  
 このメソッドは、送信、 [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) Windows SDK で説明するメッセージ。  
  
##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph  
 現在の分割ボタン コントロールに関連付けられたグリフを取得します。  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の分割ボタン コントロールに関連付けられたグリフの文字。  
  
### <a name="remarks"></a>コメント  
 グリフは、特定のフォントの文字の物理的に表したものです。 たとえば、分割ボタン コントロールは、チェック マークの Unicode 文字のグリフで装飾できます可能性があります (u+2713)。  
  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_GLYPH`フラグ、および、構造体送信、 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969)記載されているメッセージwindows SDK。 このメソッドは、グリフから取得メッセージの関数が戻るとき、`himlGlyph`構造体のメンバーです。  
  
##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList  
 取得、[イメージ リスト](../../mfc/reference/cimagelist-class.md)現在の分割ボタン コントロールです。  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_IMAGE`フラグ、および、構造体送信、 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969)記載されているメッセージwindows SDK。 このメソッドは、イメージの一覧から取得メッセージの関数が戻るとき、`himlGlyph`構造体のメンバーです。  
  
##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo  
 現在の分割ボタン コントロールの描画方法を決定するパラメーターを取得します。  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pInfo`|ポインター、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)現在の分割ボタン コントロールに関する情報を受け取る構造体。 呼び出し元は、構造体の割り当てをします。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、送信、 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK で説明するメッセージ。  
  
##  <a name="getsplitsize"></a>  CButton::GetSplitSize  
 現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を取得します。  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pSize`|ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)四角形の説明を受け取る。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタン コントロールを展開すると、リスト コントロールのページャー コントロールなどのドロップダウン コンポーネントを表示できます。 このメソッドは、ドロップダウンのコンポーネントを含む外接する四角形を取得します。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_SIZE`フラグ、および、構造体送信、 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969)記載されているメッセージwindows SDK。 このメソッドがから外接する四角形を取得するメッセージの関数が戻るとき、`size`構造体のメンバーです。  
  
##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle  
 現在の分割ボタン コントロールを定義する分割ボタン スタイルを取得します。  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割ボタンのスタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタンのスタイルは、配置、縦横比、および Windows が分割ボタン アイコンを描画するため、グラフィカルな形式を指定します。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_STYLE`フラグ、および、構造体送信、 [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969)記載されているメッセージwindows SDK。 このメソッドがから分割ボタンのスタイルを取得するメッセージの関数が戻るとき、`uSplitStyle`構造体のメンバーです。  
  
##  <a name="getstate"></a>  CButton::GetState  
 ボタン コントロールの状態を取得します。  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタン コントロールの現在の状態を示す値の組み合わせを含むビット フィールドです。 次の表は、使用可能な値を一覧表示します。  
  
|ボタンの状態|[値]|説明|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|初期状態です。|  
|`BST_CHECKED`|0x0001|ボタン コントロールがチェックされます。|  
|`BST_INDETERMINATE`|0x0002|不定 (のみ可能なボタン コントロールに 3 つの状態がある場合) です。|  
|`BST_PUSHED`|0x0004|ボタン コントロールをクリックします。|  
|`BST_FOCUS`|0x0008|ボタン コントロールにフォーカスが移動するとします。|  
  
### <a name="remarks"></a>コメント  
 ボタン コントロール、`BS_3STATE`または`BS_AUTO3STATE`ボタンのスタイルを不定状態の名前は 3 番目の状態を持つチェック ボックスを作成します。 不確定な状態では、このチェック ボックスがオンでもオンになっていないことを示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="gettextmargin"></a>  CButton::GetTextMargin  
 テキストの余白を取得するには、このメソッドを呼び出して、`CButton`オブジェクト。  
  
```  
BOOL GetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>パラメーター  
 `pmargin`  
 テキストの余白を指すポインター、`CButton`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 テキストの余白を返します。  
  
### <a name="remarks"></a>コメント  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_GETTEXTMARGIN**メッセージ、」の説明に従って、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)Windows SDK の「します。  
  
##  <a name="setbitmap"></a>  CButton::SetBitmap  
 新しいビットマップをボタンに関連付けるには、このメンバー関数を呼び出します。  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 ビットマップのハンドル。  
  
### <a name="return-value"></a>戻り値  
 以前、ボタンに関連付けられているビットマップのハンドル。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、既定で中央揃えボタンの表面に自動的に配置されます。 ビットマップが大きすぎる、ボタンのいずれかの側クリップされます。 次のように、他の配置オプションを選択できます。  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用する`SetBitmap`ボタンごとの 1 つだけのビットマップを使用します。 ボタンが押されたときにシフトし、右下に、ビットマップが表示されます。  
  
 関連付けが完了したら、ビットマップを解放を担当しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle  
 ボタンのスタイルを変更します。  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStyle`  
 指定します、[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)です。  
  
 `bRedraw`  
 ボタンを再描画されるかどうかを指定します。 0 以外の値には、ボタンが再描画します。 値 0 は、ボタンを再描画されません。 ボタンは既定では再描画されます。  
  
### <a name="remarks"></a>コメント  
 使用して、`GetButtonStyle`ボタンのスタイルを取得します。 完全なボタンのスタイルの下位ワードは、ボタンに固有のスタイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="setcheck"></a>  CButton::SetCheck  
 設定またはオプション ボタンまたはチェック ボックスのチェックの状態をリセットします。  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCheck`  
 チェックの状態を指定します。 このパラメーターには、次のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|**設定されています。**|ボタンの状態をオフに設定します。|  
|**BST_CHECKED**|チェック ボタンの状態を設定します。|  
|**BST_INDETERMINATE**|不確定なにボタンの状態を設定します。 この値は、ボタンがある場合のみ使用できます、 **BS_3STATE**または**BS_AUTO3STATE**スタイル。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、プッシュ ボタンに影響を与えません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="setcursor"></a>  CButton::SetCursor  
 新しいカーソルをボタンに関連付けるには、このメンバー関数を呼び出します。  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>パラメーター  
 `hCursor`  
 カーソルのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 以前、ボタンに関連付けられているカーソルのハンドルです。  
  
### <a name="remarks"></a>コメント  
 カーソルは既定で中央揃えボタンの表面に自動的に配置されます。 カーソルが大きすぎる、ボタンのいずれかの側クリップされます。 次のように、他の配置オプションを選択できます。  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用する`SetCursor`ボタンごとに 1 つだけのカーソルを使用します。 ボタンが押されたときにシフトし、右下にカーソルが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="setdropdownstate"></a>  CButton::SetDropDownState  
 現在の分割ボタン コントロールのドロップダウンの状態を設定します。  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fDropDown`|`true` 設定する`BST_DROPDOWNPUSHED`状態です。 それ以外の場合、`false`です。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 分割ボタン コントロールは、スタイルの`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`ボタンとその右側にドロップダウン矢印で構成されます。 詳細については、次を参照してください。[ボタン スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775951)です。 通常、ドロップ ダウン状態は、ユーザーがドロップダウン矢印をクリックしたときに設定されます。 コントロールのドロップ ダウン状態をプログラムで設定するのにには、このメソッドを使用します。 ドロップダウンの矢印は、状態を示す網掛けが描画されます。  
  
 このメソッドは、送信、 [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`、それが分割ボタン コントロールをプログラムでアクセスするために使用します。 次の例では、この変数を使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、ドロップダウン矢印をプッシュすることを示すために、分割ボタン コントロールの状態を設定します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired  
 現在のボタン コントロールの状態を設定`elevation required`、管理者特権でのセキュリティのアイコンを表示するコントロールに必要です。  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fElevationRequired`|`true` 設定する`elevation required`状態です。 それ以外の場合、`false`です。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタンやコマンドのリンク コントロールは、アクションの実行に管理者特権でのセキュリティ アクセス許可を必要とする場合は、コントロールを設定`elevation required`状態です。 その後、Windows では、コントロールのユーザー アカウント制御 (UAC) の盾アイコンが表示されます。 詳細についてを参照してください「のユーザー アカウント制御」 [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507)です。  
  
 このメソッドは、送信、 [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) Windows SDK で説明するメッセージ。  
  
##  <a name="seticon"></a>  CButton::SetIcon  
 新しいアイコンをボタンに関連付けるには、このメンバー関数を呼び出します。  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 アイコンのハンドル。  
  
### <a name="return-value"></a>戻り値  
 以前、ボタンに関連付けられているアイコンのハンドル。  
  
### <a name="remarks"></a>コメント  
 アイコンは、既定で中央揃えボタンの表面に自動的に配置されます。 ボタンのアイコンが大きすぎる、いずれかの側クリップされます。 次のように、他の配置オプションを選択できます。  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用する`SetIcon`ボタンごとの 1 つだけのアイコンを使用します。 ボタンが押されたときに、シフトし、右下に、アイコンが表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="setimagelist"></a>  CButton::SetImageList  
 イメージ リストを設定するには、このメソッドを呼び出して、`CButton`オブジェクト。  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbuttonImagelist`  
 新しいイメージ リストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_SETIMAGELIST**メッセージ、」の説明に従って、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)Windows SDK の「します。  
  
##  <a name="setnote"></a>  CButton::SetNote  
 現在のコマンド リンク コントロールのメモのテキストを設定します。  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `lpszNote`|コマンド リンク コントロールの注釈テキストとして設定されている Unicode 文字列へのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_COMMANDLINK`または`BS_DEFCOMMANDLINK`です。  
  
 このメソッドは、送信、 [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_cmdLink`、つまりコマンド リンク コントロールをプログラムでアクセスするために使用します。 次の例では、この変数を使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、コマンド リンク コントロールのメモのテキストを設定します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph  
 指定されたグリフを現在の分割ボタン コントロールに関連付けます。  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `chGlyph`|分割ボタンのドロップダウン矢印として使用するグリフを指定する文字。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタンのスタイルを持つコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 グリフは、特定のフォントの文字の物理的に表したものです。 `chGlyph`パラメーターは、グリフには使用されませんが、グリフのシステム定義のセットからのグリフを選択する代わりに使用します。 既定のドロップダウン矢印グリフは文字 '6' で指定され、黒いダウン-三角形 (U +0 25BC) の Unicode 文字のようになります。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_GLYPH`フラグと`himlGlyph`を持つメンバー、`chGlyph`パラメーター、および、構造体、送信[BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK に記載されているメッセージです。  
  
##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList  
 関連付けます、[イメージ リスト](../../mfc/reference/cimagelist-class.md)現在の分割ボタン コントロールにします。  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pSplitImageList`|ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)現在の分割ボタン コントロールに代入するオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_IMAGE`フラグと`himlGlyph`を持つメンバー、`pSplitImageList`パラメーター、および、構造体、送信[BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK に記載されているメッセージです。  
  
##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo  
 現在の分割ボタン コントロールの描画方法を決定するパラメーターを指定します。  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pInfo`|ポインター、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)を現在の分割ボタン コントロールを定義します。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 このメソッドは、送信、 [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`、それが分割ボタン コントロールをプログラムでアクセスするために使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、分割ボタンのドロップダウン矢印を使用するグリフを変更します。 この例には、上向き三角形のグリフ既定下向きの三角形のグリフが置換されます。 指定した文字に表示されるグリフの依存、`himlGlyph`のメンバー、`BUTTON_SPLITINFO`構造体。 下向きの三角形のグリフが文字 '6 で指定された' と、上向き三角形のグリフがある '5 文字で指定された' です。 比較については、便利なメソッドを参照してください。 [CButton::SetSplitGlyph](#setsplitglyph)です。  
  
 [!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="setsplitsize"></a>  CButton::SetSplitSize  
 現在の分割ボタン コントロールのドロップダウンのコンポーネントの外接する四角形を設定します。  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pSize`|ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)外接する四角形を記述する構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタン コントロールを展開すると、リスト コントロールのページャー コントロールなどのドロップダウン コンポーネントを表示できます。 このメソッドは、ドロップダウンのコンポーネントを含む外接する四角形のサイズを指定します。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_SIZE`フラグと`size`を持つメンバー、`pSize`パラメーター、および、構造体、送信[BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK に記載されているメッセージです。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`、それが分割ボタン コントロールをプログラムでアクセスするために使用します。 次の例では、この変数を使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例には、分割ボタンのドロップダウン矢印のサイズが 2 倍にします。  
  
 [!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle  
 現在の分割ボタン コントロールのスタイルを設定します。  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `uSplitStyle`|分割ボタンのスタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ボタン スタイルをコントロールでのみこのメソッドを使用して`BS_SPLITBUTTON`または`BS_DEFSPLITBUTTON`です。  
  
 分割ボタンのスタイルは、配置、縦横比、および Windows が分割ボタン アイコンを描画するため、グラフィカルな形式を指定します。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体。  
  
 このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955)構造体、`BCSIF_STYLE`フラグと`uSplitStyle`を持つメンバー、`uSplitStyle`パラメーター、および、構造体、送信[BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK に記載されているメッセージです。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_splitButton`、それが分割ボタン コントロールをプログラムでアクセスするために使用します。  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>例  
 次のコード例では、分割ボタンのドロップダウン矢印のスタイルを設定します。 `BCSS_ALIGNLEFT`スタイルが、ボタンの左側にある矢印を表示し、`BCSS_STRETCH`スタイルは、ボタンのサイズを変更するときにドロップダウン矢印の縦横比が保持されます。  
  
 [!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="setstate"></a>  CButton::SetState  
 ボタン コントロールが強調表示するかどうかを設定します。  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>パラメーター  
 *bHighlight*  
 ボタンを強調表示されるかどうかを指定します。 0 以外の値が; ボタンを強調表示します。値 0 は、任意の強調表示を削除します。  
  
### <a name="remarks"></a>コメント  
 ボタン コントロールの外部に影響を強調表示します。 オプション ボタンまたはチェック ボックスのチェックの状態に影響を与えません。  
  
 ユーザーがクリックして、マウスの左ボタンと、ボタン コントロールは自動的に強調表示されます。 マウス ボタンを離したときに削除、強調表示されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="settextmargin"></a>  CButton::SetTextMargin  
 テキストの余白を設定するには、このメソッドを呼び出して、`CButton`オブジェクト。  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>パラメーター  
 `pmargin`  
 新しいテキスト マージンへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 **BCM_SETTEXTMARGIN**メッセージ、」の説明に従って、[ボタン](http://msdn.microsoft.com/library/windows/desktop/bb775943)Windows SDK の「します。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [関数クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton クラス](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)
