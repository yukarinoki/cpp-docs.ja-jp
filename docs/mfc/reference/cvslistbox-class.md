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
ms.openlocfilehash: 4ea48a263a01133419067979ee5fa3e62105c7f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373186"
---
# <a name="cvslistbox-class"></a>CVSListBox クラス

この`CVSListBox`クラスは、編集可能なリスト コントロールをサポートします。

## <a name="syntax"></a>構文

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CVS リストボックス::CVSリストボックス](#cvslistbox)|`CVSListBox` オブジェクトを構築します。|
|`CVSListBox::~CVSListBox`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CVS リストボックス::アイテムの追加](#additem)|リスト コントロールに文字列を追加します。 ( `CVSListBoxBase::AddItem`をオーバーライドします)。|
|[CVSリストボックス::編集アイテム](#edititem)|リスト コントロール項目のテキストに対する編集操作を開始します。 ( `CVSListBoxBase::EditItem`をオーバーライドします)。|
|[CVS リストボックス::カウントを取得します。](#getcount)|編集可能なリスト コントロール内の文字列の数を取得します。 ( `CVSListBoxBase::GetCount`をオーバーライドします)。|
|[リストボックス::ゲットアイテムデータ](#getitemdata)|編集可能なリスト コントロール項目に関連付けられているアプリケーション固有の 32 ビット値を取得します。 ( `CVSListBoxBase::GetItemData`をオーバーライドします)。|
|[テキストを取得します。](#getitemtext)|編集可能なリスト コントロール項目のテキストを取得します。 ( `CVSListBoxBase::GetItemText`をオーバーライドします)。|
|[CVSリストボックス::ゲットセルアイテム](#getselitem)|編集可能なリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します。 ( `CVSListBoxBase::GetSelItem`をオーバーライドします)。|
|`CVSListBox::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 詳細とメソッド構文については[、「CWnd::P再翻訳メッセージ](../../mfc/reference/cwnd-class.md#pretranslatemessage)」を参照してください。 ( `CVSListBoxBase::PreTranslateMessage`をオーバーライドします)。|
|[アイテムを削除します。](#removeitem)|編集可能なリスト コントロールから項目を削除します。 ( `CVSListBoxBase::RemoveItem`をオーバーライドします)。|
|[CVSリストボックス::アイテムを選択します。](#selectitem)|編集可能なリスト コントロール文字列を選択します。 ( `CVSListBoxBase::SelectItem`をオーバーライドします)。|
|[リストボックス::セットアイテムデータ](#setitemdata)|アプリケーション固有の 32 ビット値を編集可能なリスト コントロール項目に関連付けます。 ( `CVSListBoxBase::SetItemData`をオーバーライドします)。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[リストボックス::ゲットリストフント](#getlisthwnd)|現在の埋め込みリスト ビュー コントロールへのハンドルを返します。|

## <a name="remarks"></a>解説

この`CVSListBox`クラスには、リスト コントロール内の項目を作成、変更、削除、または再配置できる一連の編集ボタンが用意されています。

次の図は、編集可能なリスト コントロールの画像です。 2 番目のリスト項目は「Item2」と題され、編集用に選択されます。

![CVSListBox コントロール](../../mfc/reference/media/cvslistbox.png "CVSListBox コントロール")

リソース エディターを使用して編集可能なリスト コントロールを追加する場合、エディタの **[ツールボックス**] ウィンドウに定義済みの編集可能なリスト コントロールが表示されないことに注意してください。 代わりに、**グループ ボックス**コントロールなどの静的コントロールを追加します。 フレームワークは、静的コントロールをプレースホルダーとして使用して、編集可能なリスト コントロールのサイズと位置を指定します。

ダイアログ ボックス テンプレートで編集可能なリスト コントロールを使用するには、`CVSListBox`ダイアログ ボックス クラスで変数を宣言します。 変数とコントロール間のデータ交換をサポートするには、ダイアログ`DDX_Control`ボックスの`DoDataExchange`メソッドでマクロ エントリを定義します。 既定では、編集可能なリスト コントロールは編集ボタンなしで作成されます。 継承された CVS リストボックスベース::SetStandardButtons メソッドを使用して、編集ボタンを有効にします。

詳細については、サンプル ディレクトリ、`New Controls`サンプル、Page3.cpp および Page3.h ファイルを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxvslistbox.h

## <a name="cvslistboxadditem"></a><a name="additem"></a>CVS リストボックス::アイテムの追加

リスト コントロールに文字列を追加します。

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>パラメーター

*ストリエスト*<br/>
[in]文字列への参照。

*dw データ*<br/>
[in]文字列に関連付けられているアプリケーション固有の 32 ビット値。 既定値は 0 です。

*をクリックします。*<br/>
[in]文字列を保持する位置の 0 から始まるインデックス。 *iIndex*パラメーターが -1 の場合、文字列はリストの末尾に追加されます。 既定値は -1 です。

### <a name="return-value"></a>戻り値

リスト コントロール内の文字列の位置を示す 0 から始まるインデックス。

### <a name="remarks"></a>解説

*dwData*パラメーターで指定された値を取得するには[、CVSListBox::GetItemData](#getitemdata)メソッドを使用します。 この値は、アプリケーション固有の整数または他のデータへのポインターです。

## <a name="cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVS リストボックス::CVSリストボックス

`CVSListBox` オブジェクトを構築します。

```
CVSListBox();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cvslistboxedititem"></a><a name="edititem"></a>CVSリストボックス::編集アイテム

リスト コントロール項目のテキストに対する編集操作を開始します。

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]リスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

編集操作が正常に開始された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ユーザーは、項目のラベルをダブルクリックするか、項目にフォーカスがあるときに**F2**キーまたは Space**キー**を押して編集操作を開始します。

## <a name="cvslistboxgetcount"></a><a name="getcount"></a>CVS リストボックス::カウントを取得します。

編集可能なリスト コントロール内の文字列の数を取得します。

```
virtual int GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト コントロールの項目の数。

### <a name="remarks"></a>解説

インデックスは 0 から始まるため、カウントは最後の項目のインデックス値より 1 大きいので注意してください。

## <a name="cvslistboxgetitemdata"></a><a name="getitemdata"></a>リストボックス::ゲットアイテムデータ

編集可能なリスト コントロール項目に関連付けられているアプリケーション固有の 32 ビット値を取得します。

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定した項目に関連付けられている 32 ビット値。

### <a name="remarks"></a>解説

32 ビット値をリスト コントロール 項目に関連付けるには[、CVSListBox::SetItemData](#setitemdata)または[CVSListBox::AddItem](#additem)メソッドを使用します。 この値は、アプリケーション固有の整数または他のデータへのポインターです。

## <a name="cvslistboxgetitemtext"></a><a name="getitemtext"></a>テキストを取得します。

編集可能なリスト コントロール項目のテキストを取得します。

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定した項目のテキストを含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

### <a name="remarks"></a>解説

## <a name="cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>リストボックス::ゲットリストフント

現在の埋め込みリスト ビュー コントロールへのハンドルを返します。

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>戻り値

埋め込みリスト ビュー コントロールへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、クラスをサポートする埋め込みリスト ビュー`CVSListBox`コントロールへのハンドルを取得するために使います。

## <a name="cvslistboxgetselitem"></a><a name="getselitem"></a>CVSリストボックス::ゲットセルアイテム

編集可能なリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します。

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、現在選択されている項目の 0 から始まるインデックス。それ以外の場合は -1。

### <a name="remarks"></a>解説

## <a name="cvslistboxremoveitem"></a><a name="removeitem"></a>アイテムを削除します。

編集可能なリスト コントロールから項目を削除します。

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定した項目が削除された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cvslistboxselectitem"></a><a name="selectitem"></a>CVSリストボックス::アイテムを選択します。

編集可能なリスト コントロール文字列を選択します。

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>パラメーター

*iItem*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、指定された項目を選択し、必要に応じて項目をスクロールして表示します。

## <a name="cvslistboxsetitemdata"></a><a name="setitemdata"></a>リストボックス::セットアイテムデータ

アプリケーション固有の 32 ビット値を編集可能なリスト コントロール項目に関連付けます。

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]編集可能なリスト コントロール項目の 0 から始まるインデックス。

*dw データ*<br/>
[in]32 ビット値。 この値は、アプリケーション固有の整数または他のデータへのポインターです。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
