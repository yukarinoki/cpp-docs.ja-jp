---
title: CVSListBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
dev_langs:
- C++
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 380b470531fd28d8cfe68aa931105430111c3dbf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cvslistbox-class"></a>CVSListBox クラス
`CVSListBox`クラスが編集可能なリスト コントロールをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|`CVSListBox` オブジェクトを構築します。|  
|`CVSListBox::~CVSListBox`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|リスト コントロールに文字列を追加します。 (`CVSListBoxBase::AddItem` をオーバーライドします)。|  
|[CVSListBox::EditItem](#edititem)|リスト コントロール項目のテキストの編集操作を開始します。 (`CVSListBoxBase::EditItem` をオーバーライドします)。|  
|[CVSListBox::GetCount](#getcount)|編集可能なリスト コントロール内の文字列の数を取得します。 (`CVSListBoxBase::GetCount` をオーバーライドします)。|  
|[CVSListBox::GetItemData](#getitemdata)|編集可能なリスト コントロール項目に関連付けられているアプリケーション固有の 32 ビット値を取得します。 (`CVSListBoxBase::GetItemData` をオーバーライドします)。|  
|[CVSListBox::GetItemText](#getitemtext)|編集可能なリスト コントロール項目のテキストを取得します。 (`CVSListBoxBase::GetItemText` をオーバーライドします)。|  
|[CVSListBox::GetSelItem](#getselitem)|編集可能なリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します。 (`CVSListBoxBase::GetSelItem` をオーバーライドします)。|  
|`CVSListBox::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。 詳細とメソッドの構文は、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)です。 (`CVSListBoxBase::PreTranslateMessage` をオーバーライドします)。|  
|[CVSListBox::RemoveItem](#removeitem)|編集可能なリスト コントロールから項目を削除します。 (`CVSListBoxBase::RemoveItem` をオーバーライドします)。|  
|[CVSListBox::SelectItem](#selectitem)|編集可能なリスト コントロール文字列を選択します。 (`CVSListBoxBase::SelectItem` をオーバーライドします)。|  
|[CVSListBox::SetItemData](#setitemdata)|アプリケーション固有の 32 ビット値を編集可能なリスト コントロール項目に関連付けます。 (`CVSListBoxBase::SetItemData` をオーバーライドします)。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|現在の埋め込みリスト ビュー コントロールにハンドルを返します。|  
  
## <a name="remarks"></a>コメント  
 `CVSListBox`クラスを作成、変更、削除、またはリスト コントロール項目を再配置するユーザーを有効にする編集ボタンのセットを提供します。  
  
 編集可能なリスト コントロールの画像を次に示します。 2 番目の一覧のエントリは、"Item2"のタイトルは、編集が選択されます。  
  
 ![CVSListBox コントロール](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 場合は、リソース エディターを使用して、編集可能なリスト コントロールを追加することに注意して、**ツールボックス**エディターのペインが編集可能な定義済みのリスト コントロールを提供していません。 代わりなどが静的なコントロールを追加、**グループ ボックス**コントロール。 フレームワークでは、プレース ホルダーとして、静的なコントロールを使用して、編集可能なリスト コントロールの位置とサイズを指定します。  
  
 編集可能なリスト コントロールをダイアログ ボックスのテンプレートを使用するのには、宣言、 `CVSListBox`  ダイアログ ボックス クラスの変数です。 サポートするには、変数、およびコントロール間のデータ交換を定義する、`DDX_Control`マクロ エントリ、 `DoDataExchange`  ダイアログ ボックスのメソッドです。 既定では、編集可能なリスト コントロールが編集 ボタンがない作成されます。 編集用のボタンを有効にするのにには、継承された CVSListBoxBase::SetStandardButtons メソッドを使用します。  
  
 詳細については、Samples ディレクトリを参照してください、 `New Controls` Page3.cpp と Page3.h ファイルのサンプルです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxvslistbox.h  
  
##  <a name="additem"></a>  CVSListBox::AddItem  
 リスト コントロールに文字列を追加します。  
  
```  
virtual int AddItem(
    const CString& strIext,  
    DWORD_PTR dwData=0,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strIext`  
 文字列への参照。  
  
 [入力] `dwData`  
 文字列に関連付けられているアプリケーション固有の 32 ビット値。 既定値は 0 です。  
  
 [入力] `iIndex`  
 文字列を保持する位置の 0 から始まるインデックス。 場合、`iIndex`文字列はパラメーターが-1 の場合、リストの末尾に追加されます。 既定値は -1 です。  
  
### <a name="return-value"></a>戻り値  
 文字列のリスト コントロール内の位置の 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CVSListBox::GetItemData](#getitemdata)で指定された値を取得するメソッド、`dwData`パラメーター。 この値は、アプリケーション固有の整数またはその他のデータへのポインターにすることができます。  
  
##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox  
 `CVSListBox` オブジェクトを構築します。  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="edititem"></a>  CVSListBox::EditItem  
 リスト コントロール項目のテキストの編集操作を開始します。  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 リスト コントロール項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 編集操作が正常に開始する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 項目のラベルをダブルクリックするか、キーを押して、ユーザーが編集操作を開始、 **F2**または**space キー**キーの項目にフォーカスがあるとします。  
  
##  <a name="getcount"></a>  CVSListBox::GetCount  
 編集可能なリスト コントロール内の文字列の数を取得します。  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト コントロールの項目の数。  
  
### <a name="remarks"></a>コメント  
 数が 1 つの最後の項目のインデックス値より大きいインデックスが 0 から始まるため、注意してください。  
  
##  <a name="getitemdata"></a>  CVSListBox::GetItemData  
 編集可能なリスト コントロール項目に関連付けられているアプリケーション固有の 32 ビット値を取得します。  
  
```  
virtual DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 編集可能なリスト コントロール項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定した項目に関連付けられている 32 ビット値。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CVSListBox::SetItemData](#setitemdata)または[CVSListBox::AddItem](#additem)に 32 ビット値をリスト コントロール項目に関連付けるメソッド。 この値は、アプリケーション固有の整数またはその他のデータへのポインターにすることができます。  
  
##  <a name="getitemtext"></a>  CVSListBox::GetItemText  
 編集可能なリスト コントロール項目のテキストを取得します。  
  
```  
virtual CString GetItemText(int iIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 編集可能なリスト コントロール項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)指定した項目のテキストを含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd  
 現在の埋め込みリスト ビュー コントロールにハンドルを返します。  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 埋め込みリスト ビュー コントロールへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、サポートする埋め込みリスト ビュー コントロールへのハンドルを取得、`CVSListBox`クラスです。  
  
##  <a name="getselitem"></a>  CVSListBox::GetSelItem  
 編集可能なリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します。  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合、現在選択されている項目の 0 から始まるインデックスそれ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removeitem"></a>  CVSListBox::RemoveItem  
 編集可能なリスト コントロールから項目を削除します。  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 編集可能なリスト コントロール項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 指定した項目が削除された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="selectitem"></a>  CVSListBox::SelectItem  
 編集可能なリスト コントロール文字列を選択します。  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iItem`  
 編集可能なリスト コントロール項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、指定した項目を選択し、必要な場合は、ビューに、項目をスクロールします。  
  
##  <a name="setitemdata"></a>  CVSListBox::SetItemData  
 アプリケーション固有の 32 ビット値を編集可能なリスト コントロール項目に関連付けます。  
  
```  
virtual void SetItemData(
    int iIndex,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 編集可能なリスト コントロール項目の 0 から始まるインデックス。  
  
 [入力] `dwData`  
 32 ビット値です。 この値は、アプリケーション固有の整数またはその他のデータへのポインターにすることができます。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
