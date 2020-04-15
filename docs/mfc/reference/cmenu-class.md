---
title: Cメニュークラス
ms.date: 11/04/2016
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
ms.openlocfilehash: 5ec97d8cf039034078f29b38fb6a41d6ff9a5e53
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369977"
---
# <a name="cmenu-class"></a>Cメニュークラス

Windows の `HMENU`をカプセル化したものです。

## <a name="syntax"></a>構文

```
class CMenu : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cメニュー::Cメニュー](#cmenu)|`CMenu` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|このメニューの末尾に新しい項目を追加します。|
|[Cメニュー::添付](#attach)|Windows のメニュー ハンドルをオブジェクト`CMenu`にアタッチします。|
|[メニュー::チェックメニューアイテム](#checkmenuitem)|ポップアップ メニューのメニュー項目の横にチェック マークを付けるか、またはメニュー項目のチェック マークを削除します。|
|[Cメニュー::チェックメニューラジオアイテム](#checkmenuradioitem)|メニュー項目の横にラジオ ボタンを配置し、そのオプション ボタンをグループ内の他のすべてのメニュー項目から削除します。|
|[Cメニュー::メニューを作成します。](#createmenu)|空のメニューを作成し、オブジェクトに`CMenu`アタッチします。|
|[メニュー::ポップアップメニューを作成します。](#createpopupmenu)|空のポップアップ メニューを作成し、`CMenu`オブジェクトにアタッチします。|
|[CMenu::Dエレテメニュー](#deletemenu)|メニューから指定した項目を削除します。 メニュー項目に関連付けられたポップアップ メニューがある場合、ポップアップ メニューへのハンドルを破棄し、そのメニューで使用されているメモリを解放します。|
|[CMenu::Dエレテ一時地図](#deletetempmap)|メンバー関数によって作成`CMenu`された一時オブジェクト`FromHandle`を削除します。|
|[CMenu::Dエストロイメニュー](#destroymenu)|オブジェクトにアタッチされたメニューを`CMenu`破棄し、メニューが占有していたすべてのメモリを解放します。|
|[CMenu::Dエタッハ](#detach)|Windows メニュー ハンドルをオブジェクトから`CMenu`切り離し、そのハンドルを返します。|
|[メニュー::Dローアイテム](#drawitem)|オーナー描画メニューの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。|
|[メニュー::メニュー項目を有効にする](#enablemenuitem)|メニュー項目を有効にする、無効にする、または淡色表示 (灰色) します。|
|[Cメニュー::ハンドルから](#fromhandle)|Windows メニュー ハンドル`CMenu`を指定したオブジェクトへのポインターを返します。|
|[メニュー::デフォルトアイテムを取得します。](#getdefaultitem)|指定したメニューの既定のメニュー項目を決定します。|
|[メニュー::メニューコンテキストヘルプId](#getmenucontexthelpid)|メニューに関連付けられているヘルプ コンテキスト ID を取得します。|
|[メニュー::メニュー情報](#getmenuinfo)|特定のメニューの情報を取得します。|
|[メニュー::メニュー項目数](#getmenuitemcount)|ポップアップ メニューまたはトップレベル メニューの項目数を指定します。|
|[メニュー::メニュー項目ID](#getmenuitemid)|指定した位置にあるメニュー項目のメニュー項目識別子を取得します。|
|[メニュー::メニュー項目情報](#getmenuiteminfo)|メニュー項目に関する情報を取得します。|
|[メニュー::メニュー状態を取得します。](#getmenustate)|指定したメニュー項目のステータスまたはポップアップ メニューの項目数を返します。|
|[メニュー::メニュー文字列を取得します。](#getmenustring)|指定したメニュー項目のラベルを取得します。|
|[メニュー::ゲットセーフメニュー](#getsafehmenu)|この`CMenu`オブジェクト`m_hMenu`でラップされた値を返します。|
|[メニュー::サブメニューを取得します。](#getsubmenu)|ポップアップ メニューへのポインターを取得します。|
|[CMenu::InsertMenu](#insertmenu)|新しいメニュー項目を指定した位置に挿入し、その他の項目をメニューの下に移動します。|
|[メニュー::メニュー項目の挿入](#insertmenuitem)|メニューの指定した位置に新しいメニュー項目を挿入します。|
|[メニュー::ロードメニュー](#loadmenu)|実行可能ファイルからメニュー リソースを読み込み、`CMenu`オブジェクトにアタッチします。|
|[メニュー::ロードメニュー間接的](#loadmenuindirect)|メニュー テンプレートからメニューをメモリに読み込み、`CMenu`オブジェクトにアタッチします。|
|[Cメニュー::メジャーアイテム](#measureitem)|オーナー描画メニューの作成時にメニューのサイズを決定するために、フレームワークによって呼び出されます。|
|[CMenu::ModifyMenu](#modifymenu)|指定した位置にある既存のメニュー項目を変更します。|
|[メニュー::メニューの削除](#removemenu)|指定したメニューから、関連付けられたポップアップ メニューを持つメニュー項目を削除します。|
|[Cメニュー::デフォルトアイテムを設定します。](#setdefaultitem)|指定したメニューの既定のメニュー項目を設定します。|
|[メニュー::メニューコンテキストヘルプId](#setmenucontexthelpid)|メニューに関連付けるヘルプ コンテキスト ID を設定します。|
|[メニュー::セットメニュー情報](#setmenuinfo)|特定のメニューに関する情報を設定します。|
|[をクリックします。](#setmenuitembitmaps)|指定したチェック マーク ビットマップをメニュー項目に関連付けます。|
|[メニュー::セットメニューアイテム情報](#setmenuiteminfo)|メニュー項目に関する情報を変更します。|
|[メニュー::トラックポップアップメニュー](#trackpopupmenu)|指定した位置にフローティング ポップアップ メニューを表示し、ポップアップ メニュー上の項目の選択を追跡します。|
|[Cメニュー::トラックポップアップメニュー](#trackpopupmenuex)|指定した位置にフローティング ポップアップ メニューを表示し、ポップアップ メニュー上の項目の選択を追跡します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cメニュー::演算子HMENU](#operator_hmenu)|メニュー オブジェクトのハンドルを取得します。|
|[Cメニュー::演算子!=](#operator_neq)|2 つのメニュー オブジェクトが等しくないかどうかを判断します。|
|[Cメニュー::演算子 ==](#operator_eq_eq)|2 つのメニュー オブジェクトが等しいかどうかを判断します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[メニュー::m_hMenu](#m_hmenu)|オブジェクトにアタッチされた Windows メニューへのハンドル`CMenu`を指定します。|

## <a name="remarks"></a>解説

メニューの作成、追跡、更新、および破棄を行うためのメンバー関数を提供します。

スタック`CMenu`フレーム上にローカルオブジェクトを作成し、必要に`CMenu`応じてメンバー関数を呼び出して新しいメニューを操作します。 次に[、CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu)を呼び出してメニューをウィンドウに設定し、その直後`CMenu`にオブジェクトの[Detach](#detach)メンバー関数を呼び出します。 この`CWnd::SetMenu`メンバー関数は、ウィンドウのメニューを新しいメニューに設定し、ウィンドウを再描画してメニューの変更を反映させ、メニューの所有権をウィンドウに渡します。 ローカル`CMenu`変数が`Detach`スコープ外に渡されるときに、`CMenu`オブジェクト`CMenu`デストラクタが所有していないメニューを破棄しないように、オブジェクトから HMENU をデタッチする呼び出し。 ウィンドウが破棄されると、メニュー自体は自動的に破棄されます。

[LoadMenuIndirect](#loadmenuindirect)メンバー関数を使用して、メモリ内のテンプレートからメニューを作成できますが[、LoadMenu](#loadmenu)の呼び出しによってリソースから作成されたメニューは保守が容易になり、メニュー リソース自体はメニュー エディターで作成および変更できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cmenuappendmenu"></a><a name="appendmenu"></a>Cメニュー::追加メニュー

メニューの末尾に新しい項目を追加します。

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>パラメーター

*Nflags*<br/>
メニューに追加するときの新しいメニュー項目の状態に関する情報を指定します。 「解説」セクションにリストされている 1 つ以上の値で構成されます。

*新しいアイテム*<br/>
新しいメニュー項目のコマンド ID を指定するか *、nFlags*が MF_POPUP に設定されている場合`HMENU`は、ポップアップ メニューのメニュー ハンドル ( ) を指定します。 *nIdNewItem*パラメーターは *、nFlags*がMF_SEPARATORに設定されている場合は無視されます (必要ありません)。

*新しいアイテムを表示します。*<br/>
新しいメニュー項目の内容を指定します。 *nFlags*パラメーターは、次の方法で*lpszNewItem*を解釈するために使用されます。

|Nflags|の解釈|
|------------|-----------------------------------|
|MF_OWNERDRAW|アプリケーションが指定した 32 ビット値を格納します。 この 32 ビット値は、WM_MEASUREITEMおよびWM_DRAWITEMメッセージを処理するときに、アプリケーションで使用できます。 値は、これらのメッセージで`itemData`提供される構造体のメンバーに格納されます。|
|MF_STRING|null で終わる文字列へのポインターを格納します。 これはデフォルトの解釈です。|
|MF_SEPARATOR|*lpszNewItem*パラメーターは無視されます (必要ありません)。|

*pBmp*<br/>
メニュー項目として`CBitmap`使用されるオブジェクトへのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

nFlags で値を設定することにより、アプリケーションはメニュー項目の*nFlags*状態を指定できます。 *nIDNewItem*がポップアップ メニューを指定すると、追加先のメニューの一部になります。 そのメニューが破棄されると、追加されたメニューも破棄されます。 競合を避けるために、追加されたメニューを`CMenu`オブジェクトからデタッチする必要があります。 MF_STRINGとMF_OWNERDRAWは、 の`AppendMenu`ビットマップ バージョンでは無効です。

次のリストは *、nFlags*で設定できるフラグを示しています。

- MF_CHECKED 項目の横に既定のチェック マークを付けるMF_UNCHECKEDの切り替えとして機能します。 アプリケーションがチェック マーク ビットマップを提供する場合[(SetMenuItemBitmaps](#setmenuitembitmaps)メンバー関数を参照)、"チェック マークオン" ビットマップが表示されます。

- MF_UNCHECKED 項目の横にあるチェック マークを削除するMF_CHECKEDとの切り替えとして機能します。 アプリケーションがチェック マーク ビットマップ (メンバー関数を`SetMenuItemBitmaps`参照) を提供すると、"チェック マーク オフ" ビットマップが表示されます。

- MF_DISABLED メニュー項目を無効にして、選択できないようにしますが、淡暗く表示されません。

- MF_ENABLED メニュー項目を選択して淡色表示の状態に戻します。

- MF_GRAYED メニュー項目を選択できないように無効にし、淡暗くします。

- MF_MENUBARBREAK項目を静的メニューの新しい行に配置するか、ポップアップ メニューの新しい列に配置します。 新しいポップアップメニュー列は、古い列と垂直分割線で区切られます。

- MF_MENUBREAK静的メニューの新しい行に項目を配置するか、ポップアップ メニューの新しい列に項目を配置します。 列の間に分割線は配置されません。

- MF_OWNERDRAWアイテムがオーナー描画項目であることを指定します。 メニューが初めて表示されるとき、メニューを所有するウィンドウは、メニュー項目の高さと幅を取得するWM_MEASUREITEMメッセージを受け取ります。 WM_DRAWITEM メッセージは、所有者がメニュー項目の外観を更新する必要がある場合に送信されるメッセージです。 このオプションは、トップレベルのメニュー項目には無効です。

- MF_POPUPメニュー項目に関連付けられたポップアップ メニューを持つ場合に指定します。 ID パラメーターは、項目に関連付けるポップアップ・メニューへのハンドルを指定します。 これは、トップレベルのポップアップメニューまたは階層ポップアップメニューをポップアップメニュー項目に追加するために使用されます。

- MF_SEPARATOR 水平分割線を描画します。 ポップアップメニューでのみ使用できます。 この線は、淡色表示、無効、または強調表示できません。 他のパラメーターは無視されます。

- MF_STRING メニュー項目が文字列であることを指定します。

次の各グループには、相互に排他的で、同時に使用できないフラグが一覧表示されます。

- MF_DISABLED、MF_ENABLED、MF_GRAYED

- MF_STRING、MF_OWNERDRAW、MF_SEPARATOR、およびビットマップバージョン

- MF_MENUBARBREAKとMF_MENUBREAK

- MF_CHECKEDとMF_UNCHECKED

ウィンドウ内のメニューが変更されると (ウィンドウが表示されるかどうかにかかわらず)、アプリケーションは[CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)を呼び出す必要があります。

### <a name="example"></a>例

  [CMenu::CreateMenu](#createmenu)の例を参照してください。

## <a name="cmenuattach"></a><a name="attach"></a>Cメニュー::添付

既存の Windows メニューをオブジェクト`CMenu`にアタッチします。

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*Hmenu*<br/>
Windows メニューへのハンドルを指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

メニューが既にオブジェクトにアタッチされている場合は、この関数を`CMenu`呼び出す必要があります。 メニュー ハンドルはデータ メンバー`m_hMenu`に格納されます。

操作するメニューが既にウィンドウに関連付けられている場合は[、CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)関数を使用してメニューへのハンドルを取得できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenucheckmenuitem"></a><a name="checkmenuitem"></a>メニュー::チェックメニューアイテム

ポップアップ メニューのメニュー項目にチェック マークを追加または削除します。

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>パラメーター

*チェックアイテム*<br/>
*nCheck*で指定された、チェックするメニュー項目を指定します。

*nチェック*<br/>
メニュー項目のチェック方法と、メニュー内での項目の位置の決定方法を指定します。 *nCheck*パラメーターは、MF_BYPOSITION フラグまたはMF_BYCOMMAND フラグを持つMF_CHECKEDまたはMF_UNCHECKEDの組み合わせにすることができます。 これらのフラグは、ビットごとの OR 演算子を使用して組み合わせることができます。 彼らは次の意味を持っています:

- MF_BYCOMMAND パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 これは既定値です。

- MF_BYPOSITION パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。

- MF_CHECKED 項目の横に既定のチェック マークを付けるMF_UNCHECKEDの切り替えとして機能します。

- MF_UNCHECKED 項目の横にあるチェック マークを削除するMF_CHECKEDとの切り替えとして機能します。

### <a name="return-value"></a>戻り値

項目の前の状態は、MF_CHECKEDまたはMF_UNCHECKED、またはメニュー項目が存在しない場合は 0xFFFFFFFF。

### <a name="remarks"></a>解説

*nIDCheckItem*パラメーターは、変更する項目を指定します。

*nIDCheckItem*パラメーターは、メニュー項目と同様にポップアップ メニュー項目を識別できます。 ポップアップメニュー項目をチェックするために特別な手順は必要ありません。 トップレベルのメニュー項目はチェックできません。 ポップアップ メニュー項目には、メニュー項目識別子が関連付けられていないため、位置によってチェックする必要があります。

### <a name="example"></a>例

  [CMenu::GetMenuState](#getmenustate)の例を参照してください。

## <a name="cmenucheckmenuradioitem"></a><a name="checkmenuradioitem"></a>Cメニュー::チェックメニューラジオアイテム

指定されたメニュー項目をチェックし、ラジオ項目にします。

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*最初の id*<br/>
オプション ボタン グループの最初のメニュー項目を指定します *(nFlags*の値に応じて、ID またはオフセットとして指定します)。

*NIDラスト*<br/>
オプション ボタン グループの最後のメニュー項目を指定します *(nFlags*の値に応じて、ID またはオフセットとして指定します)。

*nIDアイテム*<br/>
オプション ボタンでチェックされるグループ内の項目を指定します *(nFlags*の値に応じて、ID またはオフセット)。

*Nflags*<br/>
次の方法で *、nIDFirst* *、nIDLast、**および nIDItem*の解釈を指定します。

|Nflags|解釈|
|------------|--------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。|

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0

### <a name="remarks"></a>解説

同時に、関連するグループ内の他のすべてのメニュー項目のチェックを解除し、それらの項目のラジオ項目タイプフラグをクリアします。 チェック マークのビットマップではなく、ラジオ ボタン (箇条書き) ビットマップを使用して、チェックマークの項目が表示されます。

### <a name="example"></a>例

  [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)の例を参照してください。

## <a name="cmenucmenu"></a><a name="cmenu"></a>Cメニュー::Cメニュー

空のメニューを作成し、オブジェクトに`CMenu`アタッチします。

```
CMenu();
```

### <a name="remarks"></a>解説

メニューは、作成またはロードのメンバー関数のいずれかを呼び出すまで作成されません。`CMenu:`

- [メニューの作成](#createmenu)

- [メニューを作成します。](#createpopupmenu)

- [メニューを読み込む](#loadmenu)

- [ダイレクトメニュー](#loadmenuindirect)

- [Attach](#attach)

## <a name="cmenucreatemenu"></a><a name="createmenu"></a>Cメニュー::メニューを作成します。

メニューを作成し、オブジェクトに`CMenu`アタッチします。

```
BOOL CreateMenu();
```

### <a name="return-value"></a>戻り値

メニューが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メニューは最初は空です。 メニュー項目は、 または`AppendMenu``InsertMenu`メンバー関数を使用して追加できます。

メニューがウィンドウに割り当てられている場合、ウィンドウが破棄されると自動的に破棄されます。

メニューがウィンドウに割り当てられていない場合、アプリケーションは、メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーションは[、DestroyMenu](#destroymenu)メンバー関数を呼び出すことによってメニューを解放します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

## <a name="cmenucreatepopupmenu"></a><a name="createpopupmenu"></a>メニュー::ポップアップメニューを作成します。

ポップアップ メニューを作成し、オブジェクトに`CMenu`アタッチします。

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>戻り値

ポップアップ メニューが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メニューは最初は空です。 メニュー項目は、 または`AppendMenu``InsertMenu`メンバー関数を使用して追加できます。 アプリケーションは、既存のメニューまたはポップアップメニューにポップアップメニューを追加できます。 `TrackPopupMenu`このメンバー関数を使用して、このメニューをフローティング ポップアップ メニューとして表示し、ポップアップ メニューの選択内容を追跡することができます。

メニューがウィンドウに割り当てられている場合、ウィンドウが破棄されると自動的に破棄されます。 メニューが既存のメニューに追加されると、そのメニューが破棄されると自動的に破棄されます。

終了する前に、メニューがウィンドウに割り当てられていない場合、アプリケーションはポップアップメニューに関連付けられたシステムリソースを解放する必要があります。 アプリケーションは[、DestroyMenu](#destroymenu)メンバー関数を呼び出すことによってメニューを解放します。

### <a name="example"></a>例

  [CMenu::CreateMenu](#createmenu)の例を参照してください。

## <a name="cmenudeletemenu"></a><a name="deletemenu"></a>CMenu::Dエレテメニュー

メニューから項目を削除します。

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*n位置*<br/>
*nFlags*で指定された、削除するメニュー項目を指定します。

*Nflags*<br/>
nPosition を*nPosition*次のように解釈するために使用されます。

|Nflags|n位置の解釈|
|------------|---------------------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

メニュー項目に関連付けられたポップアップメニューがある場合、`DeleteMenu`ポップアップメニューへのハンドルが破棄され、ポップアップメニューで使用されているメモリが解放されます。

ウィンドウ内のメニューが変更されると (ウィンドウが表示されるかどうかにかかわらず)、アプリケーションは[CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)を呼び出す必要があります。

### <a name="example"></a>例

  [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)の例を参照してください。

## <a name="cmenudeletetempmap"></a><a name="deletetempmap"></a>CMenu::Dエレテ一時地図

`CWinApp`アイドル時ハンドラーによって自動的に呼び出され[、FromHandle](#fromhandle)メンバー関数によって作成された一時`CMenu`オブジェクトを削除します。

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>解説

`DeleteTempMap`オブジェクトを削除する前に、一時`CMenu`オブジェクトにアタッチされている Windows`CMenu`メニュー オブジェクトをデタッチします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

## <a name="cmenudestroymenu"></a><a name="destroymenu"></a>CMenu::Dエストロイメニュー

メニューと使用された Windows リソースを破棄します。

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>戻り値

メニューが破棄された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メニューは破棄される前に`CMenu`オブジェクトから切り離されます。 Windows`DestroyMenu`関数は、デストラクターで`CMenu`自動的に呼び出されます。

### <a name="example"></a>例

  [CMenu::CreateMenu](#createmenu)の例を参照してください。

## <a name="cmenudetach"></a><a name="detach"></a>CMenu::Dエタッハ

オブジェクトから Windows メニューを`CMenu`切り離し、ハンドルを返します。

```
HMENU Detach();
```

### <a name="return-value"></a>戻り値

HMENU 型のハンドルを Windows メニューに対して、成功した場合はメニューに移動します。それ以外の場合は NULL。

### <a name="remarks"></a>解説

データ`m_hMenu`メンバは NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenudrawitem"></a><a name="drawitem"></a>メニュー::Dローアイテム

オーナー描画メニューの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
必要な描画の種類に関する情報を含む[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)へのポインター。

### <a name="remarks"></a>解説

構造`itemAction`のメンバーは`DRAWITEMSTRUCT`、実行される描画アクションを定義します。 オーナー描画`CMenu`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションは、このメンバー関数の終了前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

構造体の説明については[、CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT`を参照してください。

### <a name="example"></a>例

次のコードは、MFC [CTRLTEST](../../overview/visual-cpp-samples.md)サンプルから取得されています。

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

## <a name="cmenuenablemenuitem"></a><a name="enablemenuitem"></a>メニュー::メニュー項目を有効にする

メニュー項目を有効にする、無効にする、または淡く設定します。

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>パラメーター

*NID 有効化アイテム*<br/>
*nEnable*で指定されたメニュー項目を指定します。 このパラメータでは、ポップアップメニュー項目と標準メニュー項目を指定できます。

*n有効*<br/>
実行するアクションを指定します。 MF_BYCOMMANDまたはMF_BYPOSITIONを使用して、MF_DISABLED、MF_ENABLED、またはMF_GRAYEDの組み合わせが可能です。 これらの値は、ビットごとの OR 演算子を使用して組み合わせることができます。 これらの値には次の意味があります。

- MF_BYCOMMAND パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 これは既定値です。

- MF_BYPOSITION パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。

- MF_DISABLED メニュー項目を無効にして、選択できないようにしますが、淡暗く表示されません。

- MF_ENABLED メニュー項目を選択して淡色表示の状態に戻します。

- MF_GRAYED メニュー項目を選択できないように無効にし、淡暗くします。

### <a name="return-value"></a>戻り値

前の状態 (MF_DISABLED、MF_ENABLED、またはMF_GRAYED) または -1 (無効な場合)。

### <a name="remarks"></a>解説

メニューの[作成](#createmenu)、[挿入メニュー](#insertmenu)、[変更メニュー](#modifymenu)、および[読み込みメニューの間接的](#loadmenuindirect)なメンバー関数は、メニュー項目の状態 (有効、無効、または淡色表示) を設定することもできます。

MF_BYPOSITION値を使用するには、アプリケーションが正しい`CMenu`. メニュー`CMenu`バーの が使用されている場合、トップレベルのメニュー項目 (メニュー バーの項目) が影響を受けます。 ポップアップメニューまたはネストされたポップアップメニューの項目の状態を位置ごとに設定するには、アプリケーションでポップアップメニューの を`CMenu`指定する必要があります。

アプリケーションでMF_BYCOMMAND フラグを指定すると、 に従属するすべてのポップアップ メニュー項目がチェックされます`CMenu`。したがって、重複するメニュー項目が存在しない限り`CMenu`、メニューバーの を使用するだけで十分です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

## <a name="cmenufromhandle"></a><a name="fromhandle"></a>Cメニュー::ハンドルから

メニューへの Windows`CMenu`ハンドルを指定したオブジェクトへのポインターを返します。

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*Hmenu*<br/>
メニューへの Windows ハンドル。

### <a name="return-value"></a>戻り値

一時的または永続的`CMenu`なを指すポインター。

### <a name="remarks"></a>解説

`CMenu`オブジェクトが Windows メニュー オブジェクトにまだアタッチされていない場合は、`CMenu`一時オブジェクトが作成され、アタッチされます。

この一`CMenu`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時オブジェクトが削除されます。

### <a name="example"></a>例

  [CMenu::CreateMenu](#createmenu)の例を参照してください。

## <a name="cmenugetdefaultitem"></a><a name="getdefaultitem"></a>メニュー::デフォルトアイテムを取得します。

指定したメニューの既定のメニュー項目を決定します。

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*グマディフラグ*<br/>
メニュー項目の検索方法を指定する値。 このパラメーターには、なし、1 つ、または次の値の組み合わせを指定できます。

|[値]|意味|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|サブメニューを開く既定の項目の場合、関数は対応するサブメニューを再帰的に検索することを指定します。 サブメニューに既定の項目がない場合、戻り値はサブメニューを開く項目を識別します。<br /><br /> 既定では、サブメニューを開く項目かどうかにかかわらず、指定されたメニューの最初の既定の項目が返されます。|
|GMDI_USEDISABLED|無効にした場合でも、関数が既定の項目を返すように指定します。<br /><br /> 既定では、無効または灰色の項目はスキップされます。|

*フバイポス*<br/>
メニュー項目の識別子またはその位置を取得するかどうかを指定する値。 このパラメーターが FALSE の場合、識別子が返されます。 それ以外の場合は、位置が返されます。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はメニュー項目の識別子または位置になります。 関数が失敗した場合、戻り値は -1 です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 関数の動作を実装[します](/windows/win32/api/winuser/nf-winuser-getmenudefaultitem)。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenugetmenucontexthelpid"></a><a name="getmenucontexthelpid"></a>メニュー::メニューコンテキストヘルプId

に関連付けられている`CMenu`コンテキスト ヘルプ ID を取得します。

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>戻り値

コンテキスト ヘルプ ID が`CMenu`現在関連付けられている場合は、その ID が関連付けられています。それ以外の場合はゼロ。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenugetmenuinfo"></a><a name="getmenuinfo"></a>メニュー::メニュー情報

メニューの情報を取得します。

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>パラメーター

*lpcmi*<br/>
メニューの情報を含む[MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo)構造体へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は 0 以外になります。それ以外の場合、戻り値は 0 です。

### <a name="remarks"></a>解説

メニューに関する情報を取得します。

## <a name="cmenugetmenuitemcount"></a><a name="getmenuitemcount"></a>メニュー::メニュー項目数

ポップアップ メニューまたはトップレベル メニューの項目数を指定します。

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>戻り値

関数が正常に実行された場合のメニューの項目数。それ以外の場合は -1。

### <a name="example"></a>例

  [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)の例を参照してください。

## <a name="cmenugetmenuitemid"></a><a name="getmenuitemid"></a>メニュー::メニュー項目ID

*nPos*で定義された位置にあるメニュー項目のメニュー項目識別子を取得します。

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
ID を取得するメニュー項目の位置 (0 から始まる) を指定します。

### <a name="return-value"></a>戻り値

関数が正常に実行された場合の、ポップアップ メニュー内の指定された項目の項目 ID。 指定した項目がポップアップメニューの場合(ポップアップメニュー内の項目とは対照的に)、戻り値は -1 です。 *nPos が*セパレータ メニュー項目に対応する場合、戻り値は 0 です。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenugetmenuiteminfo"></a><a name="getmenuiteminfo"></a>メニュー::メニュー項目情報

メニュー項目に関する情報を取得します。

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*アイテム*<br/>
情報を取得するメニュー項目の識別子または位置。 このパラメーターの意味は、 の`ByPos`値によって異なります。

*をクリックします。*<br/>
メニューに関する情報を含む、Windows SDK で説明されているように[、MENUITEMINFO](/windows/win32/api/winuser/ns-winuser-menuiteminfow)へのポインター。

*フバイポス*<br/>
の意味を指定する値`nIDItem`。 既定では、uItem`ByPos`がメニュー項目識別子であることを示す FALSE です。 FALSE`ByPos`に設定されていない場合は、メニュー項目の位置を示します。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は 0 以外になります。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Windows SDK で説明されているように、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を使用します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 関数[の GetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-getmenuiteminfow)の動作を実装します。 MFC の実装では`GetMenuItemInfo`、メニューへのハンドルは使用しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

## <a name="cmenugetmenustate"></a><a name="getmenustate"></a>メニュー::メニュー状態を取得します。

指定したメニュー項目のステータスまたはポップアップ メニューの項目数を返します。

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
*nFlags*で指定されるメニュー項目 ID を指定します。

*Nflags*<br/>
*nID*の性質を指定します。 次のいずれかの値を指定できます。

- MF_BYCOMMAND パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 これは既定値です。

- MF_BYPOSITION パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。

### <a name="return-value"></a>戻り値

指定された項目が存在しない場合の値 0xFFFFFFFF。 *nId*がポップアップメニューを識別する場合、上位バイトにはポップアップメニュー内の項目数が含まれ、下位バイトにはポップアップメニューに関連付けられたメニューフラグが含まれます。 それ以外の場合、戻り値は次のリストの値のマスク (ブール OR) になります (このマスクは *、nId*が識別するメニュー項目の状態を表します)。

- MF_CHECKED 項目の横に既定のチェック マークを付けるMF_UNCHECKEDの切り替えとして機能します。 アプリケーションがチェック マーク ビットマップ (メンバー関数を`SetMenuItemBitmaps`参照) を提供すると、"チェック マークオン" ビットマップが表示されます。

- MF_DISABLED メニュー項目を無効にして、選択できないようにしますが、淡暗く表示されません。

- MF_ENABLED メニュー項目を選択して淡色表示の状態に戻します。 この定数の値は 0 です。この値を使用する場合、アプリケーションは 0 に対して fail をテストしないでください。

- MF_GRAYED メニュー項目を選択できないように無効にし、淡暗くします。

- MF_MENUBARBREAK項目を静的メニューの新しい行に配置するか、ポップアップ メニューの新しい列に配置します。 新しいポップアップメニュー列は、古い列と垂直分割線で区切られます。

- MF_MENUBREAK静的メニューの新しい行に項目を配置するか、ポップアップ メニューの新しい列に項目を配置します。 列の間に分割線は配置されません。

- MF_SEPARATOR 水平分割線を描画します。 ポップアップメニューでのみ使用できます。 この線は、淡色表示、無効、または強調表示できません。 他のパラメーターは無視されます。

- MF_UNCHECKED 項目の横にあるチェック マークを削除するMF_CHECKEDとの切り替えとして機能します。 アプリケーションがチェック マーク ビットマップ (メンバー関数を`SetMenuItemBitmaps`参照) を提供すると、"チェック マーク オフ" ビットマップが表示されます。 この定数の値は 0 です。この値を使用する場合、アプリケーションは 0 に対して fail をテストしないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

## <a name="cmenugetmenustring"></a><a name="getmenustring"></a>メニュー::メニュー文字列を取得します。

指定したメニュー項目のラベルを指定したバッファーにコピーします。

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>パラメーター

*nIDアイテム*<br/>
*nFlags*の値に応じて、メニュー項目の整数識別子またはメニュー項目のオフセットを指定します。

*文字列*<br/>
ラベルを受け取るバッファーへのポイント。

*文字列*<br/>
コピーされた`CString`メニュー文字列を受け取るオブジェクトへの参照。

*カウントカウント*<br/>
コピーするラベルの最大長 (文字数) を指定します。 ラベルが*nMaxCount*で指定された最大値より長い場合、余分な文字は切り捨てられます。

*Nflags*<br/>
*パラメーター*の解釈を指定します。 次のいずれかの値を指定できます。

|Nflags|nIDアイテムの解釈|
|------------|-------------------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。|

### <a name="return-value"></a>戻り値

バッファにコピーされる実際の文字数を指定します。

### <a name="remarks"></a>解説

*nMaxCount*パラメーターは、文字列を終了する NULL 文字を収容するために、ラベル内の文字数より 1 大きい値にする必要があります。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenugetsafehmenu"></a><a name="getsafehmenu"></a>メニュー::ゲットセーフメニュー

この`CMenu`オブジェクトでラップされた HMENU または NULL`CMenu`ポインターを返します。

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>例

  [CMenu::ロードメニュー](#loadmenu)の例を参照してください。

## <a name="cmenugetsubmenu"></a><a name="getsubmenu"></a>メニュー::サブメニューを取得します。

ポップアップ メニュー`CMenu`のオブジェクトを取得します。

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
メニューに含まれるポップアップ メニューの位置を指定します。 最初のメニュー項目の位置の値は 0 から始まります。 この関数では、ポップアップメニューの識別子は使用できません。

### <a name="return-value"></a>戻り値

ポップアップ メニューが`CMenu`指定された`m_hMenu`位置に存在する場合、メンバーがポップアップ メニューへのハンドルを含むオブジェクトへのポインター。それ以外の場合は NULL。 オブジェクトが`CMenu`存在しない場合は、一時的なオブジェクトが作成されます。 返`CMenu`されたポインターは格納しないでください。

### <a name="example"></a>例

  [CMenu::トラックポップアップメニュー](#trackpopupmenu)の例を参照してください。

## <a name="cmenuinsertmenu"></a><a name="insertmenu"></a>メニュー::メニューの挿入

*nPosition*で指定した位置に新しいメニュー項目を挿入し、その他の項目をメニューの下に移動します。

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>パラメーター

*n位置*<br/>
新しいメニュー項目を挿入する前のメニュー項目を指定します。 *nFlags*パラメーターを使用して、次の方法で*nPosition*を解釈できます。

|Nflags|n位置の解釈|
|------------|---------------------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。 *nPosition が*-1 の場合、新しいメニュー項目はメニューの末尾に追加されます。|

*Nflags*<br/>
*nPosition*の解釈方法を指定し、メニューに追加されたときの新しいメニュー項目の状態に関する情報を指定します。 設定できるフラグの一覧については、メンバー関数の[AppendMenu](#appendmenu)を参照してください。 複数の値を指定するには、ビットごとの OR 演算子を使用して、MF_BYCOMMAND またはMF_BYPOSITION フラグと組み合わせます。

*新しいアイテム*<br/>
新しいメニュー項目のコマンド ID を指定するか *、nFlags*がMF_POPUPに設定されている場合は、ポップアップ メニューのメニュー ハンドル (HMENU) を指定します。 *nIdNewItem*パラメーターは *、nFlags*がMF_SEPARATORに設定されている場合は無視されます (必要ありません)。

*新しいアイテムを表示します。*<br/>
新しいメニュー項目の内容を指定します。 *nFlags*は、次の方法で*lpszNewItem*を解釈するために使用できます。

|Nflags|の解釈|
|------------|-----------------------------------|
|MF_OWNERDRAW|アプリケーションが指定した 32 ビット値を格納します。 この 32 ビット値は[、WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem)および[WM_DRAWITEM](/windows/win32/Controls/wm-drawitem)メッセージ`itemData`によって提供される構造体のメンバー内でアプリケーションで使用できます。 これらのメッセージは、メニュー項目が最初に表示されるか、変更されたときに送信されます。|
|MF_STRING|null で終わる文字列への長いポインターを格納します。 これはデフォルトの解釈です。|
|MF_SEPARATOR|*lpszNewItem*パラメーターは無視されます (必要ありません)。|

*pBmp*<br/>
メニュー項目として`CBitmap`使用されるオブジェクトへのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

nFlags で値を設定することにより、アプリケーションはメニュー項目の*nFlags*状態を指定できます。

ウィンドウ内のメニューが変更されると (ウィンドウが表示されるかどうかにかかわらず)、アプリケーションは`CWnd::DrawMenuBar`.

*nIDNewItem*がポップアップ メニューを指定すると、ポップアップ メニューが挿入されるメニューの一部になります。 そのメニューが破棄されると、挿入されたメニューも破棄されます。 挿入されたメニューは、競合を`CMenu`避けるためにオブジェクトから切り離す必要があります。

アクティブなマルチ ドキュメント インターフェイス (MDI) 子ウィンドウが最大化され、アプリケーションがこの関数を呼び出してMF_BYPOSITION フラグを指定して、MDI アプリケーションのメニューにポップアップ メニューを挿入すると、メニューは予想より 1 つ後ろに挿入されます。 これは、アクティブな MDI 子ウィンドウのコントロール メニューが MDI フレーム ウィンドウのメニュー バーの最初の位置に挿入されるために発生します。 メニューを正しく配置するには、アプリケーションは、それ以外の場合に使用される位置の値に 1 を追加する必要があります。 アプリケーションは、WM_MDIGETACTIVE メッセージを使用して、現在アクティブな子ウィンドウが最大化されているかどうかを判断できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

## <a name="cmenuinsertmenuitem"></a><a name="insertmenuitem"></a>メニュー::メニュー項目の挿入

メニューの指定した位置に新しいメニュー項目を挿入します。

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*アイテム*<br/>
Windows SDK の[挿入メニューアイテム](/windows/win32/api/winuser/nf-winuser-insertmenuitemw)の*uItem*の説明を参照してください。

*をクリックします。*<br/>
の Windows SDK で`InsertMenuItem`*の lpmii*の説明を参照してください。

*フバイポス*<br/>
Windows SDK の*fByPosition*の`InsertMenuItem`説明を参照してください。

### <a name="remarks"></a>解説

この関数は、Windows SDK で説明されている[InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw)をラップします。

## <a name="cmenuloadmenu"></a><a name="loadmenu"></a>メニュー::ロードメニュー

アプリケーションの実行可能ファイルからメニュー リソースを読み込み、オブジェクトに`CMenu`アタッチします。

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
読み込むメニュー リソースの名前を含む null で終わる文字列を指します。

*リソース*<br/>
読み込むメニュー リソースのメニュー ID を指定します。

### <a name="return-value"></a>戻り値

メニュー リソースが正常に読み込まれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メニューがウィンドウに割り当てられていない場合、アプリケーションは、メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーションは[、DestroyMenu](#destroymenu)メンバー関数を呼び出すことによってメニューを解放します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

## <a name="cmenuloadmenuindirect"></a><a name="loadmenuindirect"></a>メニュー::ロードメニュー間接的

メモリ内のメニュー テンプレートからリソースを読み込み、オブジェクト`CMenu`にアタッチします。

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
メニュー テンプレート (単一の[MENUITEMTEMPLATEHEADER](/windows/win32/api/winuser/ns-winuser-menuitemtemplateheader)構造体と 1 つ以上の[MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate)構造体のコレクション) へのポイント。 これら 2 つの構造体の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

メニュー リソースが正常に読み込まれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メニュー テンプレートは、ヘッダーの後に 1 つ以上の[MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate)構造体のコレクションを指定します。

バージョン番号は 0 にする必要があります。

フラグ`mtOption`には、ポップアップ リストの最後の項目と、メイン リストの最後の項目のMF_ENDを含める必要があります。 その他`AppendMenu`のフラグについては、メンバー関数を参照してください。 MF_POPUP`mtId`が で指定されている場合、メンバーは MENUITEMTEMPLATE 構造体から`mtOption`省略する必要があります。

MENUITEMTEMPLATE 構造体に割り当てられた領域は、メニュー項目`mtString`の名前を NULL で終わる文字列として格納するのに十分な大きさである必要があります。

メニューがウィンドウに割り当てられていない場合、アプリケーションは、メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーションは[、DestroyMenu](#destroymenu)メンバー関数を呼び出すことによってメニューを解放します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

## <a name="cmenum_hmenu"></a><a name="m_hmenu"></a>メニュー::m_hMenu

オブジェクトにアタッチされた Windows メニューの HMENU`CMenu`ハンドルを指定します。

```
HMENU m_hMenu;
```

### <a name="example"></a>例

  [CMenu::ロードメニュー](#loadmenu)の例を参照してください。

## <a name="cmenumeasureitem"></a><a name="measureitem"></a>Cメニュー::メジャーアイテム

オーナー描画スタイルのメニューが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
`MEASUREITEMSTRUCT`構造体へのポインター。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も実行しません。 このメンバー関数をオーバーライドし、メニュー`MEASUREITEMSTRUCT`のディメンションを Windows に通知する構造を設定します。

構造体の説明については[、CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT`を参照してください。

### <a name="example"></a>例

次のコードは、MFC [CTRLTEST](../../overview/visual-cpp-samples.md)サンプルから取得されています。

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

## <a name="cmenumodifymenu"></a><a name="modifymenu"></a>メニュー::メニューの変更

*nPosition*で指定された位置にある既存のメニュー項目を変更します。

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>パラメーター

*n位置*<br/>
変更するメニュー項目を指定します。 *nFlags*パラメーターを使用して、次の方法で*nPosition*を解釈できます。

|Nflags|n位置の解釈|
|------------|---------------------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。|

*Nflags*<br/>
*nPosition*の解釈方法を指定し、メニュー項目に加えられる変更に関する情報を提供します。 設定できるフラグの一覧については、メンバー関数の[AppendMenu](#appendmenu)を参照してください。

*新しいアイテム*<br/>
変更されたメニュー項目のコマンド ID を指定するか *、nFlags*が MF_POPUP に設定されている場合は、ポップアップ メニューのメニュー ハンドル (HMENU) を指定します。 *nIdNewItem*パラメーターは *、nFlags*がMF_SEPARATORに設定されている場合は無視されます (必要ありません)。

*新しいアイテムを表示します。*<br/>
新しいメニュー項目の内容を指定します。 *nFlags*パラメーターは、次の方法で*lpszNewItem*を解釈するために使用できます。

|Nflags|の解釈|
|------------|-----------------------------------|
|MF_OWNERDRAW|アプリケーションが指定した 32 ビット値を格納します。 この 32 ビット値は、アプリケーションがMF_MEASUREITEM処理してMF_DRAWITEMするときに使用できます。|
|MF_STRING|null で終わる文字列またはを指す長いポインターを`CString`含みます。|
|MF_SEPARATOR|*lpszNewItem*パラメーターは無視されます (必要ありません)。|

*pBmp*<br/>
メニュー項目として`CBitmap`使用されるオブジェクトへのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アプリケーションは*nFlags*の値を設定することによって、メニュー項目の新しい状態を指定します。 この関数がメニュー項目に関連付けられているポップアップメニューを置き換える場合、古いポップアップメニューは破棄され、ポップアップメニューで使用されているメモリが解放されます。

*nIDNewItem*がポップアップ メニューを指定すると、ポップアップ メニューが挿入されるメニューの一部になります。 そのメニューが破棄されると、挿入されたメニューも破棄されます。 挿入されたメニューは、競合を`CMenu`避けるためにオブジェクトから切り離す必要があります。

ウィンドウ内のメニューが変更されると (ウィンドウが表示されるかどうかにかかわらず)、アプリケーションは`CWnd::DrawMenuBar`. 既存のメニュー項目の属性を変更するには、`CheckMenuItem`および`EnableMenuItem`メンバー関数を使用するほうがはるかに高速です。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenuoperator-hmenu"></a><a name="operator_hmenu"></a>Cメニュー::演算子HMENU

`CMenu`この演算子は、オブジェクトのハンドルを取得するために使用します。

```
operator HMENU() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトの`CMenu`ハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用して、Windows API を直接呼び出すことができます。

## <a name="cmenuoperator-"></a><a name="operator_neq"></a>Cメニュー::演算子!=

2 つのメニューが論理的に等しくないかどうかを判断します。

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
比較対象の `CMenu` オブジェクトです。

### <a name="remarks"></a>解説

左側のメニュー オブジェクトが右側のメニュー オブジェクトと等しくないかどうかをテストします。

## <a name="cmenuoperator-"></a><a name="operator_eq_eq"></a>Cメニュー::演算子 ==

2 つのメニューが論理的に等しいかどうかを判断します。

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
比較対象の `CMenu` オブジェクトです。

### <a name="remarks"></a>解説

左側のメニュー オブジェクトが、右側のメニュー オブジェクトと等しいかどうかをテストします (HMENU 値を参照)。

## <a name="cmenuremovemenu"></a><a name="removemenu"></a>メニュー::メニューの削除

関連付けられたポップアップ メニューを含むメニュー項目をメニューから削除します。

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*n位置*<br/>
削除するメニュー項目を指定します。 *nFlags*パラメーターを使用して、次の方法で*nPosition*を解釈できます。

|Nflags|n位置の解釈|
|------------|---------------------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。|

*Nflags*<br/>
*nPosition の*解釈方法を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ポップアップメニューのハンドルは破壊されないため、メニューを再利用できます。 この関数を呼び出す前に、`GetSubMenu`アプリケーションはメンバー関数を呼び出`CMenu`して、再利用するポップアップ オブジェクトを取得できます。

ウィンドウ内のメニューが変更された場合 (ウィンドウが表示されているかどうかに関係なく) 常に、アプリケーションは`CWnd::DrawMenuBar`呼び出す必要があります。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenusetdefaultitem"></a><a name="setdefaultitem"></a>Cメニュー::デフォルトアイテムを設定します。

指定したメニューの既定のメニュー項目を設定します。

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*アイテム*<br/>
新しい既定のメニュー項目の識別子または位置、または既定の項目の場合は - 1。 このパラメーターの意味は *、fByPos*の値によって異なります。

*フバイポス*<br/>
*uItem*の意味を指定する値。 このパラメーターが FALSE の場合 *、uItem*はメニュー項目識別子です。 それ以外の場合は、メニュー項目の位置です。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は 0 以外になります。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Windows SDK で説明されているように、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を使用します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 関数[SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem)の動作を実装します。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenusetmenucontexthelpid"></a><a name="setmenucontexthelpid"></a>メニュー::メニューコンテキストヘルプId

コンテキスト ヘルプ ID を`CMenu`に関連付けます。

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
に関連付`CMenu`けるコンテキスト ヘルプ ID。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0

### <a name="remarks"></a>解説

メニュー内のすべての項目がこの識別子を共有します— 個々のメニュー項目にヘルプコンテキスト識別子を付加することはできません。

### <a name="example"></a>例

  [CMenu::InsertMenu](#insertmenu)の例を参照してください。

## <a name="cmenusetmenuinfo"></a><a name="setmenuinfo"></a>メニュー::セットメニュー情報

メニューの情報を設定します。

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>パラメーター

*lpcmi*<br/>
メニューの情報を含む[MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo)構造体へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は 0 以外になります。それ以外の場合、戻り値は 0 です。

### <a name="remarks"></a>解説

メニューに関する特定の情報を設定します。

## <a name="cmenusetmenuitembitmaps"></a><a name="setmenuitembitmaps"></a>をクリックします。

指定したビットマップをメニュー項目に関連付けます。

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>パラメーター

*n位置*<br/>
変更するメニュー項目を指定します。 *nFlags*パラメーターを使用して、次の方法で*nPosition*を解釈できます。

|Nflags|n位置の解釈|
|------------|---------------------------------|
|MF_BYCOMMAND|パラメーターが既存のメニュー項目のコマンド ID を提供することを指定します。 MF_BYCOMMANDもMF_BYPOSITIONも設定されていない場合、これはデフォルトです。|
|MF_BYPOSITION|パラメーターが既存のメニュー項目の位置を指定することを指定します。 最初の項目は位置 0 です。|

*Nflags*<br/>
*nPosition の*解釈方法を指定します。

*チェックされていない*<br/>
チェックされていないメニュー項目に使用するビットマップを指定します。

*チェック*<br/>
チェックされるメニュー項目に使用するビットマップを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

メニュー項目のチェックボックスをオンにするかオフにするかにかかわらず、Windows ではメニュー項目の横に適切なビットマップが表示されます。

*pBmpUnchecked*または*pBmpChecked*が NULL の場合、対応する属性のメニュー項目の横に何も表示されません。 両方のパラメーターが NULL の場合、Windows は項目がチェックされるときにデフォルトのチェック マークを使用し、項目がオフのときにチェック マークを削除します。

メニューが破棄された場合、これらのビットマップは破棄されません。アプリケーションはそれらを破棄する必要があります。

Windows`GetMenuCheckMarkDimensions`関数は、メニュー項目に使用される既定のチェック マークのサイズを取得します。 アプリケーションは、これらの値を使用して、この関数で提供されるビットマップに適したサイズを決定します。 サイズを取得し、ビットマップを作成し、それらを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

## <a name="cmenusetmenuiteminfo"></a><a name="setmenuiteminfo"></a>メニュー::セットメニューアイテム情報

メニュー項目に関する情報を変更します。

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*アイテム*<br/>
Windows SDK の[設定メニュー項目情報](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow)の*uItem*の説明を参照してください。

*をクリックします。*<br/>
の Windows SDK で`SetMenuItemInfo`*の lpmii*の説明を参照してください。

*フバイポス*<br/>
Windows SDK の*fByPosition*の`SetMenuItemInfo`説明を参照してください。

### <a name="remarks"></a>解説

この関数は、Windows SDK で説明されている[SetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow)をラップします。

## <a name="cmenutrackpopupmenu"></a><a name="trackpopupmenu"></a>メニュー::トラックポップアップメニュー

指定した位置にフローティング ポップアップ メニューを表示し、ポップアップ メニュー上の項目の選択を追跡します。

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>パラメーター

*Nflags*<br/>
画面位置フラグとマウス位置フラグを指定します。 使用可能なフラグの一覧については[、「TrackPopupMenu」](/windows/win32/api/winuser/nf-winuser-trackpopupmenu)を参照してください。

*X*<br/>
ポップアップ メニューの画面座標の水平位置を指定します。 *nFlags*パラメーターの値に応じて、メニューは左揃え、右揃え、またはこの位置を基準に中央揃えにすることができます。

*Y*<br/>
画面上のメニューの上部の画面座標の垂直方向の位置を指定します。

*Pwnd*<br/>
ポップアップ メニューを所有するウィンドウを識別します。 TPM_NONOTIFY フラグが指定されている場合でも、このパラメーターを NULL にすることはできません。 このウィンドウは、メニューからすべてのWM_COMMANDメッセージを受け取ります。 Windows 3.1 以降では、ウィンドウが戻るまで`TrackPopupMenu`WM_COMMANDメッセージを受信しません。 Windows 3.0 では、ウィンドウは、WM_COMMANDメッセージ`TrackPopupMenu`を受け取って、メッセージを返します。

*Lprect*<br/>
無視されます。

### <a name="return-value"></a>戻り値

このメソッドは、Windows SDK で[トラックポップアップ メニュー](/windows/win32/api/winuser/nf-winuser-trackpopupmenu)を呼び出した結果を返します。

### <a name="remarks"></a>解説

フローティングポップアップメニューは、画面上の任意の場所に表示できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

## <a name="cmenutrackpopupmenuex"></a><a name="trackpopupmenuex"></a>Cメニュー::トラックポップアップメニュー

指定した位置にフローティング ポップアップ メニューを表示し、ポップアップ メニュー上の項目の選択を追跡します。

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>パラメーター

*fuフラグ*<br/>
拡張メニューのさまざまな機能を指定します。 すべての値とその意味の一覧については[、「TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)」を参照してください。

*X*<br/>
ポップアップ メニューの画面座標の水平位置を指定します。

*Y*<br/>
画面上のメニューの上部の画面座標の垂直方向の位置を指定します。

*Pwnd*<br/>
ポップアップ メニューを所有し、作成されたメニューからメッセージを受信するウィンドウへのポインター。 このウィンドウは、現在のアプリケーションの任意のウィンドウにできますが、NULL にすることはできません。 *fuFlags*パラメーターに TPM_NONOTIFYを指定した場合、この関数はメッセージを*pWnd*に送信しません。 *関数は、pWnd*が指すウィンドウがWM_COMMANDメッセージを受信するために返す必要があります。

*lptpm*<br/>
メニューが重ならないようにする画面の領域を指定する[TPMPARAMS](/windows/win32/api/winuser/ns-winuser-tpmparams)構造体へのポインター。 このパラメーターは NULL にすることができます。

### <a name="return-value"></a>戻り値

*fuFlags*パラメーターにTPM_RETURNCMDを指定した場合、戻り値はユーザーが選択した項目のメニュー項目識別子です。 ユーザーが選択せずにメニューをキャンセルした場合、またはエラーが発生した場合は、戻り値は 0 になります。

*fuFlags*パラメーターに TPM_RETURNCMD を指定しない場合、関数が成功した場合は 0 以外の値が返され、失敗した場合は 0 が返されます。 拡張エラー情報を取得するには[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

フローティングポップアップメニューは、画面上の任意の場所に表示できます。 ポップアップ メニュー作成時のエラー処理の詳細については、「 [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL テスト](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ダイナメニュー](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)
