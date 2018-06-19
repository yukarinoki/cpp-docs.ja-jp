---
title: CComboBoxEx クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
dev_langs:
- C++
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7d2c5bbd3445e604620dc1f23f45004b7a3b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358292"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx クラス
イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。  
  
## <a name="syntax"></a>構文  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|コンボ ボックスを作成しにアタッチ、`CComboBoxEx`オブジェクト。|  
|[CComboBoxEx::CreateEx](#createex)|指定した Windows 拡張スタイルを使用して、コンボ ボックスを作成しにアタッチ、 **ComboBoxEx**オブジェクト。|  
|[CComboBoxEx::DeleteItem](#deleteitem)|項目を削除、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|子コンボ ボックス コントロールへのポインターを取得します。|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|編集コントロールの部分を識別するハンドルを取得、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|使用されている拡張スタイルを取得、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::GetImageList](#getimagelist)|割り当てられているイメージ リストへのポインターを取得、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::GetItem](#getitem)|項目の情報の取得、指定された**ComboBoxEx**項目。|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|内容をユーザーが変更されたかどうかを判断、 **ComboBoxEx** 」と入力してコントロールを編集します。|  
|[CComboBoxEx::InsertItem](#insertitem)|新しい項目を挿入、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|内の拡張スタイルを設定、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::SetImageList](#setimagelist)|用のイメージ リストの設定、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::SetItem](#setitem)|内の項目の属性を設定、 **ComboBoxEx**コントロール。|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Visual スタイル拡張コンボ ボックス コントロールを設定します。|  
  
## <a name="remarks"></a>コメント  
 使用して`CComboBoxEx`コンボ ボックス コントロールを作成するが不要になった、独自のイメージを描画コードを実装します。 代わりに、`CComboBoxEx`はイメージ リストのイメージをアクセスします。  
  
## <a name="image-list-support"></a>イメージ リストのサポート  
 標準のコンボ ボックスでは、コンボ ボックスの所有者は、コンボ ボックスのオーナー描画コントロールとして作成してイメージを描画して担当します。 使用すると`CComboBoxEx`、描画スタイルを設定する必要はありません**CBS_OWNERDRAWFIXED**と**CBS_HASSTRINGS**は暗黙的に指定するためです。 それ以外の場合、描画操作を実行するコードを記述する必要があります。 A`CComboBoxEx`コントロールは、項目ごとに最大 3 つのイメージをサポートしています。 1 つは、選択されていない状態、オーバーレイの画像の選択された状態。  
  
## <a name="styles"></a>スタイル  
 `CComboBoxEx` スタイルをサポートしている**CBS_SIMPLE**、 **CBS_DROPDOWN**、 **CBS_DROPDOWNLIST**、および**WS_CHILD**です。 ウィンドウを作成するときに渡されるその他のすべてのスタイルは、コントロールによって無視されます。 ウィンドウが作成されると、使用できるその他のコンボ ボックス スタイルを呼び出して、`CComboBoxEx`メンバー関数は、[拡張](#setextendedstyle)です。 これらのスタイルは、次のことができます。  
  
-   大文字小文字を区別する一覧で、文字列の検索をセットします。  
  
-   コンボ ボックス コントロールを作成 ('/')、スラッシュを使用して円記号 ('\\')、および期間 ('. ') の単語の区切り記号として文字です。 これにより、ユーザーがキーボード ショートカット CTRL キーと方向を使用して単語から単語にジャンプできます。  
  
-   コンボ ボックス コントロールを表示またはイメージを表示しませんを設定します。 イメージが表示されない場合、コンボ ボックスは、イメージを対応するテキストのインデントを削除できます。  
  
-   幅より広いコンボ ボックスが含まれているクリップ、狭いコンボ ボックス コントロールを作成します。  
  
 これらのスタイル フラグに記載されているさらに[を使用して CComboBoxEx](../../mfc/using-ccomboboxex.md)です。  
  
## <a name="item-retention-and-callback-item-attributes"></a>アイテムの保存とコールバック項目属性  
 Win32 構造の項目とイメージ、インデント値およびテキスト文字列のインデックスなどのアイテムの情報が格納されている[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)Windows SDK で説明されている。 構造体には、コールバック フラグに対応するメンバーも含まれています。  
  
 詳細な概念的な詳細については、次を参照してください。[を使用して CComboBoxEx](../../mfc/using-ccomboboxex.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx  
 作成するには、このメンバー関数を呼び出して、`CComboBoxEx`オブジェクト。  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>  CComboBoxEx::Create  
 コンボ ボックスを作成しにアタッチ、`CComboBoxEx`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 コンボ ボックスに適用するコンボ ボックス スタイルの組み合わせを指定します。 参照してください**解説**下スタイルの詳細についてはします。  
  
 `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コンボ ボックスのサイズと位置である構造体。  
  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)コンボ ボックスの親ウィンドウにオブジェクト (通常、 `CDialog`)。 なければなりません**NULL**です。  
  
 `nID`  
 コンボ ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 作成、 `CComboBoxEx` 2 つのステップ内のオブジェクト。  
  
1.  呼び出す[CComboBoxEx](#ccomboboxex)構築するために、`CComboBoxEx`オブジェクト。  
  
2.  このメンバー関数、拡張の Windows コンボ ボックスを作成し、それにアタッチする、`CComboBoxEx`オブジェクト。  
  
 呼び出すと**作成**、MFC コモン コントロールを初期化します。  
  
 コンボ ボックスを作成するときに、次のコンボ ボックス スタイルの一部またはすべてを指定できます。  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 ウィンドウを作成するときに渡されるその他のすべてのスタイルは無視されます。 **ComboBoxEx**コントロールには、追加機能を提供する拡張スタイルもサポートしています。 これらのスタイルが説明されている[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)、Windows SDK に含まれています。 呼び出すことによってこれらのスタイルを設定[拡張](#setextendedstyle)です。  
  
 拡張ウィンドウ スタイルをコントロールに使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**です。  
  
##  <a name="createex"></a>  CComboBoxEx::CreateEx  
 拡張コンボ ボックス コントロール (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CComboBoxEx`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 `dwStyle`  
 コンボ ボックス コントロールのスタイルです。 参照してください[作成](#create)スタイルの一覧です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体`pParentWnd`です。  
  
 `pParentWnd`  
 コントロールの親であるウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して`CreateEx`の代わりに**作成**Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
 `CreateEx` 指定された拡張ウィンドウ スタイルでコントロールが作成され`dwExStyle`です。 必要があります拡張スタイルに固有の設定拡張コンボ ボックス コントロールを使用して、[拡張](#setextendedstyle)です。 たとえば、使用して`CreateEx`としてこのようなスタイルを設定する**WS_EX_CONTEXTHELP**が使用して`SetExtendedStyle`としてこのようなスタイルを設定する**CBES_EX_CASESENSITIVE**です。 詳細については、トピックで説明されているスタイルを参照してください。 [ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)Windows SDK に含まれています。  
  
##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem  
 項目を削除、 **ComboBoxEx**コントロール。  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 削除する項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 コントロール内の残りの項目の数。 場合`iIndex`が有効でない関数を返します**CB_ERR**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装[CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768)Windows SDK で説明されている。 DeleteItem を呼び出すとき、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージを**CBEN_DELETEITEM**を親ウィンドウに通知が送信されます。  
  
##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl  
 内のコンボ ボックス コントロールへのポインターを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`オブジェクト。  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CComboBox`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CComboBoxEx`カプセル化されている親ウィンドウのコントロールでは、`CComboBox`です。  
  
 `CComboBox`戻り値によって指されるオブジェクトは一時オブジェクトであり、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl  
 コンボ ボックスのエディット コントロールへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CEdit](../../mfc/reference/cedit-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 A`CComboBoxEx`使用して作成されたときに、コントロールが編集ボックスを使用して、 **CBS_DROPDOWN**スタイル。  
  
 `CEdit`戻り値によって指されるオブジェクトは一時オブジェクトであり、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle  
 使用する拡張スタイルを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`コントロール。  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `DWORD`コンボ ボックス コントロールの使用されている拡張スタイルを表す値です。  
  
### <a name="remarks"></a>コメント  
 参照してください[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)これらのスタイルの詳細については、Windows SDK に含まれています。  
  
##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList  
 によって使用されるイメージ リストへのポインターを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`コントロール。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。 失敗したかどうか、このメンバー関数を返します**NULL**です。  
  
### <a name="remarks"></a>コメント  
 `CImageList`戻り値によって指されるオブジェクトは一時オブジェクトであり、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="getitem"></a>  CComboBoxEx::GetItem  
 項目の情報の取得、指定された**ComboBoxEx**項目。  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCBItem`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装[CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779)Windows SDK で説明されている。  
  
##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged  
 内容をユーザーが変更されたかどうかを判断、 **ComboBoxEx** 」と入力してコントロールを編集します。  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのエディット ボックスで、ユーザーが入力した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装[CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782)Windows SDK で説明されている。  
  
##  <a name="insertitem"></a>  CComboBoxEx::InsertItem  
 新しい項目を挿入、 **ComboBoxEx**コントロール。  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCBItem`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目情報を受け取る。 この構造体には、項目のコールバック フラグの値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 挿入先である新しい項目が成功した場合、インデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
 呼び出すと`InsertItem`、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージを[CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764)を親ウィンドウに通知が送信されます。  
  
##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle  
 コンボ ボックス コントロールを拡張するための拡張スタイルを設定するには、このメンバー関数を呼び出します。  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExMask`  
 A`DWORD`のスタイルを示す値`dwExStyles`影響を受けるには、します。 拡張スタイルのみ`dwExMask`変更されます。 他のすべてのスタイルが保持されます。 このパラメーターが 0、すべてのスタイルの場合`dwExStyles`を受けます。  
  
 `dwExStyles`  
 A`DWORD`コンボ ボックスを含む値が拡張スタイルをコントロールの設定を制御します。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`コントロールの使用されていた拡張スタイルを表す値です。  
  
### <a name="remarks"></a>コメント  
 参照してください[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)これらのスタイルの詳細については、Windows SDK に含まれています。  
  
 拡張ウィンドウ スタイルを使用してコントロールを拡張コンボ ボックスを作成するには、使用[CreateEx](#createex)です。  
  
##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList  
 用のイメージ リストの設定、 **ComboBoxEx**コントロール。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、`CImageList`オブジェクトで使用するイメージを含む、`CComboBoxEx`コントロール。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトによって使用されていたイメージを含む、`CComboBoxEx`コントロール。 **NULL**イメージ リストが既に設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装[CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787)Windows SDK で説明されている。 既定の編集コントロールの高さを変更する場合は、Win32 関数を呼び出す[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)呼び出し後に、コントロールのサイズを変更する`SetImageList`、正しく表示されません。  
  
 `CImageList`戻り値によって指されるオブジェクトは一時オブジェクトであり、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="setitem"></a>  CComboBoxEx::SetItem  
 内の項目の属性を設定、 **ComboBoxEx**コントロール。  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCBItem`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装[CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788)Windows SDK で説明されている。  
  
##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme  
 Visual スタイル拡張コンボ ボックス コントロールを設定します。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSubAppName`  
 設定するには、拡張コンボ ボックス visual スタイルを表す Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790)メッセージ、Windows SDK で説明します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)
