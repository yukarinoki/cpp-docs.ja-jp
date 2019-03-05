---
title: CVSListBox クラス
ms.date: 11/19/2018
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
ms.openlocfilehash: 618f4f386db477dd301ada862ebd2094a6c6651f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301520"
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
|[CVSListBox::GetItemData](#getitemdata)|編集可能なリスト コントロール項目に関連付けられているアプリケーションに固有の 32 ビット値を取得します。 (`CVSListBoxBase::GetItemData` をオーバーライドします)。|
|[CVSListBox::GetItemText](#getitemtext)|編集可能なリスト コントロール項目のテキストを取得します。 (`CVSListBoxBase::GetItemText` をオーバーライドします)。|
|[CVSListBox::GetSelItem](#getselitem)|編集可能なリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します。 (`CVSListBoxBase::GetSelItem` をオーバーライドします)。|
|`CVSListBox::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 詳細とメソッド構文は、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。 (`CVSListBoxBase::PreTranslateMessage` をオーバーライドします)。|
|[CVSListBox::RemoveItem](#removeitem)|編集可能なリスト コントロールから項目を削除します。 (`CVSListBoxBase::RemoveItem` をオーバーライドします)。|
|[CVSListBox::SelectItem](#selectitem)|編集可能なリスト文字列を選択します。 (`CVSListBoxBase::SelectItem` をオーバーライドします)。|
|[CVSListBox::SetItemData](#setitemdata)|アプリケーション固有の 32 ビット値を編集可能なリスト コントロール項目に関連付けます。 (`CVSListBoxBase::SetItemData` をオーバーライドします)。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|現在の埋め込みリスト ビュー コントロールにハンドルを返します。|

## <a name="remarks"></a>Remarks

`CVSListBox`クラスは、ユーザーを作成、変更、削除、またはリスト コントロール項目を再配置を有効にする編集ボタンのセットを提供します。

編集可能なリスト コントロールの図を次に示します。 2 番目の一覧のエントリは、"Item2"のタイトルは編集用に選択します。

![CVSListBox コントロール](../../mfc/reference/media/cvslistbox.png "CVSListBox コントロール")

リソース エディターを使用して、編集可能なリスト コントロールを追加する場合、**ツールボックス**エディターのペインが編集可能な定義済みのリスト コントロールを提供しません。 代わりなどの静的コントロールを追加、**グループ ボックス**コントロール。 フレームワークは、編集可能なリスト コントロールの位置とサイズを指定するのにプレース ホルダーとして静的コントロールを使用します。

ダイアログ ボックスのテンプレートで、編集可能なリスト コントロールを使用するには、宣言、`CVSListBox`ダイアログ ボックス クラスの変数。 変数とコントロール間のデータ交換をサポートするために定義、`DDX_Control`マクロのエントリ、 `DoDataExchange`  ダイアログ ボックスのメソッド。 既定では、編集ボタンなし、編集可能なリスト コントロールが作成されます。 編集ボタンを有効にするのにには、継承された CVSListBoxBase::SetStandardButtons メソッドを使用します。

詳細については、サンプルのディレクトリを参照してください、 `New Controls` Page3.cpp と Page3.h ファイルのサンプルです。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>必要条件

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

*strIext*<br/>
[in]文字列への参照。

*dwData*<br/>
[in]文字列に関連付けられているアプリケーション固有の 32 ビット値。 既定値は 0 です。

*iIndex*<br/>
[in]文字列を保持する位置の 0 から始まるインデックス。 場合、 *iIndex*パラメーターが-1 の場合、文字列はリストの末尾に追加されます。 既定値は -1 です。

### <a name="return-value"></a>戻り値

文字列のリスト コントロール内の位置の 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

使用して、 [CVSListBox::GetItemData](#getitemdata)で指定された値を取得するメソッド、*指定*パラメーター。 この値は、アプリケーション固有の整数またはその他のデータへのポインターを指定できます。

##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox

`CVSListBox` オブジェクトを構築します。

```
CVSListBox();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="edititem"></a>  CVSListBox::EditItem

リスト コントロール項目のテキストの編集操作を開始します。

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]リスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

編集操作が正常に開始する場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

項目のラベルをダブルクリックするか、キーを押して、ユーザーが編集操作を開始、 **F2**または**space キーを押す**キーの項目にフォーカスがあります。

##  <a name="getcount"></a>  CVSListBox::GetCount

編集可能なリスト コントロール内の文字列の数を取得します。

```
virtual int GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト コントロールの項目の数。

### <a name="remarks"></a>Remarks

カウントのいずれかの最後の項目のインデックス値より大きいインデックスが 0 から始まるので注意してください。

##  <a name="getitemdata"></a>  CVSListBox::GetItemData

編集可能なリスト コントロール項目に関連付けられているアプリケーションに固有の 32 ビット値を取得します。

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定した項目に関連付けられている 32 ビット値。

### <a name="remarks"></a>Remarks

使用して、 [CVSListBox::SetItemData](#setitemdata)または[CVSListBox::AddItem](#additem)に 32 ビット値をリスト コントロール項目に関連付けるメソッド。 この値は、アプリケーション固有の整数またはその他のデータへのポインターを指定できます。

##  <a name="getitemtext"></a>  CVSListBox::GetItemText

編集可能なリスト コントロール項目のテキストを取得します。

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

A [CString](../../atl-mfc-shared/reference/cstringt-class.md)指定した項目のテキストを含むオブジェクト。

### <a name="remarks"></a>Remarks

##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd

現在の埋め込みリスト ビュー コントロールにハンドルを返します。

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>戻り値

埋め込みリスト ビュー コントロールへのハンドル。

### <a name="remarks"></a>Remarks

サポートする組み込みのリスト ビュー コントロールを識別するハンドルを取得するには、このメソッドを使用して、`CVSListBox`クラス。

##  <a name="getselitem"></a>  CVSListBox::GetSelItem

編集可能なリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します。

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合、現在選択されている項目の 0 から始まるインデックスそれ以外の場合、-1 を返します。

### <a name="remarks"></a>Remarks

##  <a name="removeitem"></a>  CVSListBox::RemoveItem

編集可能なリスト コントロールから項目を削除します。

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定した項目が削除された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="selectitem"></a>  CVSListBox::SelectItem

編集可能なリスト文字列を選択します。

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>パラメーター

*iItem*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、指定された項目を選択し、必要な場合は、ビューに項目をスクロールします。

##  <a name="setitemdata"></a>  CVSListBox::SetItemData

アプリケーション固有の 32 ビット値を編集可能なリスト コントロール項目に関連付けます。

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

*dwData*<br/>
[in]32 ビット値。 この値は、アプリケーション固有の整数またはその他のデータへのポインターを指定できます。

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
