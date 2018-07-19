---
title: CRichEditView クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
dev_langs:
- C++
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ece09b51dba7be272a208478d48196024189180e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853525"
---
# <a name="cricheditview-class"></a>CRichEditView クラス
[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)と[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|`CRichEditView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|現在の選択範囲と重ならないようにダイアログ ボックスに移動します。|  
|[CRichEditView::CanPaste](#canpaste)|リッチ エディット ビューに貼り付けることができるデータがクリップボードに含まれるかどうかを指示します。|  
|[CRichEditView::DoPaste](#dopaste)|リッチ エディット ビューには、OLE 項目を貼り付けます。|  
|[CRichEditView::FindText](#findtext)|待機カーソルを呼び出して、指定したテキストを検索します。|  
|[CRichEditView::FindTextSimple](#findtextsimple)|指定したテキストを検索します。|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|現在の選択の属性を書式設定文字を取得します。|  
|[CRichEditView::GetDocument](#getdocument)|関連するへのポインターを取得します。 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)します。|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|リッチ エディット ビューの現在位置で有効になっている OLE 項目を取得します。|  
|[CRichEditView::GetMargins](#getmargins)|リッチ エディット ビューの余白を取得します。|  
|[CRichEditView::GetPageRect](#getpagerect)|リッチ エディット ビューのページの四角形を取得します。|  
|[CRichEditView::GetPaperSize](#getpapersize)|リッチ エディット ビューの用紙サイズを取得します。|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|段落の現在の選択の属性を取得します。|  
|[CRichEditView::GetPrintRect](#getprintrect)|リッチ エディット ビューの印刷の四角形を取得します。|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|リッチ エディット ビューの印刷の幅を取得します。|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|リッチ エディット コントロールを取得します。|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|リッチ エディット ビューから選択した項目を取得します。|  
|[CRichEditView::GetTextLength](#gettextlength)|リッチ エディット ビュー内のテキストの長さを取得します。|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|バイト リッチ エディット ビューのいずれかの文字の数を取得します。 長さを確認する方法の拡張フラグの一覧です。|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|OLE アイテムとしてファイルを挿入します。|  
|[CRichEditView::InsertItem](#insertitem)|OLE 項目としては、新しい項目を挿入します。|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|リッチ エディットまたはテキスト形式のデータがクリップボードに含まれるかどうかを指示します。|  
|[CRichEditView::OnCharEffect](#onchareffect)|現在の選択範囲の書式設定文字を切り替えます。|  
|[CRichEditView::OnParaAlign](#onparaalign)|段落の配置を変更します。|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|パブリック メンバー関数の文字コマンド UI を更新します。|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|段落のパブリック メンバー関数のコマンドの UI を更新します。|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|指定した四角形内の指定したテキストの書式を設定します。|  
|[CRichEditView::PrintPage](#printpage)|指定されたページ内の指定したテキストの書式を設定します。|  
|[CRichEditView::SetCharFormat](#setcharformat)|現在の選択の属性を書式設定文字を設定します。|  
|[CRichEditView::SetMargins](#setmargins)|このリッチ マージンを設定では、ビューを編集します。|  
|[CRichEditView::SetPaperSize](#setpapersize)|リッチ エディット ビューの用紙サイズを設定します。|  
|[CRichEditView::SetParaFormat](#setparaformat)|段落の現在の選択の属性を設定します。|  
|[CRichEditView::TextNotFound](#textnotfound)|コントロールの検索の内部状態をリセットします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|リッチ エディット ビューの範囲でクリップボード オブジェクトを取得します。|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|ダウン右マウス ボタンを使用するコンテキスト メニューを取得します。|  
|[CRichEditView::IsSelected](#isselected)|指定した OLE アイテムが選択されているかどうかを示します。|  
|[CRichEditView::OnFindNext](#onfindnext)|次の部分文字列の出現箇所を検索します。|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|ドキュメントにアタッチする場合は、最初のビューを更新します。|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|OLE 項目からネイティブのデータを取得します。|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|指定されたデバイスに印刷特性を設定します。|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|指定された文字列のすべての出現箇所を新しい文字列に置き換えます。|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|現在の選択範囲を置き換えます。|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|要求されたテキストが見つかりませんでした。 ユーザーの通知を処理します。|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|上のデータについて表示するクエリ、`IDataObject`します。|  
|[CRichEditView::WrapChanged](#wrapchanged)|ターゲットの出力デバイスを調整します。 この豊富な編集の値に基づいて、表示の`m_nWordWrap`します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|箇条書きリストのインデントの量を示します。|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|ワード ラップの制約を示します。|  
  
## <a name="remarks"></a>Remarks  
 「リッチ エディット コントロール」をユーザーは入力し、テキストの編集ウィンドウです。 テキストは、文字および段落の書式設定に割り当てることができるし、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストの書式設定のプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーに使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` テキストとテキストの書式設定特性を保持します。 `CRichEditDoc` ビューでは OLE クライアント アイテムの一覧を保持します。 `CRichEditCntrItem` コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (つまり、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は以降 Windows 95/98 および Windows NT 3.51 の下で実行中のプログラムにのみ使用できます。  
  
 MFC アプリケーションでリッチ エディット ビューの使用の例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーション。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrich.h  
  
##  <a name="adjustdialogposition"></a>  CRichEditView::AdjustDialogPosition  
 現在の選択範囲が見えにくくならないように、指定されたダイアログ ボックスを移動するには、この関数を呼び出します。  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDlg*  
 ポインターを`CDialog`オブジェクト。  
  
##  <a name="canpaste"></a>  CRichEditView::CanPaste  
 リッチ エディット ビューに貼り付けることができる情報がクリップボードに含まれるかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リッチ エディット ビューを受け入れることができます。 この形式でデータがクリップボードに含まれている場合、0 以外の場合それ以外の場合、0 を返します。  
  
##  <a name="cricheditview"></a>  CRichEditView::CRichEditView  
 作成するには、この関数を呼び出し、`CRichEditView`オブジェクト。  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>  CRichEditView::DoPaste  
 OLE 項目を貼り付けるには、この関数を呼び出す*dataobj*リッチ ドキュメント/ビューの編集にします。  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>パラメーター  
 *dataobj*  
 [COleDataObject](../../mfc/reference/coledataobject-class.md)を貼り付けるデータを格納しています。  
  
 *cf*  
 目的のクリップボード形式。  
  
 *hMetaPict*  
 貼り付ける項目を表すメタファイル。  
  
### <a name="remarks"></a>Remarks  
 フレームワークの既定の実装の一部としてこの関数を呼び出す[QueryAcceptData](#queryacceptdata)します。  
  
 この関数は、貼り付け のハンドラーの結果に基づいて貼り付けの種類を決定します。 場合*cf*が 0 の場合、新しい項目が、現在の象徴的な表現を使用します。 場合*cf*が 0 以外と*hMetaPict*が NULL でない、新しい項目を使用して*hMetaPict*の表現。  
  
##  <a name="findtext"></a>  CRichEditView::FindText  
 指定したテキストを検索し、現在の選択範囲に設定するには、この関数を呼び出します。  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 検索する文字列が含まれています。  
  
 *置き換えた*  
 検索が大文字小文字が区別されますを示します。  
  
 *bWord*  
 検索する単語のみ、単語の一部ではないかどうかを示します。  
  
 *bNext*  
 検索の方向を示します。 TRUE の場合、検索の方向は、バッファーの末尾方向です。 FALSE の場合、検索の方向は、バッファーの先頭方向です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、*されて*テキストが見つかった場合は 0。  
  
### <a name="remarks"></a>Remarks  
 この関数は、検索操作中に待機カーソルを表示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple  
 指定したテキストを検索し、現在の選択範囲に設定するには、この関数を呼び出します。  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 検索する文字列が含まれています。  
  
 *置き換えた*  
 検索が大文字小文字が区別されますを示します。  
  
 *bWord*  
 検索する単語のみ、単語の一部ではないかどうかを示します。  
  
 *bNext*  
 検索の方向を示します。 TRUE の場合、検索の方向は、バッファーの末尾方向です。 FALSE の場合、検索の方向は、バッファーの先頭方向です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、*されて*テキストが見つかった場合は 0。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection  
 この関数では、現在の選択の属性を書式設定文字を取得します。  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>戻り値  
 A [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)を現在の選択の属性を書式設定文字を含む構造体。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、 [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026)メッセージと[CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Windows SDK の構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData  
 フレームワークの処理の一環としてこの関数を呼び出す[IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315)します。  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpchrg*  
 ポインター、[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)構造体で指定されたデータ オブジェクトにコピーする文字 (と OLE アイテム) の範囲を指定する*と*します。  
  
 *dwReco*  
 クリップボードの操作フラグです。 これらの値のいずれかを指定できます。  
  
- RECO_COPY クリップボードにコピーします。  
  
- RECO_CUT をクリップボードに切り取ります。  
  
- RECO_DRAG ドラッグ操作 (ドラッグ アンド ドロップ) です。  
  
- RECO_DROP Drop 操作 (ドラッグ アンド ドロップ) です。  
  
- クリップボードから貼り付けを RECO_PASTE します。  
  
 *lpRichDataObj*  
 ポインター、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)豊富なからクリップボードのデータを格納しているオブジェクトの編集コントロール ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341))。  
  
 *と*  
 アドレスを受け取るポインター変数へのポインター、`IDataObject`オブジェクトで指定された範囲を表す、 *lpchrg*パラメーター。 値*と*エラーが返される場合は無視されます。  
  
### <a name="return-value"></a>戻り値  
 操作の成功を報告する HRESULT 値。 HRESULT の詳細については、次を参照してください。 [COM エラー コードの構造](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK に含まれています。  
  
### <a name="remarks"></a>Remarks  
 戻り値が成功すると、示された場合`IRichEditOleCallback::GetClipboardData`を返します、`IDataObject`によってアクセス*と*。 それ以外がアクセスする 1 つを返します*lpRichDataObj*します。 クリップボードのデータを提供するには、この関数をオーバーライドします。 この関数の既定の実装では、E_NOTIMPL を返します。  
  
 これは、高度なオーバーライド可能な。  
  
 詳細については、次を参照してください[IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)、 [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315)、および[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)Windows SDK と参照[。IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Windows SDK にします。  
  
##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu  
 フレームワークの処理の一環としてこの関数を呼び出す[IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317)します。  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>パラメーター  
 *seltyp*  
 選択の種類。 選択型の値は、「解説」で説明します。  
  
 *持っていないとき*  
 ポインター、`OLEOBJECT`選択範囲には、1 つまたは複数の OLE 項目が含まれている場合は、最初に選択した OLE オブジェクトを指定する構造体。 選択範囲に、項目が含まれていない場合*持っていないとき*は NULL です。 `OLEOBJECT` OLE オブジェクト v テーブルへのポインターを保持する構造体。  
  
 *lpchrg*  
 ポインターを[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)現在の選択範囲を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 コンテキスト メニューへのハンドルします。  
  
### <a name="remarks"></a>Remarks  
 この関数は、処理速度の右マウス ボタンの標準的な部分です。  
  
 選択の種類には、次のフラグの任意の組み合わせを指定できます。  
  
- SEL_EMPTY では、現在選択されていないことを示します。  
  
- SEL_TEXT では、現在の選択範囲にテキストが含まれていることを示します。  
  
- SEL_OBJECT では、現在の選択範囲が少なくとも 1 つの OLE 項目が含まれていることを示します。  
  
- SEL_MULTICHAR では、現在の選択範囲にテキストの 1 つ以上の文字が含まれていることを示します。  
  
- SEL_MULTIOBJECT では、現在の選択範囲には、複数の OLE オブジェクトが含まれていることを示します。  
  
 既定の実装では、NULL を返します。 これは、高度なオーバーライド可能な。  
  
 詳細については、次を参照してください。 [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317)と[上](http://msdn.microsoft.com/library/windows/desktop/bb787885)Windows SDK に含まれています。  
  
 詳細については、 `OLEOBJECT` OLE データ構造体と構造体の割り当ての記事を参照して、入力、 *OLE サポート技術情報*します。  
  
##  <a name="getdocument"></a>  CRichEditView::GetDocument  
 ポインターを取得するには、この関数を呼び出して、`CRichEditDoc`このビューに関連付けられています。  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)オブジェクトに関連付けられている、`CRichEditView`オブジェクト。  
  
##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem  
 項目の OLE を取得するには、この関数の呼び出しがこの場所で現在アクティブ化`CRichEditView`オブジェクト。  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 1 つ、インプレース アクティブへのポインター [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) ; リッチ エディット ビュー内のオブジェクト項目がない OLE 現在インプレース アクティブ状態の場合は NULL します。  
  
##  <a name="getmargins"></a>  CRichEditView::GetMargins  
 印刷に使用される現在の余白を取得するには、この関数を呼び出します。  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷で使用される余白は MM_TWIPS で測定されます。  
  
##  <a name="getpagerect"></a>  CRichEditView::GetPageRect  
 印刷に使用されるページの寸法を取得するには、この関数を呼び出します。  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷で使用されるページの境界は、MM_TWIPS で測定されます。  
  
### <a name="remarks"></a>Remarks  
 この値は、用紙サイズに基づきます。  
  
##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize  
 現在の用紙サイズを取得するには、この関数を呼び出します。  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷で使用する用紙のサイズは、MM_TWIPS で測定されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection  
 段落の現在の選択の属性を取得するには、この関数を呼び出します。  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>戻り値  
 A [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)段落の現在の選択の属性を格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182)メッセージと[PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Windows SDK の構造体。  
  
##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect  
 ページの四角形内で印刷領域の境界を取得するには、この関数を呼び出します。  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷で使用されるイメージの領域の境界は、MM_TWIPS で測定されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth  
 印刷領域の幅を決定するには、この関数を呼び出します。  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 MM_TWIPS で印刷領域の幅が測定されます。  
  
##  <a name="getricheditctrl"></a>  CRichEditView::GetRichEditCtrl  
 取得するには、この関数を呼び出し、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)オブジェクトに関連付けられている、`CRichEditView`オブジェクト。  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CRichEditCtrl`このビューのオブジェクト。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem  
 OLE 項目を取得するには、この関数を呼び出す (、`CRichEditCntrItem`オブジェクト) で現在選択されている`CRichEditView`オブジェクト。  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)で選択したオブジェクト、`CRichEditView`オブジェクト。このビューで項目が選択されていない場合は NULL です。  
  
##  <a name="gettextlength"></a>  CRichEditView::GetTextLength  
 このテキストの長さを取得するには、この関数を呼び出す`CRichEditView`オブジェクト。  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このテキストの長さ`CRichEditView`オブジェクト。  
  
##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx  
 このテキストの長さを計算するには、このメンバー関数を呼び出す`CRichEditView`オブジェクト。  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 テキストの長さを決定する際に使用するメソッドを指定する値。 このメンバーは、いずれかを指定できますまたは以上の値のフラグのメンバーに表示されている[GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) Windows SDK で説明します。  
  
 *uCodePage*  
 変換 (Unicode の 1200 の ANSI コード ページの CP_ACP) のコード ページです。  
  
### <a name="return-value"></a>戻り値  
 文字または、編集コントロール内のバイト数。 互換性のないフラグが設定されている場合*dwFlags*、このメンバー関数は、E_INVALIDARG を返します。  
  
### <a name="remarks"></a>Remarks  
 `GetTextLengthEx` テキストの長さを決定するその他の方法を提供します。 リッチ エディット 2.0 の機能をサポートします。 詳細については、次を参照してください。[リッチのエディット コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb787873)Windows SDK に含まれています。  
  
##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject  
 指定したファイルを挿入するには、この関数を呼び出す (として、 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)オブジェクト) に豊富なビューを編集します。  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 *場合*  
 挿入するファイルの名前を表す文字列です。  
  
##  <a name="insertitem"></a>  CRichEditView::InsertItem  
 挿入するには、この関数を呼び出し、 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)リッチ エディット ビューへのオブジェクト。  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pItem*  
 挿入する項目へのポインター。  
  
### <a name="return-value"></a>戻り値  
 挿入の成功を示す HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 HRESULT の詳細については、次を参照してください。 [COM エラー コードの構造](http://msdn.microsoft.com/library/windows/desktop/ms690088)Windows SDK に含まれています。  
  
##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat  
 場合を判断するには、この関数を呼び出す*cf*はテキスト、リッチ テキスト、または OLE 項目を含むリッチ テキストはクリップボード形式です。  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>パラメーター  
 *cf*  
 目的のクリップボード形式。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値*cf*はリッチ テキストの編集またはクリップボードの形式です。  
  
##  <a name="isselected"></a>  CRichEditView::IsSelected  
 指定した OLE 項目がこのビューで現在選択されているかどうかを判断するには、この関数を呼び出します。  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pDocItem*  
 ビュー内のオブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが選択されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 派生ビュー クラスの OLE 項目の選択を処理するための別の方法がある場合は、この関数をオーバーライドします。  
  
##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent  
 リスト内の項目のインデント既定では、720 単位、1/2 インチであります。  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap  
 リッチ エディット ビューのワード ラップの種類を示します。  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>Remarks  
 次のいずれかの値です。  
  
- `WrapNone` 自動のワード ラップがないことを示します。  
  
- `WrapToWindow` ウィンドウの幅に基づいてテキストの折り返しを示します。  
  
- `WrapToTargetDevice` ターゲット デバイスの特性に基づき、ワード ラップを示します。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::WrapChanged](#wrapchanged)します。  
  
##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect  
 文字書式の現在の選択の効果を切り替えるには、この関数を呼び出します。  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwMask*  
 現在の選択範囲を変更する効果を書式設定文字です。  
  
 *dwEffect*  
 文字書式の効果を切り替えるの目的のリスト。  
  
### <a name="remarks"></a>Remarks  
 この関数に対する各呼び出しは、現在の選択範囲の指定した書式設定の効果を切り替えます。  
  
 詳細については、 *dwMask*と*dwEffect*パラメーターと、その潜在的な値の対応するデータ メンバーを参照してください。 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>  CRichEditView::OnFindNext  
 検索と置換 ダイアログ ボックスからコマンドを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 検索する文字列。  
  
 *bNext*  
 検索する方向: true に設定します。False の場合、アップします。  
  
 *置き換えた*  
 検索の大文字小文字を区別するかどうかを示します。  
  
 *bWord*  
 検索の完全一致する単語のみかどうかどうかを示します。  
  
### <a name="remarks"></a>Remarks  
 内のテキストを検索するには、この関数を呼び出して、`CRichEditView`します。 派生ビュー クラスの検索の特性を変更するには、この関数をオーバーライドします。  
  
##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate  
 ビューが最初に、ドキュメントに接続されているが、ビューが最初に表示される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装、 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)ヒント情報なしでメンバー関数 (つまり、0 の既定値を使用して、 *lHint*パラメーターと、の場合はNULL*pHint*パラメーター)。 ドキュメントに関する情報を必要とする任意の one-time initialization を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションは、固定サイズのドキュメントに、ドキュメントのサイズに基づくビューのスクロール範囲を初期化するためにこの関数を使用できます。 アプリケーションでは、可変サイズのドキュメントをサポートする場合は、使用`OnUpdate`スクロールを更新する時間を制限すべてドキュメントの変更。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::m_nWordWrap](#m_nwordwrap)します。  
  
##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject  
 埋め込みアイテムからネイティブのデータを読み込むには、この関数を使用します。  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpStg*  
 ポインター、 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外の場合それ以外の場合、0 です。  
  
### <a name="remarks"></a>Remarks  
 通常、このタスクは実行を作成して、 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)の周囲、`IStorage`します。 `COleStreamFile`アーカイブに接続できると[cobject::serialize](../../mfc/reference/cobject-class.md#serialize)データを読み込むために呼び出されます。  
  
 これは、高度なオーバーライド可能な。  
  
 詳細については、次を参照してください。 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Windows SDK に含まれています。  
  
##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign  
 選択した段落の段落の配置を変更するには、この関数を呼び出します。  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 *wAlign*  
 段落の配置が必要です。 次のいずれかの値です。  
  
- PFA_LEFT では、左の余白を使用して段落を揃えます。  
  
- PFA_RIGHT では、右の余白を使用して段落を整列します。  
  
- PFA_CENTER センターの間の余白の段落です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged  
 プリンターが変更されたときに、リッチ エディット ビューの特性を変更するには、この関数をオーバーライドします。  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>パラメーター  
 *dcPrinter*  
 A [CDC](../../mfc/reference/cdc-class.md)新しいプリンターのオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、物理的な高さと幅出力デバイス (プリンター) に、用紙サイズを設定します。 存在する場合のデバイス コンテキストに関連付けられた*dcPrinter*既定の実装では、用紙サイズを 8.5 で 11 インチに設定します。  
  
##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll  
 置換 ダイアログ ボックスから すべて置換のコマンドの処理中に、フレームワークによって呼び出されます。  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 置換するテキスト。  
  
 *見つかる*  
 置換テキスト。  
  
 *置き換えた*  
 検索が大文字小文字が区別されますを示します。  
  
 *bWord*  
 検索に単語全体を選択する必要がありますかかどうかを示します。  
  
### <a name="remarks"></a>Remarks  
 この関数では、別の文字列で指定された文字列のすべての出現箇所を置き換えます。 このビューの検索の特性を変更するには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel  
 [置換] ダイアログ ボックス [置換] コマンドを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 置換するテキスト。  
  
 *bNext*  
 検索の方向を示します TRUE は、ダウンすると、。False の場合、アップします。  
  
 *置き換えた*  
 検索が大文字小文字が区別されますを示します。  
  
 *bWord*  
 検索に単語全体を選択する必要がありますかかどうかを示します。  
  
 *見つかる*  
 置換テキスト。  
  
### <a name="remarks"></a>Remarks  
 この関数では、別の文字列で指定された文字列が 1 つを置き換えます。 このビューの検索の特性を変更するには、この関数をオーバーライドします。  
  
##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound  
 検索が失敗したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 テキストは見つかりませんでした。  
  
### <a name="remarks"></a>Remarks  
 出力の通知を変更するには、この関数をオーバーライドする[MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356)します。  
  
 詳細については、次を参照してください。 [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect  
 フレームワークは、文字効果コマンドのコマンドの UI を更新するには、この関数を呼び出します。  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 *対応付けられました。*  
 ポインターを[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクト。  
  
 *dwMask*  
 マスクの書式設定文字を示します。  
  
 *dwEffect*  
 文字書式の効果を示します。  
  
### <a name="remarks"></a>Remarks  
 マスク*dwMask*文字確認を書式設定属性を指定します。 フラグ*dwEffect*文字書式セット/消去に属性を一覧表示します。  
  
 詳細については、 *dwMask*と*dwEffect*パラメーターと、その潜在的な値の対応するデータ メンバーを参照してください。 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign  
 フレームワークは、段落の効果のコマンドのコマンド UI を更新するには、この関数を呼び出します。  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 *対応付けられました。*  
 ポインターを[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクト。  
  
 *wAlign*  
 段落の配置を確認します。 次のいずれかの値です。  
  
- PFA_LEFT では、左の余白を使用して段落を揃えます。  
  
- PFA_RIGHT では、右の余白を使用して段落を整列します。  
  
- PFA_CENTER センターの間の余白の段落です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect  
 範囲内に収まるリッチ エディット コントロール内のテキストの書式設定するには、この関数を呼び出す*rectLayout*で指定されたデバイスの*pDC*します。  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 出力領域のデバイス コンテキストへのポインター。  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md)または[CRect](../../atl-mfc-shared/reference/crect-class.md)出力領域を定義します。  
  
 *nIndexStart*  
 書式設定する最初の文字の 0 から始まるインデックス。  
  
 *nIndexStop*  
 書式設定する最後の文字の 0 から始まるインデックス。  
  
 *bOutput*  
 テキストを表示するかどうかを示します。 FALSE の場合は、テキストはだけ測定されます。  
  
### <a name="return-value"></a>戻り値  
 出力領域と 1 つに適合する最後の文字のインデックス。  
  
### <a name="remarks"></a>Remarks  
 この呼び出しへの呼び出し後に通常、 [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband)出力を生成します。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::GetPaperSize](#getpapersize)します。  
  
##  <a name="printpage"></a>  CRichEditView::PrintPage  
 指定された出力デバイス用のリッチ エディット コントロールのテキストの範囲の書式設定するには、この関数を呼び出す*pDC*します。  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 ページ出力のデバイス コンテキストへのポインター。  
  
 *nIndexStart*  
 書式設定する最初の文字の 0 から始まるインデックス。  
  
 *nIndexStop*  
 書式設定する最後の文字の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 ページと 1 つに適合する最後の文字のインデックス。  
  
### <a name="remarks"></a>Remarks  
 によって制御される各ページのレイアウト[GetPageRect](#getpagerect)と[GetPrintRect](#getprintrect)します。 この呼び出しへの呼び出し後に通常、 [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband)出力を生成します。  
  
 余白は論理ページではなく、物理ページの基準としたことに注意してください。 そのため、多くのプリンターがあるページの一部に印刷できないために、0 の余白は、テキストをクリップ多くの場合。 呼び出す必要があります、テキストをクリッピングを避けるため、 [SetMargins](#setmargins)印刷する前に適切な余白を設定するとします。  
  
##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData  
 リッチ エディットにオブジェクトを貼り付けるために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,  
    CLIPFORMAT* lpcfFormat,  
    DWORD dwReco,  
    BOOL bReally,  
    HGLOBAL hMetaFile);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpdataobj*  
 ポインター、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)をクエリします。  
  
 *lpcfFormat*  
 許容可能なデータ形式へのポインター。  
  
 *dwReco*  
 使用しません。  
  
 *bReally*  
 貼り付け操作を続けるかかどうかを示します。  
  
 *hMetaFile*  
 項目のアイコンを描画するために使われるメタファイルのハンドル。  
  
### <a name="return-value"></a>戻り値  
 操作の成功を報告する HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 COM のアイテム、ドキュメントの派生クラスでの別の組織を処理するには、この関数をオーバーライドします。 これは、高度なオーバーライド可能な。  
  
 HRESULT の詳細については、`IDataObject`を参照してください[COM エラー コードの構造](http://msdn.microsoft.com/library/windows/desktop/ms690088)と[IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)、それぞれ、Windows SDK で。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat  
 これで新しいテキストの属性を書式設定文字を設定するには、この関数を呼び出す`CRichEditView`オブジェクト。  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>パラメーター  
 *cf*  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883)新しい既定の文字書式属性を含む構造体。  
  
### <a name="remarks"></a>Remarks  
 指定された属性のみ、`dwMask`のメンバー *cf*は、この関数によって変更します。  
  
 詳細については、次を参照してください。 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230)メッセージと[CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Windows SDK の構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>  CRichEditView::SetMargins  
 リッチ エディット ビューの印刷余白を設定するには、この関数を呼び出します。  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectMargin*  
 印刷の場合、新しい余白の値は、MM_TWIPS で測定されます。  
  
### <a name="remarks"></a>Remarks  
 場合[m_nWordWrap](#m_nwordwrap)は`WrapToTargetDevice`、呼び出す必要があります[WrapChanged](#wrapchanged)この関数を使用して印刷特性を調整した後。  
  
 余白がによって使用される[PrintPage](#printpage)は論理ページではなく、物理ページを基準とします。 そのため、多くのプリンターがあるページの一部に印刷できないために、0 の余白は、テキストをクリップ多くの場合。 テキストを回避するには、使用を呼び出す必要があります`SetMargins`印刷する前に適切なプリンターの余白を設定します。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::GetPaperSize](#getpapersize)します。  
  
##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize  
 リッチ エディット ビューを印刷する用紙サイズを設定するには、この関数を呼び出します。  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizePaper*  
 MM_TWIPS で印刷の場合、新しい用紙サイズ値が測定されます。  
  
### <a name="remarks"></a>Remarks  
 場合[m_nWordWrap](#m_nwordwrap)は`WrapToTargetDevice`、呼び出す必要があります[WrapChanged](#wrapchanged)この関数を使用して印刷特性を調整した後。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat  
 段落の現在の選択の属性を設定するには、この関数を呼び出す`CRichEditView`オブジェクト。  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>パラメーター  
 *pf*  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942)新しい既定の段落書式属性。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 指定された属性のみ、`dwMask`のメンバー *pf*は、この関数によって変更します。  
  
 詳細については、次を参照してください。 [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276)メッセージと[PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Windows SDK の構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>  CRichEditView::TextNotFound  
 検索の内部状態をリセットするには、この関数を呼び出し、 [CRichEditView](../../mfc/reference/cricheditview-class.md)に失敗した呼び出しの後にコントロール[FindText](#findtext)します。  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>パラメーター  
 *中から*  
 見つからなかったテキスト文字列が含まれています。  
  
### <a name="remarks"></a>Remarks  
 失敗した呼び出しの直後にこのメソッドを呼び出すことをお勧め[FindText](#findtext)コントロールの検索の内部状態が正しくリセットされるようにします。  
  
 *されて*パラメーターに指定された文字列と同じコンテンツを含める必要があります[FindText](#findtext)します。 このメソッドを呼び出す内部検索の状態をリセットした後、[見つからなかったとき](#ontextnotfound)メソッドに指定された検索文字列。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::FindText](#findtext)します。  
  
##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged  
 印刷の特性が変化したときに、この関数を呼び出す ( [SetMargins](#setmargins)または[SetPaperSize](#setpapersize))。  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>Remarks  
 豊富なビューを編集する方法を変更するには、この関数の応答の変更に上書き[m_nWordWrap](#m_nwordwrap)または印刷の特性 ( [OnPrinterChanged](#onprinterchanged))。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)
