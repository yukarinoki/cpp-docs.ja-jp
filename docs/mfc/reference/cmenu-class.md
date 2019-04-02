---
title: CMenu クラス
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
ms.openlocfilehash: 464b59f7e598ea1901cf88c47c5887cbbf308607
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770851"
---
# <a name="cmenu-class"></a>CMenu クラス

Windows の `HMENU`をカプセル化したものです。

## <a name="syntax"></a>構文

```
class CMenu : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|`CMenu` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|このメニューの末尾に新しい項目を追加します。|
|[CMenu::Attach](#attach)|Windows メニューを識別するハンドルをアタッチ、`CMenu`オブジェクト。|
|[CMenu::CheckMenuItem](#checkmenuitem)|チェック マークの横に配置するか、ポップアップ メニューにメニュー項目からチェック マークを削除します。|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|メニュー項目の横にあるラジオ ボタンを配置し、グループ内の他のメニュー項目のすべてのラジオ ボタンを削除します。|
|[CMenu::CreateMenu](#createmenu)|空のメニューを作成し、それにアタッチします、`CMenu`オブジェクト。|
|[CMenu::CreatePopupMenu](#createpopupmenu)|空のポップアップ メニューを作成しにアタッチします、`CMenu`オブジェクト。|
|[CMenu::DeleteMenu](#deletemenu)|メニューから、指定した項目を削除します。 メニュー項目に関連付けられたポップアップ メニューがある場合は、ポップアップ メニューへのハンドルを破棄し、使用されるメモリを解放します。|
|[CMenu::DeleteTempMap](#deletetempmap)|一時的な削除`CMenu`によって作成されたオブジェクト、`FromHandle`メンバー関数。|
|[メニューを破棄](#destroymenu)|アタッチされているメニューの破棄、`CMenu`オブジェクトし、メニューが占有されているメモリを解放します。|
|[CMenu::Detach](#detach)|Windows メニュー ハンドルをデタッチする`CMenu`オブジェクトおよびハンドルを返します。|
|[CMenu::DrawItem](#drawitem)|ビジュアルな部分のオーナー描画メニューが変更されたときにフレームワークによって呼び出されます。|
|[CMenu::EnableMenuItem](#enablemenuitem)|有効、無効化、または灰色表示になります (グレー表示) メニュー項目。|
|[CMenu::FromHandle](#fromhandle)|ポインターを返します、`CMenu`オブジェクトの Windows メニューのハンドルを指定します。|
|[CMenu::GetDefaultItem](#getdefaultitem)|指定されたメニューの既定のメニュー項目を決定します。|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|メニューに関連付けられたヘルプ コンテキスト ID を取得します。|
|[CMenu::GetMenuInfo](#getmenuinfo)|特定のメニューに関する情報を取得します。|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|ポップアップまたは最上位メニュー内の項目の数を決定します。|
|[CMenu::GetMenuItemID](#getmenuitemid)|指定した位置にあるメニュー項目のメニュー項目の識別子を取得します。|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|メニュー項目に関する情報を取得します。|
|[CMenu::GetMenuState](#getmenustate)|ポップアップ メニューで、指定したメニュー項目または項目の数の状態を返します。|
|[CMenu::GetMenuString](#getmenustring)|指定したメニュー項目のラベルを取得します。|
|[CMenu::GetSafeHmenu](#getsafehmenu)|返します、`m_hMenu`これによってラップされた`CMenu`オブジェクト。|
|[CMenu::GetSubMenu](#getsubmenu)|ポップアップ メニューへのポインターを取得します。|
|[CMenu::InsertMenu](#insertmenu)|その他の項目を移動して、メニューを指定した位置にある新しいメニュー項目を挿入します。|
|[CMenu::InsertMenuItem](#insertmenuitem)|新しいメニュー項目をメニュー内の指定した位置に挿入します。|
|[CMenu::LoadMenu](#loadmenu)|実行可能ファイルからメニュー リソースを読み込みにアタッチします、`CMenu`オブジェクト。|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|メモリ内のメニューのテンプレートから、メニューを読み込みにアタッチします、`CMenu`オブジェクト。|
|[CMenu::MeasureItem](#measureitem)|メニューの大きさをオーナー描画メニューが作成されたときにフレームワークによって呼び出されます。|
|[CMenu::ModifyMenu](#modifymenu)|指定した位置にある既存のメニュー項目を変更します。|
|[CMenu::RemoveMenu](#removemenu)|指定されたメニューから、関連付けられたポップアップ メニューにメニュー項目を削除します。|
|[CMenu::SetDefaultItem](#setdefaultitem)|指定されたメニューの既定のメニュー項目を設定します。|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|メニューに関連付けられるヘルプ コンテキスト ID を設定します。|
|[CMenu::SetMenuInfo](#setmenuinfo)|特定のメニューに関する情報を設定します。|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|指定されたチェック マークのビットマップをメニュー項目に関連付けます。|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|メニュー項目に関する情報を変更します。|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CMenu::operator HMENU](#operator_hmenu)|メニュー オブジェクトのハンドルを取得します。|
|[CMenu::operator! =](#operator_neq)|2 つのオブジェクトが等しくないかどうかを決定します。|
|[CMenu::operator = =](#operator_eq_eq)|2 つのオブジェクトが等しいかどうかを決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CMenu::m_hMenu](#m_hmenu)|アタッチされている Windows メニューへのハンドルを指定します、`CMenu`オブジェクト。|

## <a name="remarks"></a>Remarks

作成、追跡、更新、およびメニューを破棄するメンバー関数を提供します。

作成、`CMenu`オブジェクトとしてローカル スタック フレームに対して呼び出す`CMenu`の必要に応じて、[新規] メニューを操作するメンバー関数。 次に、呼び出す[CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu)ウィンドウ、メニューの設定をすぐに続くへの呼び出し、`CMenu`オブジェクトの[デタッチ](#detach)メンバー関数。 `CWnd::SetMenu`メンバー関数の新しいメニュー ウィンドウのメニューを設定、メニューの変更を反映するように再描画するウィンドウおよびも、メニューの所有権をウィンドウに渡します。 呼び出し`Detach`から HMENU をデタッチします、`CMenu`オブジェクト、そのときに、ローカル`CMenu`変数がスコープ外に移り、`CMenu`されなく所有しているメニューを破棄するオブジェクトのデストラクターは行われません。 ウィンドウが破棄されるときに、メニュー自体が自動的に破棄されます。

使用することができます、 [LoadMenuIndirect](#loadmenuindirect)メンバー関数は、メモリ内テンプレートからのメニューがリソースからの呼び出しによって作成されたメニューを作成する[LoadMenu](#loadmenu)はより簡単に保持されると、メニュー リソース自体作成し、メニュー エディターで変更できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="appendmenu"></a>  CMenu::AppendMenu

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

*nFlags*<br/>
メニューに追加されたときに、新しいメニュー項目の状態に関する情報を指定します。 1 つ以上の「解説」に記載した値で構成されます。

*nIDNewItem*<br/>
新しいメニュー項目のコマンド ID を指定しますまたは、 *nFlags*ならば、メニューのハンドルに設定されている ( `HMENU`) のポップアップ メニュー。 *NIDNewItem*パラメーターは無視されます (不要) 場合*nFlags* MF_SEPARATOR に設定されます。

*lpszNewItem*<br/>
新しいメニュー項目の内容を指定します。 *NFlags*パラメーターが解釈に使用*lpszNewItem*次のようにします。

|nFlags|LpszNewItem の解釈|
|------------|-----------------------------------|
|MF_OWNERDRAW|アプリケーションは、メニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、ためおよび WM_DRAWITEM メッセージを処理するときに、アプリケーションで使用できます。 値が格納されている、`itemData`それらのメッセージで提供される構造体のメンバー。|
|MF_STRING|Null で終わる文字列へのポインターが含まれています。 これは、既定の解釈です。|
|MF_SEPARATOR|*LpszNewItem* (不要) パラメーターは無視されます。|

*pBmp*<br/>
指す、`CBitmap`メニュー項目として使用されるオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションで値を設定 メニュー項目の状態を指定できます*nFlags*します。 ときに*nIDNewItem*ポップアップ メニューを指定しますが追加されます メニューの一部となります。 メニューが破棄される場合、追加したメニューも破棄されます。 追加のメニューからデタッチする必要があります、`CMenu`競合を回避するオブジェクト。 MF_STRING および MF_OWNERDRAW はのビットマップのバージョンに対して有効ではないことに注意してください。`AppendMenu`します。

次に示しますで設定できるフラグ*nFlags*:

- 既定値を配置する MF_UNCHECKED でトグルとしてを動作は、項目の横にマークを確認します。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、 [SetMenuItemBitmaps](#setmenuitembitmaps)メンバー関数)、「のチェック マーク」ビットマップが表示されます。

- MF_UNCHECKED を項目の横にあるチェック マークを削除するのには、トグルとして機能します。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「チェック マークをオフ」ビットマップが表示されます。

- MF_DISABLED を選択することはできませんが、淡色表示には、メニュー項目を無効にします。

- MF_ENABLED は、選択できるし、グレーの状態から復元できるように、メニュー項目を使用できます。

- 選択することはできませんし、淡色表示にするように、MF_GRAYED はメニュー項目を無効にします。

- MF_MENUBARBREAK は、静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 新しいポップアップ メニュー列は、垂直方向の境界線で、古い列から区切られます。

- MF_MENUBREAK は、静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 列の間の区切り線は適用されません。

- MF_OWNERDRAW では、項目がオーナー描画項目を指定します。 最初に、メニューが表示されたら、メニューを所有するウィンドウが高さと幅のメニュー項目を取得するようメッセージを受信します。 所有者は、メニュー項目の外観を更新する必要がありますたびに、送信は、ならなくです。 このオプションは、トップレベルのメニュー項目に対して有効ではできません。

- ならばでは、メニュー項目に、ポップアップ メニューが関連付けられていることを指定します。 ID パラメーターには、ポップアップ メニュー項目に関連付けられるを識別するハンドルを指定します。 これは、最上位レベルのポップアップ メニューまたはポップアップ メニューを階層のいずれかをポップアップ メニュー項目を追加するために使用されます。

- MF_SEPARATOR では、水平方向の境界線を描画します。 ポップアップ メニューでのみ使用できます。 この行の淡色表示されている、無効になっている、または強調表示されていることはできません。 その他のパラメーターは無視されます。

- MF_STRING では、メニュー項目が、文字の文字列を指定します。

次のグループのそれぞれは相互に排他的と同時に使用できないフラグを一覧します。

- MF_DISABLED、MF_ENABLED、および MF_GRAYED

- MF_STRING、MF_OWNERDRAW、MF_SEPARATOR、およびビットマップのバージョン

- MF_MENUBARBREAK と MF_MENUBREAK

- MF_UNCHECKED

内のメニューに配置されるたびに (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります[かかわらず](../../mfc/reference/cwnd-class.md#drawmenubar)します。

### <a name="example"></a>例

  例をご覧ください[CMenu::CreateMenu](#createmenu)します。

##  <a name="attach"></a>  CMenu::Attach

アタッチに既存の Windows メニュー、`CMenu`オブジェクト。

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*hMenu*<br/>
Windows メニューへのハンドルを指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

メニューが既にアタッチされている場合、この関数は呼び出されませんが、`CMenu`オブジェクト。 メニュー ハンドルに格納されている、`m_hMenu`データ メンバー。

使用することができますを操作するメニューが既に、ウィンドウに関連付けられている場合、[とき](../../mfc/reference/cwnd-class.md#getmenu)メニューへのハンドルを取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem

チェック マークを追加します。 またはのポップアップ メニューにメニュー項目のチェック マークを削除します。

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>パラメーター

*nIDCheckItem*<br/>
チェックするメニュー項目を指定によって決定される*を確認してください*します。

*確認してください。*<br/>
メニュー項目を確認する方法と、メニュー内の項目の位置を確認する方法を指定します。 *を確認してください*パラメーターをまたは MF_UNCHECKED MF_BYPOSITION またはときのフラグと組み合わせて指定できます。 これらのフラグは、ビットごとの OR 演算子を使用して組み合わせることができます。 次の意味があります。

- ときは、パラメーターが既存のメニュー項目のコマンド ID を指定します。 既定値です。

- パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。

- 既定値を配置する MF_UNCHECKED でトグルとしてを動作は、項目の横にマークを確認します。

- MF_UNCHECKED を項目の横にあるチェック マークを削除するのには、トグルとして機能します。

### <a name="return-value"></a>戻り値

項目の以前の状態:または MF_UNCHECKED、または 0 xffffffff メニュー項目が存在しなかった場合。

### <a name="remarks"></a>Remarks

*NIDCheckItem*パラメーターを変更する項目を指定します。

*NIDCheckItem*メニュー項目と同様に、ポップアップ メニュー項目のパラメーターが見つかる場合があります。 ポップアップ メニュー項目を確認するのには、特別な手順は必要ありません。 トップレベルのメニュー項目をチェックすることはできません。 関連付けられているメニュー項目の識別子がないために、位置によってポップアップ メニュー項目をチェックする必要があります。

### <a name="example"></a>例

  例をご覧ください[CMenu::GetMenuState](#getmenustate)します。

##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem

指定したメニュー項目を確認し、オプションの項目になります。

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*nIDFirst*<br/>
指定します (ID またはの値に応じて、オフセットとして*nFlags*) ラジオ ボタン グループの最初のメニュー項目。

*nIDLast*<br/>
指定します (ID またはの値に応じて、オフセットとして*nFlags*) ラジオ ボタン グループの最後のメニュー項目。

*nIDItem*<br/>
指定します (ID またはの値に応じて、オフセットとして*nFlags*) オプション ボタンとチェックされるグループ内の項目。

*nFlags*<br/>
解釈を指定します*のど*、 *nIDLast*、および*nIDItem*次のようにします。

|nFlags|解釈|
|------------|--------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。|

### <a name="return-value"></a>戻り値

成功した場合、0 以外の場合それ以外の場合 0

### <a name="remarks"></a>Remarks

関数は、同時に関連付けられているグループ内の他のすべてのメニュー項目をオフにし、それらの項目についての選択項目型のフラグをクリアします。 チェック マークのビットマップではなく、ラジオ ボタン (または行頭文字) のビットマップを使用してチェックされている項目が表示されます。

### <a name="example"></a>例

  例をご覧ください[ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)します。

##  <a name="cmenu"></a>  CMenu::CMenu

空のメニューを作成し、それにアタッチします、`CMenu`オブジェクト。

```
CMenu();
```

### <a name="remarks"></a>Remarks

作成のいずれかを呼び出すかのメンバー関数を読み込むまで、メニューは作成されません。 `CMenu:`

- [CreateMenu](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Attach](#attach)

##  <a name="createmenu"></a>  CMenu::CreateMenu

メニューを作成し、それにアタッチ、`CMenu`オブジェクト。

```
BOOL CreateMenu();
```

### <a name="return-value"></a>戻り値

0 以外の場合、メニューが正常に作成された場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

メニューは、最初は空です。 使用してメニュー項目を追加することができます、`AppendMenu`または`InsertMenu`メンバー関数。

ウィンドウに、メニューが割り当てられる場合、ウィンドウが破棄されるときに自動的に破棄されます。

終了する前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーションが呼び出すことによって、メニューを解放、 [DestroyMenu](#destroymenu)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu

ポップアップ メニューを作成しにアタッチします、`CMenu`オブジェクト。

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>戻り値

ポップアップ メニューが正常に作成された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

メニューは、最初は空です。 使用してメニュー項目を追加することができます、`AppendMenu`または`InsertMenu`メンバー関数。 アプリケーションでは、既存のメニューまたはポップアップ メニューに、ポップアップ メニューを追加できます。 `TrackPopupMenu`メンバー関数は、浮動小数点のポップアップ メニューとしてこのメニューを表示して、ポップアップ メニューで選択内容を追跡するために、使用可能性があります。

ウィンドウに、メニューが割り当てられる場合、ウィンドウが破棄されるときに自動的に破棄されます。 既存のメニューにメニューを追加すると場合、そのメニューが破棄されるときに自動的に破棄されます。

終了する前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、ポップアップ メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーションが呼び出すことによって、メニューを解放、 [DestroyMenu](#destroymenu)メンバー関数。

### <a name="example"></a>例

  例をご覧ください[CMenu::CreateMenu](#createmenu)します。

##  <a name="deletemenu"></a>  CMenu::DeleteMenu

メニューから項目を削除します。

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*nPosition*<br/>
によって決定される、削除するにはメニュー アイテムを指定します*nFlags*します。

*nFlags*<br/>
解釈するために使用*照合を n 続行*次のようにします。

|nFlags|照合を n 続行の解釈|
|------------|---------------------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

メニュー項目に関連付けられたポップアップ メニュー場合`DeleteMenu`ポップアップ メニューへのハンドルを破棄し、ポップアップ メニューで使用されるメモリを解放します。

内のメニューに配置されるたびに (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります[かかわらず](../../mfc/reference/cwnd-class.md#drawmenubar)します。

### <a name="example"></a>例

  例をご覧ください[とき](../../mfc/reference/cwnd-class.md#getmenu)します。

##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap

によって自動的に呼び出されます、`CWinApp`アイドル処理ハンドラーを削除一時`CMenu`によって作成されたオブジェクト、 [FromHandle](#fromhandle)メンバー関数。

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Remarks

`DeleteTempMap` 一時的に接続されている Windows メニュー オブジェクトをデタッチ`CMenu`オブジェクトを削除する前に、`CMenu`オブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

##  <a name="destroymenu"></a>  CMenu::DestroyMenu

メニューと使用されていたすべての Windows リソースを破棄します。

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>戻り値

メニューが破棄された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

メニューは、デタッチ、`CMenu`オブジェクトが破棄される前にします。 Windows`DestroyMenu`で自動的に呼び出される関数は、`CMenu`デストラクター。

### <a name="example"></a>例

  例をご覧ください[CMenu::CreateMenu](#createmenu)します。

##  <a name="detach"></a>  CMenu::Detach

Windows メニューからのデタッチ、`CMenu`オブジェクトおよびハンドルを返します。

```
HMENU Detach();
```

### <a name="return-value"></a>戻り値

型 HMENU、成功した場合は、Windows メニューへのハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

`m_hMenu`データ メンバーが NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="drawitem"></a>  CMenu::DrawItem

ビジュアルな部分のオーナー描画メニューが変更されたときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
ポインターを[DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)のために必要な図面の種類に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

`itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行する描画の動作を定義します。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CMenu`オブジェクト。 アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバー関数の終了前にします。

参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)の説明については、`DRAWITEMSTRUCT`構造体。

### <a name="example"></a>例

次のコードは、MFC [CTRLTEST](../../overview/visual-cpp-samples.md)サンプル。

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

##  <a name="enablemenuitem"></a>  CMenu::EnableMenuItem

有効または、無効にすると、暗転するメニュー項目。

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>パラメーター

*nIDEnableItem*<br/>
有効にするメニュー項目を指定によって決定される*nEnable*します。 このパラメーターには、標準のメニュー項目だけでなく、ポップアップ メニュー項目を指定できます。

*nEnable*<br/>
実行するアクションを指定します。 MF_DISABLED、MF_ENABLED、またはときまたは MF_BYPOSITION の MF_GRAYED の組み合わせであることができます。 これらの値は、ビットごとの OR 演算子を使用して組み合わせることができます。 これらの値には、次の意味があります。

- ときは、パラメーターが既存のメニュー項目のコマンド ID を指定します。 既定値です。

- パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。

- MF_DISABLED を選択することはできませんが、淡色表示には、メニュー項目を無効にします。

- MF_ENABLED は、選択できるし、グレーの状態から復元できるように、メニュー項目を使用できます。

- 選択することはできませんし、淡色表示にするように、MF_GRAYED はメニュー項目を無効にします。

### <a name="return-value"></a>戻り値

以前の状態 (MF_DISABLED、MF_ENABLED、または MF_GRAYED) または有効でない場合は-1。

### <a name="remarks"></a>Remarks

[CreateMenu](#createmenu)、[項目](#insertmenu)、[メニュー](#modifymenu)、および[LoadMenuIndirect](#loadmenuindirect)メンバー関数は、(有効になっている、状態にも設定できます淡色表示されているか、無効にする) のメニュー項目。

MF_BYPOSITION 値を使用して、適切なを使用するアプリケーションが必要です`CMenu`します。 場合、`CMenu`のメニュー バーを使用すると、トップレベルのメニュー項目 (メニュー バーの項目) が影響を受けます。 位置によってポップアップまたは入れ子になったポップアップ メニュー項目の状態を設定するアプリケーションを指定する必要があります、`CMenu`のポップアップ メニュー。

Windows が従属するすべてのポップアップ メニュー項目をチェックするときフラグを指定する場合、アプリケーション、 `CMenu`。 したがって、を使用して、重複するメニュー項目が存在する場合を除き、`CMenu`のメニュー バーで十分です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

##  <a name="fromhandle"></a>  CMenu::FromHandle

ポインターを返します、`CMenu`メニューへの Windows ハンドルを指定したオブジェクト。

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*hMenu*<br/>
メニューへの Windows ハンドル。

### <a name="return-value"></a>戻り値

ポインター、`CMenu`一時的または永続的があります。

### <a name="remarks"></a>Remarks

場合、`CMenu`オブジェクトが、一時的な Windows メニュー オブジェクトに既にアタッチされていない`CMenu`オブジェクトを作成し、接続されています。

この一時`CMenu`オブジェクトは、次回、アプリケーションがあるすべての一時オブジェクトを削除する時点で、イベント ループでのアイドル時間までのみ有効です。

### <a name="example"></a>例

  例をご覧ください[CMenu::CreateMenu](#createmenu)します。

##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem

指定されたメニューの既定のメニュー項目を決定します。

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*gmdiFlags*<br/>
メニュー項目の検索方法を指定する値。 このパラメーターには、なし、1 つ、または、次の値の組み合わせを指定できます。

|[値]|説明|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|既定の項目がいずれかのサブメニューを開く場合は、関数は、対応するサブメニューを再帰的に検索するを指定します。 既定の項目のサブメニューがない場合は、戻り値は、サブメニューを開く項目を識別します。<br /><br /> 既定では、サブメニューを開く項目であるかどうかにかかわらず、指定されたメニューの既定の最初の項目を返します。|
|GMDI_USEDISABLED|関数は、無効になっている場合でも、既定の項目を返すにを指定します。<br /><br /> 既定では、関数は、無効または淡色表示の項目をスキップします。|

*どの*<br/>
メニュー項目の識別子またはその位置を取得するかどうかを指定する値。 このパラメーターが FALSE の場合は、識別子が返されます。 それ以外の場合、位置が返されます。

### <a name="return-value"></a>戻り値

関数が成功すると、戻り値は、識別子またはメニュー項目の位置。 関数が失敗した場合、戻り値は - 1 です。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 関数の動作を実装[GetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-getmenudefaultitem)」の説明に従って、Windows SDK。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId

ID に関連付けられているコンテキスト ヘルプを取得します。`CMenu`します。

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>戻り値

ID に関連付けられているコンテキスト ヘルプ`CMenu`; いずれかがある場合は 0 それ以外の場合。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo

メニューの情報を取得します。

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>パラメーター

*lpcmi*<br/>
ポインターを[保持](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo)メニューの情報を含む構造体。

### <a name="return-value"></a>戻り値

戻り値は 0 以外の場合は、関数が成功すると、それ以外の場合、戻り値は 0 です。

### <a name="remarks"></a>Remarks

この関数では、メニューに関する情報を取得します。

##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount

ポップアップまたは最上位メニュー内の項目の数を決定します。

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>戻り値

関数が成功した場合は、メニュー内の項目の数それ以外の場合は-1。

### <a name="example"></a>例

  例をご覧ください[とき](../../mfc/reference/cwnd-class.md#getmenu)します。

##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID

によって定義された位置にあるメニュー項目のメニュー項目の識別子を取得します。 *nPos*します。

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
位置 (0 から始まる) メニュー項目の ID を取得するを指定します。

### <a name="return-value"></a>戻り値

関数が成功した場合に、ポップアップ メニューで指定した項目の項目の ID。 指定した項目が (ポップアップ メニュー内の項目) ではなくポップアップ メニューの場合は、戻り値は-1。 場合*nPos*対応区切り記号のメニュー項目には、戻り値は 0 です。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo

メニュー項目に関する情報を取得します。

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*uItem*<br/>
識別子またはに関する情報を取得するメニュー項目の位置。 このパラメーターの意味は、の値によって異なります。`ByPos`します。

*lpMenuItemInfo*<br/>
ポインターを[MENUITEMINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuiteminfoa)」の説明に従って Windows SDK のメニューに関する情報が含まれています。

*どの*<br/>
値の意味を指定する`nIDItem`します。 既定では、 `ByPos` false では、メニュー項目の識別子を示します。 場合`ByPos`が設定されていないを FALSE にメニュー項目の位置を示します。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は 0 以外の値です。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Win32 関数を使用して[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)」の説明に従って、Windows SDK。

### <a name="remarks"></a>Remarks

このメンバー関数の動作を実装する、Win32 関数の[GetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-getmenuiteminfoa)」の説明に従って、Windows SDK。 MFC 実装で`GetMenuItemInfo`メニューのハンドルを使用しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

##  <a name="getmenustate"></a>  CMenu::GetMenuState

ポップアップ メニューで、指定したメニュー項目または項目の数の状態を返します。

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
によって決定されるメニュー項目 ID を指定*nFlags*します。

*nFlags*<br/>
性質を指定*nID*します。 次の値のいずれかを指定できます。

- ときは、パラメーターが既存のメニュー項目のコマンド ID を指定します。 既定値です。

- パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。

### <a name="return-value"></a>戻り値

値が指定した項目が存在しない場合、0 xffffffff。 場合*nId*識別ポップアップ メニューでは、上位バイトがポップアップ メニュー項目の数を含むし、下位バイトには、ポップアップ メニューに関連付けられたメニュー フラグが含まれています。 戻り値は、次の一覧から値のマスク (論理 OR) をそれ以外の場合 (このマスク メニューの状態を説明している項目*nId*を識別します)。

- 既定値を配置する MF_UNCHECKED でトグルとしてを動作は、項目の横にマークを確認します。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「のチェック マーク」ビットマップが表示されます。

- MF_DISABLED を選択することはできませんが、淡色表示には、メニュー項目を無効にします。

- MF_ENABLED は、選択できるし、グレーの状態から復元できるように、メニュー項目を使用できます。 この定数の値は 0 になります。この値を使用する場合、アプリケーションのテストはに対して 0 を返しますいない必要があります。

- 選択することはできませんし、淡色表示にするように、MF_GRAYED はメニュー項目を無効にします。

- MF_MENUBARBREAK は、静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 新しいポップアップ メニュー列は、垂直方向の境界線で、古い列から区切られます。

- MF_MENUBREAK は、静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 列の間の区切り線は適用されません。

- MF_SEPARATOR では、水平方向の境界線を描画します。 ポップアップ メニューでのみ使用できます。 この行の淡色表示されている、無効になっている、または強調表示されていることはできません。 その他のパラメーターは無視されます。

- MF_UNCHECKED を項目の横にあるチェック マークを削除するのには、トグルとして機能します。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「チェック マークをオフ」ビットマップが表示されます。 この定数の値は 0 になります。この値を使用する場合、アプリケーションのテストはに対して 0 を返しますいない必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

##  <a name="getmenustring"></a>  CMenu::GetMenuString

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

*nIDItem*<br/>
値に応じて、メニューにメニュー項目の整数の識別子またはメニュー項目のオフセットを指定*nFlags*します。

*lpString*<br/>
ラベルを受け取るバッファーへのポインター。

*rString*<br/>
参照を`CString`をコピーしたメニュー文字列を受け取るオブジェクト。

*nMaxCount*<br/>
コピーされるラベルの最大長 (文字) で指定します。 ラベルはで指定された最大長を超えて*nMaxCount*、余分な文字は切り捨てられます。

*nFlags*<br/>
解釈を指定します、 *nIDItem*パラメーター。 次の値のいずれかを指定できます。

|nFlags|NIDItem の解釈|
|------------|-------------------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。|

### <a name="return-value"></a>戻り値

実際、null 終端文字を含まない、バッファーにコピーされた文字数を指定します。

### <a name="remarks"></a>Remarks

*NMaxCount*パラメーターは、文字列を終了する null 文字を対応するために、ラベルの文字数を超えるのいずれかを指定する必要があります。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu

これによってラップされた HMENU を返します`CMenu`オブジェクト、または NULL`CMenu`ポインター。

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>例

  例をご覧ください[CMenu::LoadMenu](#loadmenu)します。

##  <a name="getsubmenu"></a>  CMenu::GetSubMenu

取得、`CMenu`のポップアップ メニュー オブジェクト。

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
メニューに含まれているポップアップ メニューの位置を指定します。 位置の値は、最初のメニュー項目の 0 から始まります。 ポップアップ メニューの識別子は、この関数では使用できません。

### <a name="return-value"></a>戻り値

ポインターを`CMenu`オブジェクト`m_hMenu`メンバーが指定された位置にポップアップ メニューが存在する場合、ポップアップ メニューへのハンドルには含まれています。 それ以外の場合は NULL です。 場合、`CMenu`オブジェクトが存在しないその一時的なものが作成されます。 `CMenu`返されたポインターを格納する必要があります。

### <a name="example"></a>例

  例をご覧ください[CMenu::TrackPopupMenu](#trackpopupmenu)します。

##  <a name="insertmenu"></a>  CMenu::InsertMenu

指定された位置に新しいメニュー項目を挿入*照合を n 続行*し、メニューの他のアイテムを移動します。

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

*nPosition*<br/>
その前に、新しいメニュー項目が挿入されるメニュー項目を指定します。 *NFlags*の解釈にパラメーターを使用できる*照合を n 続行*次の方法で。

|nFlags|照合を n 続行の解釈|
|------------|---------------------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。 場合*照合を n 続行*-1 で、新しいメニュー項目がメニューの末尾に追加されます。|

*nFlags*<br/>
指定する方法*照合を n 続行*は解釈され、メニューに追加されたときに、新しいメニュー項目の状態に関する情報を指定します。 設定できるフラグの一覧は、次を参照してください。、[は](#appendmenu)メンバー関数。 1 つ以上の値を指定するには、ビットごとの OR 演算子を使用してときまたは MF_BYPOSITION フラグと組み合わせることです。

*nIDNewItem*<br/>
新しいメニュー項目のコマンド ID を指定しますまたは、 *nFlags*ならば、ポップアップ メニューのメニューのハンドル (HMENU) に設定されます。 *NIDNewItem*パラメーターは無視されます (不要) 場合*nFlags* MF_SEPARATOR に設定されます。

*lpszNewItem*<br/>
新しいメニュー項目の内容を指定します。 *nFlags*の解釈に使用できる*lpszNewItem*次のようにします。

|nFlags|LpszNewItem の解釈|
|------------|-----------------------------------|
|MF_OWNERDRAW|アプリケーションは、メニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値でアプリケーションに使用、`itemData`によって提供される構造体のメンバー、[よう](/windows/desktop/Controls/wm-measureitem)と[WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem)メッセージ。 メニュー項目が最初に表示されるかが変更される、これらのメッセージが送信されます。|
|MF_STRING|Null で終わる文字列への long ポインターが含まれています。 これは、既定の解釈です。|
|MF_SEPARATOR|*LpszNewItem* (不要) パラメーターは無視されます。|

*pBmp*<br/>
指す、`CBitmap`メニュー項目として使用されるオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションで値を設定 メニュー項目の状態を指定できます*nFlags*します。

内のメニューに配置されるたびに (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります`CWnd::DrawMenuBar`します。

ときに*nIDNewItem*ポップアップ メニューを指定しますが挿入されるメニューの一部となります。 メニューが破棄されると、挿入されたメニューも破棄されます。 挿入のメニューからデタッチする必要があります、`CMenu`競合を回避するオブジェクト。

マルチ ドキュメント インターフェイス (MDI) 子ウィンドウが最大表示されたアクティブなと、ポップアップ メニューを MDI アプリケーションのメニューで、この関数を呼び出すと、メニューの MF_BYPOSITION フラグを指定するのには、アプリケーションによる挿入位置を 1 つ、遠くよりも左を挿入する場合必要です。 これは、アクティブな MDI 子ウィンドウのコントロール メニューが MDI フレーム ウィンドウのメニュー バーの最初の位置に挿入されるために発生します。 メニューを正しく配置するには、アプリケーションは 1 を使用する場合は位置の値に追加する必要があります。 アプリケーションは、現在アクティブな子ウィンドウを最大化するかどうかを判断するのに WM_MDIGETACTIVE メッセージを使用することができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

##  <a name="insertmenuitem"></a>  CMenu::InsertMenuItem

新しいメニュー項目をメニュー内の指定した位置に挿入します。

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*uItem*<br/>
説明を参照してください。 *uItem*で[InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema) Windows SDK に含まれています。

*lpMenuItemInfo*<br/>
説明を参照してください。 *lpmii*で`InsertMenuItem`Windows SDK に含まれています。

*どの*<br/>
説明を参照してください。 *fByPosition*で`InsertMenuItem`Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

この関数をラップ[InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema)Windows SDK で説明します。

##  <a name="loadmenu"></a>  CMenu::LoadMenu

アプリケーションの実行可能ファイルからメニュー リソースを読み込みにアタッチします、`CMenu`オブジェクト。

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
読み込む] メニューの [リソースの名前を含む null で終わる文字列へのポインター。

*可能*<br/>
読み込むメニュー リソースのメニュー ID を指定します。

### <a name="return-value"></a>戻り値

メニュー リソースが正常に読み込まれている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

終了する前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーションが呼び出すことによって、メニューを解放、 [DestroyMenu](#destroymenu)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect

メモリ内のメニューのテンプレートからリソースを読み込むしにアタッチします、`CMenu`オブジェクト。

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>パラメーター

*lpMenuTemplate*<br/>
メニューのテンプレートを指す (これは、1 つ[MENUITEMTEMPLATEHEADER](/windows/desktop/api/winuser/ns-winuser-menuitemtemplateheader)構造と 1 つまたは複数のコレクション[それに続く](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate)構造)。 これら 2 つの構造の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

メニュー リソースが正常に読み込まれている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

メニューのテンプレートは、1 つまたは複数のコレクションに続くヘッダー[それに続く](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate)構造、各メニュー項目とポップアップ メニューの 1 つまたは複数を含めることができます。

バージョン番号は 0 になります。

`mtOption`ポップアップ リストの最後の項目をメイン リストの最後の項目、フラグは mf_end する必要があります。 参照してください、`AppendMenu`のフラグを他のメンバー関数。 `mtId`ならばがで指定した場合、それに続く構造からメンバーを省略する必要があります`mtOption`します。

それに続く構造体は、十分な大きさである必要がありますに割り当てられた領域`mtString`null で終わる文字列としてのメニュー項目の名前を格納します。

終了する前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーションが呼び出すことによって、メニューを解放、 [DestroyMenu](#destroymenu)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

##  <a name="m_hmenu"></a>  CMenu::m_hMenu

アタッチされている Windows メニューの HMENU ハンドルを指定します、`CMenu`オブジェクト。

```
HMENU m_hMenu;
```

### <a name="example"></a>例

  例をご覧ください[CMenu::LoadMenu](#loadmenu)します。

##  <a name="measureitem"></a>  CMenu::MeasureItem

オーナー描画スタイルを持つメニューが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpMeasureItemStruct*<br/>
ポインター、`MEASUREITEMSTRUCT`構造体。

### <a name="remarks"></a>Remarks

既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、 `MEASUREITEMSTRUCT`  メニューのディメンションの Windows に通知する構造体。

参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の説明については、`MEASUREITEMSTRUCT`構造体。

### <a name="example"></a>例

次のコードは、MFC [CTRLTEST](../../overview/visual-cpp-samples.md)サンプル。

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

##  <a name="modifymenu"></a>  CMenu::ModifyMenu

指定された位置にある既存のメニュー項目を変更*照合を n 続行*します。

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

*nPosition*<br/>
変更するメニュー項目を指定します。 *NFlags*の解釈にパラメーターを使用できる*照合を n 続行*次の方法で。

|nFlags|照合を n 続行の解釈|
|------------|---------------------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。|

*nFlags*<br/>
指定する方法*照合を n 続行*は解釈され、メニュー項目に対する変更に関する情報を提供します。 設定できるフラグの一覧は、次を参照してください。、[は](#appendmenu)メンバー関数。

*nIDNewItem*<br/>
変更されたメニュー項目のコマンド ID を指定しますまたは、 *nFlags*ならば、ポップアップ メニューのメニューのハンドル (HMENU) に設定されます。 *NIDNewItem*パラメーターは無視されます (不要) 場合*nFlags* MF_SEPARATOR に設定されます。

*lpszNewItem*<br/>
新しいメニュー項目の内容を指定します。 *NFlags*の解釈にパラメーターを使用できる*lpszNewItem*次の方法で。

|nFlags|LpszNewItem の解釈|
|------------|-----------------------------------|
|MF_OWNERDRAW|アプリケーションは、メニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、MF_MEASUREITEM とが処理するときに、アプリケーションで使用できます。|
|MF_STRING|Null で終わる文字列またはの long ポインターが含まれています、`CString`します。|
|MF_SEPARATOR|*LpszNewItem* (不要) パラメーターは無視されます。|

*pBmp*<br/>
指す、`CBitmap`メニュー項目として使用されるオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションでは、メニュー項目の新しい状態を指定値を設定して*nFlags*します。 この関数に代わるメニュー項目に関連付けられたポップアップ メニューで場合、その古いポップアップ メニューを破棄し、ポップアップ メニューで使用されるメモリを解放します。

ときに*nIDNewItem*ポップアップ メニューを指定しますが挿入されるメニューの一部となります。 メニューが破棄されると、挿入されたメニューも破棄されます。 挿入のメニューからデタッチする必要があります、`CMenu`競合を回避するオブジェクト。

内のメニューに配置されるたびに (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります`CWnd::DrawMenuBar`します。 既存のメニュー項目の属性を変更するには使用する方が速く、`CheckMenuItem`と`EnableMenuItem`メンバー関数。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="operator_hmenu"></a>  CMenu::operator HMENU

この演算子を使用してのハンドルを取得する、`CMenu`オブジェクト。

```
operator HMENU() const;
```

### <a name="return-value"></a>戻り値

成功した場合のハンドル、`CMenu`オブジェクト。 それ以外の場合、NULL。

### <a name="remarks"></a>Remarks

ハンドルを使用して、Windows Api を直接呼び出すことができます。

##  <a name="operator_neq"></a>  CMenu::operator! =

2 つのメニューが論理的に等しいかどうかを決定します。

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
A`CMenu`比較対象のオブジェクト。

### <a name="remarks"></a>Remarks

左側のメニュー オブジェクトが右側にあるメニュー オブジェクトと等しくないかどうかをテストします。

##  <a name="operator_eq_eq"></a>  CMenu::operator = =

2 つのメニューが論理的に等しいかどうかを決定します。

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
A`CMenu`比較対象のオブジェクト。

### <a name="remarks"></a>Remarks

左側にあるメニュー オブジェクトかどうかは、(HMENU 値) の観点から、右側にあるメニュー オブジェクトと等しい。

##  <a name="removemenu"></a>  CMenu::RemoveMenu

メニューから、メニュー項目を関連付けられたポップアップ メニューを削除します。

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*nPosition*<br/>
削除するメニュー項目を指定します。 *NFlags*の解釈にパラメーターを使用できる*照合を n 続行*次の方法で。

|nFlags|照合を n 続行の解釈|
|------------|---------------------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。|

*nFlags*<br/>
指定する方法*照合を n 続行*解釈されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

メニューが再利用できるように、ポップアップ メニューのハンドルは破棄しません。 この関数を呼び出す前に、アプリケーションを呼び出すことができます、`GetSubMenu`ポップアップ ウィンドウを取得するメンバー関数`CMenu`再利用するためのオブジェクト。

内のメニューに配置されるたびに (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります`CWnd::DrawMenuBar`します。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem

指定されたメニューの既定のメニュー項目を設定します。

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*uItem*<br/>
識別子または既定の新しいメニュー項目または 1 のない既定の項目の位置。 このパラメーターの意味は、の値によって異なります。*どの*します。

*どの*<br/>
値の意味を指定する*uItem*します。 このパラメーターが FALSE の場合*uItem*はメニュー項目の識別子です。 それ以外の場合、メニュー項目の位置になります。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は 0 以外の値です。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Win32 関数を使用して[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)」の説明に従って、Windows SDK。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 関数の動作を実装[SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem)」の説明に従って、Windows SDK。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId

コンテキスト ヘルプ ID を関連付けます`CMenu`します。

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>パラメーター

*dwContextHelpId*<br/>
コンテキスト ヘルプの ID に関連付ける`CMenu`します。

### <a name="return-value"></a>戻り値

成功した場合、0 以外の場合それ以外の場合 0

### <a name="remarks"></a>Remarks

メニュー内のすべての項目は、この id を共有: ヘルプ コンテキスト識別子を個々 のメニュー項目にアタッチすることはできません。

### <a name="example"></a>例

  例をご覧ください[CMenu::InsertMenu](#insertmenu)します。

##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo

メニューの情報を設定します。

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>パラメーター

*lpcmi*<br/>
ポインターを[保持](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo)メニューの情報を含む構造体。

### <a name="return-value"></a>戻り値

戻り値は 0 以外の場合は、関数が成功すると、それ以外の場合、戻り値は 0 です。

### <a name="remarks"></a>Remarks

特定のメニューに関する情報を設定するには、この関数を呼び出します。

##  <a name="setmenuitembitmaps"></a>  CMenu::SetMenuItemBitmaps

指定されたビットマップをメニュー項目に関連付けます。

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>パラメーター

*nPosition*<br/>
変更するメニュー項目を指定します。 *NFlags*の解釈にパラメーターを使用できる*照合を n 続行*次の方法で。

|nFlags|照合を n 続行の解釈|
|------------|---------------------------------|
|とき|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 これは、ときでも MF_BYPOSITION が設定されている場合、既定値です。|
|MF_BYPOSITION|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目が 0 の位置です。|

*nFlags*<br/>
指定する方法*照合を n 続行*解釈されます。

*pBmpUnchecked*<br/>
メニュー項目がチェックされていないを使用するビットマップを指定します。

*pBmpChecked*<br/>
オンになっているメニュー項目に使用するビットマップを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

メニュー項目がオンまたはオフの場合、Windows には、メニュー項目の横にある適切なビットマップが表示されます。

いずれか*pBmpUnchecked*または*pBmpChecked*が NULL の場合、Windows では、属性に対応するメニュー項目の横に何も表示されません。 両方のパラメーターが NULL の場合は、Windows は、項目がチェックされ、項目がチェックされている場合にチェック マークが削除時に既定のチェック マークを使用します。

メニューが破棄されると、これらのビットマップは破棄されません。アプリケーションは、それらを破棄する必要があります。

Windows`GetMenuCheckMarkDimensions`関数は、メニュー項目に対して使用される既定のチェック マークの寸法を取得します。 アプリケーションでは、これらの値を使用して、この関数に渡すビットマップの適切なサイズを決定します。 サイズを取得し、ビットマップを作成し、それらを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

##  <a name="setmenuiteminfo"></a>  CMenu::SetMenuItemInfo

メニュー項目に関する情報を変更します。

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>パラメーター

*uItem*<br/>
説明を参照してください。 *uItem*で[SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa) Windows SDK に含まれています。

*lpMenuItemInfo*<br/>
説明を参照してください。 *lpmii*で`SetMenuItemInfo`Windows SDK に含まれています。

*どの*<br/>
説明を参照してください。 *fByPosition*で`SetMenuItemInfo`Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

この関数をラップ[SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa)Windows SDK で説明します。

##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu

指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>パラメーター

*nFlags*<br/>
フラグを画面位置とマウスの位置を指定します。 参照してください[TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu)使用可能なフラグの一覧についてはします。

*x*<br/>
ポップアップ メニューの画面座標の水平方向の位置を指定します。 値に応じて、 *nFlags*パラメーター、メニューは左揃え、右揃え、またはこの位置から見て中央揃えにすることができます。

*y*<br/>
画面のメニューの上部の画面座標の垂直位置を指定します。

*我が物*<br/>
ポップアップ メニューを所有しているウィンドウを識別します。 TPM_NONOTIFY フラグが指定されている場合でも、このパラメーターは null の場合にすることはできません。 このウィンドウは、メニューから、すべての WM_COMMAND メッセージを受信します。 Windows バージョン 3.1 以降で、ウィンドウ メッセージを受信しません WM_COMMAND まで`TrackPopupMenu`を返します。 Windows 3.0 では、ウィンドウは前に、WM_COMMAND メッセージを受け取ります。`TrackPopupMenu`を返します。

*lpRect*<br/>
無視されます。

### <a name="return-value"></a>戻り値

このメソッド呼び出しの結果を返します[TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

浮動小数点のポップアップ メニューは、画面に任意の場所に表示できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx

指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>パラメーター

*fuFlags*<br/>
拡張メニューのさまざまな関数を指定します。 すべての値の一覧とその意味では、次を参照してください。[バインド](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex)します。

*x*<br/>
ポップアップ メニューの画面座標の水平方向の位置を指定します。

*y*<br/>
画面のメニューの上部の画面座標の垂直位置を指定します。

*我が物*<br/>
ポップアップ メニューを所有していると、[作成] メニューから、メッセージの受信ウィンドウへのポインター。 このウィンドウは、現在のアプリケーションからの任意のウィンドウを指定できますが、NULL にすることはできません。 TPM_NONOTIFY を指定する場合、 *fuFlags*パラメーター、関数はすべてのメッセージを送信しません*我が物*します。 によって示されるウィンドウ関数が返す必要があります*我が物*WM_COMMAND メッセージを受信します。

*lptpm*<br/>
ポインターを[TPMPARAMS](/windows/desktop/api/winuser/ns-winuser-tagtpmparams)メニュー画面の領域を指定する構造体が重なり合ってはなりません。 このパラメーターは、NULL を指定できます。

### <a name="return-value"></a>戻り値

TPM_RETURNCMD を指定する場合、 *fuFlags*パラメーター、戻り値は、ユーザーが選択した項目をメニュー項目の識別子。 ユーザーが、選択を行わず、メニューを取り消した場合、またはエラーが発生した場合は、戻り値は 0 です。

TPM_RETURNCMD を指定しない場合、 *fuFlags*パラメーター、戻り値は 0 以外の場合、関数が成功した場合、0、失敗した場合。 拡張エラー情報を取得するには呼び出します[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)します。

### <a name="remarks"></a>Remarks

浮動小数点のポップアップ メニューは、画面に任意の場所に表示できます。 ポップアップ メニューを作成するときのエラー処理の詳細については、次を参照してください。[バインド](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex)します。

## <a name="see-also"></a>関連項目

[MFC サンプル CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル DYNAMENU](../../overview/visual-cpp-samples.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)
