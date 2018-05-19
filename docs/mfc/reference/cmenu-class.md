---
title: CMenu クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64682066a93618c8646973c76df395883dddf053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CMenu::Attach](#attach)|Windows メニュー ハンドルをアタッチ、`CMenu`オブジェクト。|  
|[CMenu::CheckMenuItem](#checkmenuitem)|横にチェック マークを挿入またはポップアップ メニューのメニュー項目から、チェック マークを削除します。|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|メニュー項目の横にあるラジオ ボタンを配置し、すべてのグループ内の他のメニュー項目から、ラジオ ボタンを削除します。|  
|[CMenu::CreateMenu](#createmenu)|空のメニューを作成し、それにアタッチ、`CMenu`オブジェクト。|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|空のポップアップ メニューを作成し、それにアタッチ、`CMenu`オブジェクト。|  
|[なる](#deletemenu)|メニューから、指定した項目を削除します。 メニュー項目に関連付けられたポップアップ メニューがある場合は、ポップアップ メニューへのハンドルを破棄し、それによって使用されるメモリを解放します。|  
|[CMenu::DeleteTempMap](#deletetempmap)|一時的な削除`CMenu`によって作成されたオブジェクト、`FromHandle`メンバー関数。|  
|[メニューを破棄](#destroymenu)|接続されているメニューの破棄、`CMenu`オブジェクトし、メニューが占有されているメモリを解放します。|  
|[CMenu::Detach](#detach)|Windows メニューのハンドルをデタッチ、`CMenu`オブジェクトおよびハンドルを返します。|  
|[CMenu::DrawItem](#drawitem)|オーナー描画メニュー変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CMenu::EnableMenuItem](#enablemenuitem)|淡色表示 (灰色) を有効、無効化、またはメニュー項目。|  
|[CMenu::FromHandle](#fromhandle)|ポインターを返します、 `CMenu` Windows メニューのハンドルを指定されたオブジェクト。|  
|[CMenu::GetDefaultItem](#getdefaultitem)|指定されたメニューの既定のメニュー項目を決定します。|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|メニューに関連付けられているヘルプ コンテキスト ID を取得します。|  
|[CMenu::GetMenuInfo](#getmenuinfo)|特定のメニューに関する情報を取得します。|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|ポップアップまたはトップレベルのメニュー内の項目数を決定します。|  
|[CMenu::GetMenuItemID](#getmenuitemid)|指定した位置にあるメニュー項目のメニュー項目の識別子を取得します。|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|メニュー項目に関する情報を取得します。|  
|[CMenu::GetMenuState](#getmenustate)|ポップアップ メニューで、指定されたメニュー項目または項目の数の状態を返します。|  
|[CMenu::GetMenuString](#getmenustring)|指定されたメニュー項目のラベルを取得します。|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|返します、`m_hMenu`これによってラップされた`CMenu`オブジェクト。|  
|[CMenu::GetSubMenu](#getsubmenu)|ポップアップ メニューへのポインターを取得します。|  
|[CMenu::InsertMenu](#insertmenu)|メニューの他の項目の移動で指定した位置に新しいメニュー項目を挿入します。|  
|[CMenu::InsertMenuItem](#insertmenuitem)|メニュー内の指定位置に新しいメニュー項目を挿入します。|  
|[CMenu::LoadMenu](#loadmenu)|実行可能ファイルからメニュー リソースを読み込みにアタッチ、`CMenu`オブジェクト。|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|メモリ内のメニュー テンプレートから、メニューを読み込んでにアタッチ、`CMenu`オブジェクト。|  
|[CMenu::MeasureItem](#measureitem)|オーナー描画メニューが作成されるときに、メニューの大きさを調べるためにフレームワークによって呼び出されます。|  
|[CMenu::ModifyMenu](#modifymenu)|指定した位置にある既存のメニュー項目を変更します。|  
|[CMenu::RemoveMenu](#removemenu)|指定されたメニューから、関連付けられたポップアップ メニューにメニュー項目を削除します。|  
|[CMenu::SetDefaultItem](#setdefaultitem)|指定されたメニューの既定のメニュー項目を設定します。|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|メニューと関連するヘルプ コンテキスト ID を設定します。|  
|[CMenu::SetMenuInfo](#setmenuinfo)|特定のメニューに関する情報を設定します。|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|指定されたチェック マークのビットマップをメニュー項目に関連付けます。|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|メニュー項目に関する情報を変更します。|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択肢を追跡します。|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択肢を追跡します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|メニュー オブジェクトのハンドルを取得します。|  
|[CMenu::operator! =](#operator_neq)|2 つのメニュー オブジェクトが等しくないかどうかを判断します。|  
|[CMenu::operator = =](#operator_eq_eq)|2 つのメニュー オブジェクトが等しいかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|接続されている Windows メニューへのハンドルを指定します、`CMenu`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 メンバー関数を作成する、追跡、更新、およびメニューの破棄を提供します。  
  
 作成、`CMenu`オブジェクトとして、ローカルのスタック フレームに呼び出して`CMenu`の必要に応じて、新しいメニューを操作するメンバー関数。 次に、呼び出す[CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu)に設定する、メニュー、ウィンドウをすぐに続くことへの呼び出しによって、`CMenu`オブジェクトの[デタッチ](#detach)メンバー関数。 `CWnd::SetMenu`メンバー関数は、新しいメニューに、ウィンドウのメニューを設定、メニューの変更を反映するように再描画されるウィンドウ発生して、メニューの所有権をウィンドウにも渡します。 呼び出し**デタッチ**デタッチ、`HMENU`から、`CMenu`オブジェクト、そのときにローカル`CMenu`変数がスコープから外れたが渡されます、`CMenu`メニューを破棄するオブジェクトのデストラクターは行われません、なし現在所有しています。 ウィンドウが破棄されるときに、メニュー自体が自動的に破棄されます。  
  
 使用することができます、 [LoadMenuIndirect](#loadmenuindirect)メンバー関数を作成、メモリ内テンプレートからのメニューがメニューへの呼び出しによってリソースから作成する[LoadMenu](#loadmenu)はより簡単に保持されると、メニュー リソースそれ自体作成し、メニュー エディターで変更できます。  
  
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
 `nFlags`  
 メニューに追加されたときに、新しいメニュー項目の状態に関する情報を指定します。 「解説」セクションに示された値の 1 つ以上で構成されます。  
  
 `nIDNewItem`  
 新しいメニュー項目のコマンド ID を指定または、`nFlags`に設定されている**ならば**、メニューのハンドル ( `HMENU`) ポップアップ メニューのです。 `nIDNewItem`パラメーターは無視されます (必要ではない) 場合`nFlags`に設定されている**MF_SEPARATOR**です。  
  
 `lpszNewItem`  
 新しいメニュー項目の内容を指定します。 `nFlags`を解釈するパラメーターが使用される`lpszNewItem`次のようにします。  
  
|nFlags|LpszNewItem の解釈|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|アプリケーションは、メニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、処理するときに、アプリケーションで使用できる`WM_MEASUREITEM`と`WM_DRAWITEM`メッセージ。 値が格納されている、**取得**これらのメッセージで指定された構造体のメンバーです。|  
|**MF_STRING**|Null で終わる文字列へのポインターが含まれています。 これは、既定の解釈です。|  
|**MF_SEPARATOR**|`lpszNewItem` (必要ないため) パラメーターは無視されます。|  
  
 *pBmp*  
 指す、`CBitmap`メニュー項目として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションで値を設定して、メニュー項目の状態を指定できます`nFlags`です。 ときに`nIDNewItem`ポップアップ メニューを指定しますが追加されます メニューの一部となります。 メニューが破棄される場合、追加したメニューも破棄されます。 追加したメニューからデタッチする必要があります、`CMenu`競合を回避するオブジェクト。 なお**MF_STRING**と`MF_OWNERDRAW`のビットマップのバージョンが無効な`AppendMenu`します。  
  
 次のとおりに設定できるフラグ`nFlags`:  
  
- **MF_CHECKED** で切り替えを果たします**MF_UNCHECKED**アイテムの横にある既定のチェック ボックスをオンにします。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、 [SetMenuItemBitmaps](#setmenuitembitmaps)メンバー関数)、「にチェック マーク」ビットマップが表示されます。  
  
- **MF_UNCHECKED**で切り替えを果たします**を**項目の横にチェック ボックスをオフにします。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「チェック マークをオフ」ビットマップが表示されます。  
  
- **MF_DISABLED**が無効になり、メニュー項目は選択できませんが、淡色表示にしません。  
  
- `MF_ENABLED` 選択することができ、グレーの状態から復元できるようには、メニュー項目を有効にします。  
  
- **MF_GRAYED**選択することはできませんし、淡色表示にするように、メニュー項目を無効にします。  
  
- **MF_MENUBARBREAK**静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 新しいポップアップ メニュー列は、垂直方向の区切り線によって、古い列から分離されます。  
  
- **MF_MENUBREAK**静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 列の間の区切り線は配置されません。  
  
- `MF_OWNERDRAW` 項目がオーナー描画項目であることを指定します。 メニューを所有するウィンドウを受け取りますが最初に、メニューが表示されたら、`WM_MEASUREITEM`メニュー項目の幅と高さを取得するメッセージ。 `WM_DRAWITEM`メッセージが 1 つの所有者は、メニュー項目の表示を更新する必要がありますたびに送信されます。 このオプションは、トップレベルのメニュー項目に対して有効ではできません。  
  
- **ならば**メニュー項目に関連付けられているポップアップ メニューがあることを指定します。 ID パラメーターは、ポップアップ メニュー項目に関連付けられるへのハンドルを指定します。 ポップアップ メニュー項目に、トップレベルのポップアップ メニューまたは階層的なポップアップ メニューを追加するために使用されます。  
  
- **MF_SEPARATOR**水平分割線を描画します。 ポップアップ メニューでのみ使用できます。 この行は、淡色表示されている、無効化、または強調表示されていることはできません。 その他のパラメーターは無視されます。  
  
- **MF_STRING**メニュー項目を文字の文字列に指定します。  
  
 次のグループのそれぞれは相互に排他的と一緒に使用できないフラグが一覧表示します。  
  
- **MF_DISABLED**、 `MF_ENABLED`、および**MF_GRAYED**  
  
- **MF_STRING**、 `MF_OWNERDRAW`、 **MF_SEPARATOR**、およびビットマップ バージョン  
  
- **MF_MENUBARBREAK**と**MF_MENUBREAK**  
  
- **MF_CHECKED** と**MF_UNCHECKED**  
  
 (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります内に存在するメニューたびに[かかわらず](../../mfc/reference/cwnd-class.md#drawmenubar)です。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::CreateMenu](#createmenu)です。  
  
##  <a name="attach"></a>  CMenu::Attach  
 アタッチに既存の Windows メニュー、`CMenu`オブジェクト。  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 Windows メニューへのハンドルを指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューに既にアタッチされている場合、この関数を呼び出すことはできません、`CMenu`オブジェクト。 メニューのハンドルに格納されている、`m_hMenu`データ メンバーです。  
  
 使用することができますを操作するメニューが既にウィンドウに関連付けられている場合、[とき](../../mfc/reference/cwnd-class.md#getmenu)メニューへのハンドルを取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem  
 チェック マークを追加またはポップアップ メニューのメニュー項目からチェック マークを削除します。  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCheckItem`  
 によって決定されたようにチェックするメニュー項目を指定`nCheck`です。  
  
 `nCheck`  
 メニュー項目を確認する方法と、メニュー内の項目の位置を確認する方法を指定します。 `nCheck`パラメーターの組み合わせを指定できます**を**または**MF_UNCHECKED**で**MF_BYPOSITION**または**とき**フラグです。 これらのフラグは、ビットごとの OR 演算子を使用して組み合わせることができます。 次の意味があります。  
  
- **とき**パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値です。  
  
- **MF_BYPOSITION**パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。  
  
- **MF_CHECKED** で切り替えを果たします**MF_UNCHECKED**アイテムの横にある既定のチェック ボックスをオンにします。  
  
- **MF_UNCHECKED**で切り替えを果たします**を**項目の横にチェック ボックスをオフにします。  
  
### <a name="return-value"></a>戻り値  
 項目の以前の状態:**を**または**MF_UNCHECKED**、またはメニュー項目が存在しなかった場合に 0 xffffffff です。  
  
### <a name="remarks"></a>コメント  
 `nIDCheckItem`パラメーターを変更する項目を指定します。  
  
 `nIDCheckItem`パラメーターがメニュー項目と同様に、ポップアップ メニュー項目に見つかる場合があります。 ポップアップ メニュー項目をチェックする特別な手順は必要ありません。 トップレベルのメニュー項目をチェックすることはできません。 関連付けられたメニュー項目の識別子がないために、位置でポップアップ メニュー項目をチェックする必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::GetMenuState](#getmenustate)です。  
  
##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem  
 指定されたメニュー項目をチェックし、オプションの項目を使用します。  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirst`  
 指定します (ID またはの値に応じて、オフセットと`nFlags`) ラジオ ボタン グループの最初のメニュー項目。  
  
 `nIDLast`  
 指定します (ID またはの値に応じて、オフセットと`nFlags`) ラジオ ボタン グループの最後のメニュー項目。  
  
 `nIDItem`  
 指定します (ID またはの値に応じて、オフセットと`nFlags`)、オプション ボタンとチェックされる、グループ内の項目。  
  
 `nFlags`  
 解釈を指定`nIDFirst`、 `nIDLast`、および`nIDItem`次のようにします。  
  
|nFlags|解釈|  
|------------|--------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合 0  
  
### <a name="remarks"></a>コメント  
 同時に、関数は、関連付けられているグループ内の他のすべてのメニュー項目をオフにし、それらの項目の選択項目型のフラグをクリアします。 チェック マークのビットマップではなく、ラジオ ボタン (または行頭文字) のビットマップを使用してチェックされている項目が表示されます。  
  
### <a name="example"></a>例  
  例を参照して[ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)です。  
  
##  <a name="cmenu"></a>  CMenu::CMenu  
 空のメニューを作成し、それにアタッチ、`CMenu`オブジェクト。  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>コメント  
 作成または読み込みのメンバー関数の 1 つを呼び出すまで、メニューは作成されません**CMenu:**  
  
- [CreateMenu](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [添付](#attach)  
  
##  <a name="createmenu"></a>  CMenu::CreateMenu  
 メニューを作成し、それにアタッチ、`CMenu`オブジェクト。  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>戻り値  
 メニューが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューは、最初は空です。 使用してメニュー項目を追加することができます、`AppendMenu`または`InsertMenu`メンバー関数。  
  
 メニューがウィンドウに割り当てられている場合、ウィンドウが破棄されるときに自動的に破棄されます。  
  
 、終了する前に、アプリケーションは、ウィンドウ、メニューが割り当てられていない場合に、メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu  
 ポップアップ メニューを作成し、それにアタッチ、`CMenu`オブジェクト。  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニューが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューは、最初は空です。 使用してメニュー項目を追加することができます、`AppendMenu`または`InsertMenu`メンバー関数。 アプリケーションは、既存のメニューまたはポップアップ メニューに、ポップアップ メニューを追加できます。 `TrackPopupMenu`フローティング ポップアップ メニューとしてこのメニューを表示して、ポップアップ メニューで選択内容を追跡するために、メンバー関数を使用する可能性があります。  
  
 メニューがウィンドウに割り当てられている場合、ウィンドウが破棄されるときに自動的に破棄されます。 既存のメニューにメニューを追加すると場合、そのメニューが破棄されるときに自動的に破棄されます。  
  
 、終了する前に、アプリケーションは、ウィンドウに、メニューが割り当てられていない場合、ポップアップ メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::CreateMenu](#createmenu)です。  
  
##  <a name="deletemenu"></a>  なる  
 メニュー項目を削除します。  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 によって決定されたように、削除するのにはメニュー項目を指定`nFlags`です。  
  
 `nFlags`  
 解釈に使用される`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー項目が関連付けられているなポップアップ メニューでは、`DeleteMenu`ポップアップ メニューへのハンドルを破棄し、ポップアップ メニューで使用されるメモリを解放します。  
  
 (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります内に存在するメニューたびに[かかわらず](../../mfc/reference/cwnd-class.md#drawmenubar)です。  
  
### <a name="example"></a>例  
  例を参照して[とき](../../mfc/reference/cwnd-class.md#getmenu)です。  
  
##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap  
 によって自動的に呼び出されます、`CWinApp`アイドル処理ハンドラーを削除、一時`CMenu`によって作成されたオブジェクト、 [FromHandle](#fromhandle)メンバー関数。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>コメント  
 `DeleteTempMap` 一時的に接続されている Windows メニュー オブジェクトをデタッチ`CMenu`オブジェクトを削除する前に、`CMenu`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>  メニューを破棄  
 メニューと使用されている Windows のシステム リソースを破棄します。  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>戻り値  
 メニューが破棄された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューをデタッチ、`CMenu`オブジェクトが破棄される前にします。 Windows`DestroyMenu`関数自動的に、`CMenu`デストラクターです。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::CreateMenu](#createmenu)です。  
  
##  <a name="detach"></a>  CMenu::Detach  
 Windows メニューからのデタッチ、`CMenu`オブジェクトおよびハンドルを返します。  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>戻り値  
 型のハンドル`HMENU`、それ以外の成功した場合は、Windows メニューに**NULL**です。  
  
### <a name="remarks"></a>コメント  
 `m_hMenu`データ メンバーに設定されている**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>  CMenu::DrawItem  
 オーナー描画メニュー変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 `itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CMenu`オブジェクト。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`このメンバー関数の終了前にします。  
  
 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)の詳細については、`DRAWITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 次のコードは、MFC [CTRLTEST](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>  CMenu::EnableMenuItem  
 有効、無効化、またはメニュー項目を使用できなくなります。  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDEnableItem*  
 によって決定される、有効にするメニュー項目を指定`nEnable`です。 このパラメーターには、標準のメニュー項目だけでなく、ポップアップ メニュー項目を指定できます。  
  
 `nEnable`  
 実行するアクションを指定します。 組み合わせであることができます**MF_DISABLED**、 `MF_ENABLED`、または**MF_GRAYED**で**とき**または**MF_BYPOSITION**です。 これらの値は、ビットごとの OR 演算子を使用して組み合わせることができます。 これらの値には、次の意味があります。  
  
- **とき**パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値です。  
  
- **MF_BYPOSITION**パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。  
  
- **MF_DISABLED**が無効になり、メニュー項目は選択できませんが、淡色表示にしません。  
  
- `MF_ENABLED` 選択することができ、グレーの状態から復元できるようには、メニュー項目を有効にします。  
  
- **MF_GRAYED**選択することはできませんし、淡色表示にするように、メニュー項目を無効にします。  
  
### <a name="return-value"></a>戻り値  
 以前の状態 ( **MF_DISABLED**、 `MF_ENABLED`、または**MF_GRAYED**) または有効でない場合は-1。  
  
### <a name="remarks"></a>コメント  
 [CreateMenu](#createmenu)、[項目](#insertmenu)、[メニュー](#modifymenu)、および[LoadMenuIndirect](#loadmenuindirect)メンバー関数は、(有効になっている、状態にも設定できます淡色表示されているか、無効に) のメニュー項目。  
  
 使用して、 **MF_BYPOSITION**値には、正しいを使用するアプリケーションが必要です。`CMenu`です。 場合、 `CMenu`  メニューのバーを使用すると、トップレベルのメニュー項目 (メニュー バーのアイテム) が影響を受けます。 位置でポップアップまたは入れ子になったポップアップ メニューの項目の状態を設定する、アプリケーションで指定する必要があります、`CMenu`ポップアップ メニューのです。  
  
 指定されている場合、アプリケーション、**とき**フラグは、Windows は下にあるすべてのポップアップ メニュー項目を確認、`CMenu`ですそのため、重複するメニュー項目が存在しない限り、を使用して、 `CMenu` 、メニュー バーの。十分なです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CMenu::FromHandle  
 ポインターを返します、`CMenu`メニューへの Windows ハンドルを指定するオブジェクト。  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 メニューへの Windows ハンドル。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMenu`一時的または永続する可能性があります。  
  
### <a name="remarks"></a>コメント  
 場合、 `CMenu` Windows メニュー オブジェクト、一時的なにオブジェクトが既にアタッチされていない`CMenu`オブジェクトが作成され、接続されています。  
  
 この一時`CMenu`オブジェクトは、次に、アプリケーションが、すべての一時オブジェクトの削除時に、イベント ループのアイドル時間までのみ有効です。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::CreateMenu](#createmenu)です。  
  
##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem  
 指定されたメニューの既定のメニュー項目を決定します。  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *gmdiFlags*  
 関数がメニュー項目を検索する方法を指定する値。 このパラメーターには、なし、1 つ、または、次の値の組み合わせを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|、既定の項目のいずれかのサブメニューを開く場合、関数がある、対応するサブメニューを再帰的に検索するを指定します。 サブメニューには、既定の項目がなければ、戻り値は、サブメニューを開く項目を識別します。<br /><br /> 既定では、サブメニューを開く項目であるかどうかに関係なく、指定されたメニューの最初の既定の項目を返します。|  
|**GMDI_USEDISABLED**|関数は、無効になっている場合でも、既定の項目を返すにを指定します。<br /><br /> 既定では、関数は、無効または淡色表示の項目をスキップします。|  
  
 `fByPos`  
 メニュー項目の識別子またはの位置を取得するかどうかを指定する値。 このパラメーターが場合**FALSE**識別子が返されます。 それ以外の場合、位置が返されます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、識別子またはメニュー項目の位置。 関数が失敗した場合、戻り値は - 1 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 関数の動作を実装して[GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId  
 ID に関連付けられているコンテキスト ヘルプを取得`CMenu`です。  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ID が現在関連付けられているコンテキスト ヘルプ`CMenu`; いずれかがある場合は 0 それ以外の場合。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo  
 メニューの情報を取得します。  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcmi`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/ms647575)メニューの情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 戻り値は 0 以外です。 関数が成功した場合それ以外の場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数では、メニューに関する情報を取得します。  
  
##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount  
 ポップアップまたはトップレベルのメニュー内の項目数を決定します。  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、メニュー内の項目数それ以外の場合は-1。  
  
### <a name="example"></a>例  
  例を参照して[とき](../../mfc/reference/cwnd-class.md#getmenu)です。  
  
##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID  
 によって定義される位置にあるメニュー項目のメニュー項目の識別子を取得`nPos`です。  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 位置 (0 から始まる) のメニュー項目の ID を取得するを指定します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合に、ポップアップ メニューで指定された項目の項目の ID。 指定した項目が (ポップアップ メニュー内の項目) ではなくポップアップ メニューの場合は、戻り値は-1 です。 場合`nPos`に対応する、**区切り**メニュー項目、戻り値は 0 です。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo  
 メニュー項目に関する情報を取得します。  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 識別子またはに関する情報を取得するメニュー項目の位置。 このパラメーターの意味は、の値によって異なります。`ByPos`です。  
  
 `lpMenuItemInfo`  
 ポインター、 [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578)メニューに関する情報を含む Windows SDK で説明されている。  
  
 `fByPos`  
 値の意味を指定する`nIDItem`です。 既定では、`ByPos`は**FALSE**では、メニュー項目の識別子。 場合`ByPos`に設定されていない**FALSE**、メニュー項目の位置を示します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は 0 以外の値です。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Win32 関数を使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)Windows SDK で説明されている。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の動作を実装して、Win32 関数の[GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980)Windows SDK で説明されている。 MFC 実装では、ことに注意してください。 `GetMenuItemInfo`、メニューへのハンドルを使用しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>  CMenu::GetMenuState  
 ポップアップ メニューで、指定されたメニュー項目または項目の数の状態を返します。  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 によって決定されたように、メニュー項目の ID を指定`nFlags`です。  
  
 `nFlags`  
 性質を示す`nID`です。 次の値のいずれかを指定できます。  
  
- **とき**パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値です。  
  
- **MF_BYPOSITION**パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。  
  
### <a name="return-value"></a>戻り値  
 値が指定した項目が存在しない場合に 0 xffffffff です。 場合*nId*識別ポップアップ メニューでは、高位バイトは、ポップアップ メニューの項目の数を表すし、下位バイトがポップアップ メニューに関連付けられたメニュー フラグを格納します。 戻り値は次の一覧から値のマスク (論理 OR) をそれ以外の場合 (このマスクは、メニューの状態を説明する項目*nId*を識別)。  
  
- **MF_CHECKED** で切り替えを果たします**MF_UNCHECKED**アイテムの横にある既定のチェック ボックスをオンにします。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「にチェック マーク」ビットマップが表示されます。  
  
- **MF_DISABLED**が無効になり、メニュー項目は選択できませんが、淡色表示にしません。  
  
- `MF_ENABLED` 選択することができ、グレーの状態から復元できるようには、メニュー項目を有効にします。 この定数の値は 0 になります。この値を使用する場合、アプリケーションのテストは 0 を返します対象いない必要があります。  
  
- **MF_GRAYED**選択することはできませんし、淡色表示にするように、メニュー項目を無効にします。  
  
- **MF_MENUBARBREAK**静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 新しいポップアップ メニュー列は、垂直方向の区切り線によって、古い列から分離されます。  
  
- **MF_MENUBREAK**静的なメニューまたはポップアップ メニューに新しい列に新しい行にアイテムを配置します。 列の間の区切り線は配置されません。  
  
- **MF_SEPARATOR**水平分割線を描画します。 ポップアップ メニューでのみ使用できます。 この行は、淡色表示されている、無効化、または強調表示されていることはできません。 その他のパラメーターは無視されます。  
  
- **MF_UNCHECKED**で切り替えを果たします**を**項目の横にチェック ボックスをオフにします。 アプリケーションでチェック マークのビットマップを提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「チェック マークをオフ」ビットマップが表示されます。 この定数の値は 0 になります。この値を使用する場合、アプリケーションのテストは 0 を返します対象いない必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>  CMenu::GetMenuString  
 指定されたメニュー項目のラベルを指定したバッファーにコピーします。  
  
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
 `nIDItem`  
 値に応じて、メニューにメニュー項目の整数識別子またはメニュー項目のオフセットを指定`nFlags`です。  
  
 `lpString`  
 ラベルを受け取るバッファーへのポインター。  
  
 `rString`  
 参照、`CString`をコピーしたメニュー文字列を受け取るオブジェクト。  
  
 `nMaxCount`  
 コピーするラベルの文字) 単位で最大長を指定します。 指定された最大値よりも長い場合は、ラベル`nMaxCount`、余分な文字は切り捨てられます。  
  
 `nFlags`  
 解釈を指定します、`nIDItem`パラメーター。 次の値のいずれかを指定できます。  
  
|nFlags|NIDItem の解釈|  
|------------|-------------------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
### <a name="return-value"></a>戻り値  
 実際、null 終端文字を含まない、バッファーにコピーされた文字数を指定します。  
  
### <a name="remarks"></a>コメント  
 `nMaxCount`パラメーターは、文字列の終端の null 文字に対応するラベルの文字数を超えるのいずれかにする必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu  
 返します、`HMENU`これによってラップされた`CMenu`オブジェクト、または**NULL** `CMenu`ポインター。  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>例  
  例を参照して[CMenu::LoadMenu](#loadmenu)です。  
  
##  <a name="getsubmenu"></a>  CMenu::GetSubMenu  
 取得、`CMenu`ポップアップ メニューのオブジェクト。  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 メニューに含まれるポップアップ メニューの位置を指定します。 位置の値は、最初のメニュー項目の 0 から始まります。 ポップアップ メニューの識別子は、この関数では使用できません。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMenu`オブジェクト`m_hMenu`メンバーは、ポップアップ メニューが指定された位置に存在する場合に、ポップアップ メニューへのハンドルを含むそれ以外の場合**NULL**です。 場合、`CMenu`オブジェクトが存在しません、その一時的なが作成されます。 `CMenu`返されたポインターを格納いない必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::TrackPopupMenu](#trackpopupmenu)です。  
  
##  <a name="insertmenu"></a>  CMenu::InsertMenu  
 指定された位置に新しいメニュー項目を挿入`nPosition`し、メニューの他の項目を移動します。  
  
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
 `nPosition`  
 位置の前に、新しいメニュー項目を挿入するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用することができます`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。 場合`nPosition`-1 で、新しいメニュー項目は、メニューの末尾に追加されます。|  
  
 `nFlags`  
 指定方法`nPosition`は解釈され、メニューに追加されたときに、新しいメニュー項目の状態に関する情報を指定します。 設定できるは、フラグの一覧は、次を参照してください。、[は](#appendmenu)メンバー関数。 1 つ以上の値を指定するとそれらを結合するビットごとの OR 演算子を使用して、**とき**または**MF_BYPOSITION**フラグ。  
  
 `nIDNewItem`  
 新しいメニュー項目のコマンド ID を指定または、`nFlags`に設定されている**ならば**、メニューのハンドル ( `HMENU`) ポップアップ メニューのです。 `nIDNewItem`パラメーターは無視されます (必要ではない) 場合`nFlags`に設定されている**MF_SEPARATOR**です。  
  
 `lpszNewItem`  
 新しいメニュー項目の内容を指定します。 `nFlags` 解釈に使用できる`lpszNewItem`次のようにします。  
  
|nFlags|LpszNewItem の解釈|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|アプリケーションは、メニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、アプリケーションに使用できる、**取得**によって提供される構造体のメンバー、[よう](http://msdn.microsoft.com/library/windows/desktop/bb775925)と[WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923)メッセージ。 メニュー項目を最初に表示または変更されたときに、これらのメッセージが送信されます。|  
|**MF_STRING**|Null で終わる文字列への long ポインターが含まれています。 これは、既定の解釈です。|  
|**MF_SEPARATOR**|`lpszNewItem` (必要ないため) パラメーターは無視されます。|  
  
 *pBmp*  
 指す、`CBitmap`メニュー項目として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションで値を設定して、メニュー項目の状態を指定できます`nFlags`です。  
  
 (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります内に存在するメニューたびに`CWnd::DrawMenuBar`です。  
  
 ときに`nIDNewItem`ポップアップ メニューを指定しますが挿入 メニューの一部となります。 メニューが破棄される場合は、挿入されたメニューも破棄されます。 挿入メニューはからデタッチする必要があります、`CMenu`競合を回避するオブジェクト。  
  
 マルチ ドキュメント インターフェイス (MDI) 子ウィンドウを最大化、アクティブとアプリケーションは、MDI アプリケーションのメニューに、ポップアップ メニューを指定してこの関数を呼び出すことによって挿入される場合、 **MF_BYPOSITION**フラグは、メニューが挿入されます1 つの位置よりも左に予想よりもします。 これは、アクティブな MDI 子ウィンドウのコントロールのメニューが MDI フレーム ウィンドウのメニュー バーの最初の位置に挿入されるために発生します。 メニューを正しく配置するには、アプリケーションは、それ以外の場合に使用される位置の値に 1 を追加する必要があります。 アプリケーションで使用できます、 **WM_MDIGETACTIVE**メッセージを現在アクティブな子ウィンドウを最大化するかどうかを判断します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>  CMenu::InsertMenuItem  
 メニュー内の指定位置に新しいメニュー項目を挿入します。  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 説明を参照してください`uItem`で[InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) Windows SDK に含まれています。  
  
 `lpMenuItemInfo`  
 説明を参照してください`lpmii`で**InsertMenuItem** Windows SDK に含まれています。  
  
 `fByPos`  
 説明を参照してください`fByPosition`で**InsertMenuItem** Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 この関数をラップ[InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988)Windows SDK に記述されている。  
  
##  <a name="loadmenu"></a>  CMenu::LoadMenu  
 メニュー リソースをアプリケーションの実行可能ファイルから読み込んでにアタッチ、`CMenu`オブジェクト。  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 読み込む] メニューの [リソースの名前を表す null で終わる文字列へのポインター。  
  
 `nIDResource`  
 読み込むメニュー リソースのメニュー ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースが正常に読み込まれた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 、終了する前に、アプリケーションは、ウィンドウ、メニューが割り当てられていない場合に、メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect  
 メモリ内のメニュー テンプレートからリソースを読み込みにアタッチ、`CMenu`オブジェクト。  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMenuTemplate*  
 メニューのテンプレートを指します (これは、1 つ[MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583)構造と、1 つまたは複数のコレクション[それに続く](http://msdn.microsoft.com/library/windows/desktop/ms647581)構造体)。 これら 2 つの構造体の詳細については、Windows SDK を参照してください。  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースが正常に読み込まれた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューのテンプレートは、1 つまたは複数のコレクションでの後にヘッダー[それに続く](http://msdn.microsoft.com/library/windows/desktop/ms647581)構造、メニュー項目とポップアップ メニューの 1 つ以上の場合があります。  
  
 バージョン番号は 0 を指定する必要があります。  
  
 **MtOption**フラグを含める必要があります**MF_END**ポップアップ リストの最後の項目とメインのリストの最後の項目。 参照してください、`AppendMenu`メンバー関数の他のフラグ。 **MtId**からメンバーを省略する必要があります、**それに続く**ときに構造体**ならば**で指定された**mtOption**です。  
  
 割り当てられた領域、**それに続く**構造体は、十分な大きさにする必要があります**mtString** null で終わる文字列としてのメニュー項目の名前を格納します。  
  
 、終了する前に、アプリケーションは、ウィンドウ、メニューが割り当てられていない場合に、メニューに関連付けられたシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>  CMenu::m_hMenu  
 指定します、`HMENU`にアタッチされている Windows メニューのハンドル、`CMenu`オブジェクト。  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>例  
  例を参照して[CMenu::LoadMenu](#loadmenu)です。  
  
##  <a name="measureitem"></a>  CMenu::MeasureItem  
 オーナー描画スタイルを持つメニューが作成されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMeasureItemStruct`  
 ポインター、`MEASUREITEMSTRUCT`構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数では何も行いません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`構造、メニューのディメンションの Windows に通知します。  
  
 参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の詳細については、`MEASUREITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 次のコードは、MFC [CTRLTEST](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>  CMenu::ModifyMenu  
 指定された位置にある既存のメニュー項目を変更`nPosition`です。  
  
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
 `nPosition`  
 変更するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用することができます`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
 `nFlags`  
 指定方法`nPosition`は解釈され、メニュー項目に対して行う変更について説明します。 設定できるのフラグの一覧は、次を参照してください。、[は](#appendmenu)メンバー関数。  
  
 `nIDNewItem`  
 変更されたメニュー項目のコマンド ID を指定または、`nFlags`に設定されている**ならば**、メニューのハンドル ( `HMENU`) ポップアップ メニューのです。 `nIDNewItem`パラメーターは無視されます (必要ではない) 場合`nFlags`に設定されている**MF_SEPARATOR**です。  
  
 `lpszNewItem`  
 新しいメニュー項目の内容を指定します。 `nFlags`の解釈にパラメーターを使用することができます`lpszNewItem`次のようにします。  
  
|nFlags|LpszNewItem の解釈|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|アプリケーションは、メニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、処理するときに、アプリケーションで使用できる**MF_MEASUREITEM**と**が**です。|  
|**MF_STRING**|Null で終わる文字列をまたはの long ポインターが含まれています、`CString`です。|  
|**MF_SEPARATOR**|`lpszNewItem` (必要ないため) パラメーターは無視されます。|  
  
 *pBmp*  
 指す、`CBitmap`メニュー項目として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、メニュー項目の新しい状態を指定値を設定して`nFlags`です。 この関数には、メニュー項目に関連付けられたポップアップ メニューが置き換え場合、に、古いポップアップ メニューを破棄し、ポップアップ メニューで使用されるメモリを解放します。  
  
 ときに`nIDNewItem`ポップアップ メニューを指定しますが挿入 メニューの一部となります。 メニューが破棄される場合は、挿入されたメニューも破棄されます。 挿入メニューはからデタッチする必要があります、`CMenu`競合を回避するオブジェクト。  
  
 (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります内に存在するメニューたびに`CWnd::DrawMenuBar`です。 既存のメニュー項目の属性を変更するには使用する方が速く、`CheckMenuItem`と`EnableMenuItem`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="operator_hmenu"></a>  CMenu::operator HMENU  
 この演算子のハンドルの取得を使用して、`CMenu`オブジェクト。  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合のハンドル、`CMenu`オブジェクト。 それ以外の場合、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 Windows Api を直接呼び出すために、ハンドルを使用することができます。  
  
##  <a name="operator_neq"></a>  CMenu::operator! =  
 2 つのメニューが等しく論理的にないかどうかを判断します。  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `menu`  
 A`CMenu`比較対象のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 左側のメニュー オブジェクトが右側にあるメニュー オブジェクトと等しくないかどうか。  
  
##  <a name="operator_eq_eq"></a>  CMenu::operator = =  
 2 つのメニューが論理的に等しいかどうかを決定します。  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `menu`  
 A`CMenu`比較対象のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 左側のメニュー オブジェクトが等しいかどうか (の観点で、`HMENU`値) の右側にあるメニュー オブジェクトにします。  
  
##  <a name="removemenu"></a>  CMenu::RemoveMenu  
 メニューから、関連付けられたポップアップ メニューにメニュー項目を削除します。  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 削除するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用することができます`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
 `nFlags`  
 指定方法`nPosition`は解釈されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューが再利用できるように、ポップアップ メニューのハンドルは破棄しません。 この関数を呼び出す前に、アプリケーションを呼び出すことがあります、`GetSubMenu`ポップアップを取得するメンバー関数`CMenu`再利用するためのオブジェクト。  
  
 (ウィンドウが表示されます) かどうか、ウィンドウが変更された、アプリケーションを呼び出す必要があります内に存在するメニューたびに`CWnd::DrawMenuBar`です。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem  
 指定されたメニューの既定のメニュー項目を設定します。  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 識別子または新しい既定のメニュー項目またはない既定の項目の 1 の位置。 このパラメーターの意味は、の値によって異なります。`fByPos`です。  
  
 `fByPos`  
 値の意味を指定する`uItem`です。 このパラメーターは、する場合**FALSE**、`uItem`メニュー項目の識別子を指定します。 それ以外の場合、メニュー項目の位置を勧めします。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は 0 以外の値です。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Win32 関数を使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)Windows SDK で説明されている。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 関数の動作を実装して[SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId  
 コンテキスト ヘルプ ID に関連付けます`CMenu`です。  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwContextHelpId`  
 コンテキスト ヘルプ ID に関連付ける`CMenu`です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合 0  
  
### <a name="remarks"></a>コメント  
 メニュー内のすべての項目は、この id を共有 — 個々 のメニュー項目にヘルプ コンテキスト識別子をアタッチすることはできません。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::InsertMenu](#insertmenu)です。  
  
##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo  
 メニューの情報を設定します。  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcmi`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/ms647575)メニューの情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 戻り値は 0 以外です。 関数が成功した場合それ以外の場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
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
 `nPosition`  
 変更するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用することができます`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターは、既存のメニュー項目のコマンド ID を指定します。 既定値は、どちらの場合これは**とき**も**MF_BYPOSITION**が設定されています。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
 `nFlags`  
 指定方法`nPosition`は解釈されます。  
  
 `pBmpUnchecked`  
 メニュー項目のチェックされていない使用するビットマップを指定します。  
  
 `pBmpChecked`  
 オンになっているメニュー項目に対して使用するビットマップを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー項目が、オンまたはオフ、かどうか、Windows は、メニュー項目の横にある適切なビットマップを表示します。  
  
 いずれか`pBmpUnchecked`または`pBmpChecked`は**NULL**Windows では、属性に対応するメニュー項目の横に何が表示されます。 両方のパラメーターが場合**NULL**項目がチェックされ、項目がチェックされたときに、チェック マークを削除するときに Windows が既定のチェック マークを使用します。  
  
 メニューが破棄されると、これらのビットマップは破棄されません。アプリケーションは、それらを破棄しなければなりません。  
  
 Windows **GetMenuCheckMarkDimensions**関数は、メニュー項目に使用される既定のチェック マークの寸法を取得します。 アプリケーションでは、これらの値を使用して、この関数に渡すビットマップの適切なサイズを決定します。 サイズを取得し、ビットマップを作成して設定します。  
  
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
 `uItem`  
 説明を参照してください`uItem`で[SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) Windows SDK に含まれています。  
  
 `lpMenuItemInfo`  
 説明を参照してください`lpmii`で**SetMenuItemInfo** Windows SDK に含まれています。  
  
 `fByPos`  
 説明を参照してください`fByPosition`で**SetMenuItemInfo** Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 この関数をラップ[SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001)Windows SDK に記述されている。  
  
##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu  
 指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択肢を追跡します。  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 フラグを画面位置とマウスの位置を指定します。 参照してください[TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002)使用可能なフラグの一覧についてはします。  
  
 *x*  
 ポップアップ メニューの画面座標で水平方向の位置を指定します。 値に応じて、`nFlags`パラメーター、メニューは左揃え、右揃え、またはこの位置に対して中央揃えを指定できます。  
  
 *y*  
 画面で、メニューの上部の画面座標で、垂直位置を指定します。  
  
 `pWnd`  
 ポップアップ メニューを所有しているウィンドウを識別します。 このパラメーターを指定できません**NULL**場合でも、 **TPM_NONOTIFY**フラグが指定されています。 このウィンドウはすべて受信**WM_COMMAND**メニューからのメッセージ。 Windows ではバージョン 3.1 以降では、ウィンドウを受け取りません**WM_COMMAND**までメッセージ`TrackPopupMenu`を返します。 Windows 3.0 では、ウィンドウを受け取ります**WM_COMMAND**する前にメッセージ`TrackPopupMenu`を返します。  
  
 `lpRect`  
 無視されます。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、呼び出しの結果を返します[TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 浮動小数点のポップアップ メニュー画面のどこでも表示できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx  
 指定した位置に浮動小数点のポップアップ メニューを表示し、ポップアップ メニュー項目の選択肢を追跡します。  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>パラメーター  
 `fuFlags`  
 拡張メニューのさまざまな関数を指定します。 すべての値の一覧とその意味では、次を参照してください。[バインド](http://msdn.microsoft.com/library/windows/desktop/ms648003)です。  
  
 *x*  
 ポップアップ メニューの画面座標で水平方向の位置を指定します。  
  
 *y*  
 画面で、メニューの上部の画面座標で、垂直位置を指定します。  
  
 `pWnd`  
 ポップアップ メニューを所有していると、[作成] メニューから、メッセージの受信ウィンドウへのポインター。 このウィンドウは、現在のアプリケーションからの任意のウィンドウを指定できますが、指定できません**NULL**です。 指定した場合**TPM_NONOTIFY**で、`fuFlags`パラメーター、関数はすべてのメッセージを送信しません`pWnd`です。 によって示される、ウィンドウ関数が返す必要があります`pWnd`を受信する、 **WM_COMMAND**メッセージ。  
  
 *lptpm*  
 ポインター、[重ならないようにする](http://msdn.microsoft.com/library/windows/desktop/ms647586)メニュー画面の領域を指定する構造体が重ならないようにします。 このパラメーターを指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 指定した場合**TPM_RETURNCMD**で、`fuFlags`パラメーター、戻り値は、ユーザーが選択された項目をメニュー項目の識別子。 ユーザーを選択せず、メニューをキャンセルした場合、またはエラーが発生した場合は、戻り値は 0 です。  
  
 指定しない場合**TPM_RETURNCMD**で、`fuFlags`パラメーター、戻り値は、関数が成功した場合は 0 以外、0、失敗した場合。 拡張エラー情報を取得する呼び出し[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="remarks"></a>コメント  
 浮動小数点のポップアップ メニュー画面のどこでも表示できます。 ポップアップ メニューを作成するときにエラーの処理の詳細については、次を参照してください。[バインド](http://msdn.microsoft.com/library/windows/desktop/ms648003)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLTEST](../../visual-cpp-samples.md)   
 [MFC サンプル DYNAMENU](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)
