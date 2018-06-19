---
title: CLinkCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2312861a1b13ecb432c7893a27d72c61ecd78ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371700"
---
# <a name="clinkctrl-class"></a>CLinkCtrl クラス
Windows コモン SysLink コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|`CLinkCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|リンク コントロールを作成し、それにアタッチ、`CLinkCtrl`オブジェクト。|  
|[適用](#createex)|拡張スタイルを使用してリンク コントロールを作成し、それにアタッチ、`CLinkCtrl`オブジェクト。|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|リンク コントロールの適切な高さを取得します。|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|リンク テキスト リンクの指定した幅に応じて、現在のリンク コントロールの適切な高さを計算します。|  
|[CLinkCtrl::GetItem](#getitem)|状態とのリンク コントロールのアイテムの属性を取得します。|  
|[CLinkCtrl::GetItemID](#getitemid)|リンク コントロールの項目の ID を取得します。|  
|[CLinkCtrl::GetItemState](#getitemstate)|リンク コントロールの項目の状態を取得します。|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|リンク コントロールのアイテムで表される URL を取得します。|  
|[CLinkCtrl::HitTest](#hittest)|ユーザーが指定されたリンクをクリックするかどうかを判断します。|  
|[CLinkCtrl::SetItem](#setitem)|状態とのリンク コントロールのアイテムの属性を設定します。|  
|[CLinkCtrl::SetItemID](#setitemid)|リンク コントロールの項目の ID を設定します。|  
|[CLinkCtrl::SetItemState](#setitemstate)|リンク コントロールの項目の状態を設定します。|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|リンク コントロールのアイテムで表される URL を設定します。|  
  
## <a name="remarks"></a>コメント  
 「リンク制御」ウィンドウにハイパー テキスト リンクを埋め込むには便利な方法を提供します。 実際のコントロールは、テキストを表示し、ユーザーが埋め込みリンクをクリックしたときに、適切なアプリケーションを起動するウィンドウです。 複数のリンクは、1 つのコントロールではサポートされてし、0 から始まるインデックスによってアクセスできることができます。  
  
 このコントロール (したがって、`CLinkCtrl`クラス) は下にある Windows XP 以降を実行中のプログラムでのみ使用できます。  
  
 詳細については、次を参照してください。 [SysLink コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760706)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="clinkctrl"></a>  CLinkCtrl::CLinkCtrl  
 `CLinkCtrl` オブジェクトを構築します。  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>  CLinkCtrl::Create  
 リンク コントロールを作成し、それにアタッチ、`CLinkCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLinkMarkup`  
 マークされた項目を表示するテキストを含む 0 で終わる文字列へのポインター。 詳細については、」の「マークアップとリンクのアクセス」セクションを参照してください。 [SysLink コントロールの概要](http://msdn.microsoft.com/library/windows/desktop/bb760706)です。  
  
 `dwStyle`  
 リンク コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 参照してください[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、`Windows SDK`詳細についてはします。  
  
 `rect`  
 リンク コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 リンク コントロールの親ウィンドウを指定します。 なければなりません`NULL`です。  
  
 `nID`  
 リンク コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 `true` 初期化が成功した場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CLinkCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出す`Create`、リンク コントロールを作成しにアタッチする、`CLinkCtrl`オブジェクト。 拡張ウィンドウ スタイルをコントロールに使用する場合は、呼び出す[適用](#createex)の代わりに`Create`です。  
  
 2 番目の形式、`Create`メソッドは使用されなくなりました。 指定する最初の形式を使用して、`lpszLinkMarkup`パラメーター。  
  
### <a name="example"></a>例  
 次のコード例は、という名前の 2 つの変数を定義`m_Link1`と`m_Link2`、2 つのリンク コントロールのアクセスに使用されます。  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、別のリンク コントロールの場所に基づき、1 つのリンク コントロールを作成します。 リソース ローダーは、アプリケーションの起動時に最初のリンク コントロールを作成します。 OnInitDialog メソッドに入ると、アプリケーションとき、に、最初のリンク コントロールの位置を基準とした 2 番目のリンク コントロールを作成します。 2 番目のリンク コントロール、表示されるテキストに合わせてサイズを変更します。  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  適用  
 拡張スタイルを使用してリンク コントロールを作成し、それにアタッチ、`CLinkCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLinkMarkup`  
 マークされた項目を表示するテキストを含む 0 で終わる文字列へのポインター。 詳細については、」の「マークアップとリンクのアクセス」セクションを参照してください。 [SysLink コントロールの概要](http://msdn.microsoft.com/library/windows/desktop/bb760706)です。  
  
 `dwExStyle`  
 リンク コントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 `dwStyle`  
 リンク コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 詳細については、次を参照してください。[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)Windows SDK に含まれています。  
  
 `rect`  
 リンク コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 リンク コントロールの親ウィンドウを指定します。 なければなりません`NULL`です。  
  
 `nID`  
 リンク コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 `true` 初期化が成功した場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 使用して`CreateEx`の代わりに[作成](#create)拡張ウィンドウ スタイルの定数を適用します。  
  
 2 番目の形式、`CreateEx`メソッドは使用されなくなりました。 指定する最初の形式を使用して、`lpszLinkMarkup`パラメーター。  
  
##  <a name="getidealheight"></a>  CLinkCtrl::GetIdealHeight  
 リンク コントロールの適切な高さを取得します。  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で表したコントロールの適切な高さです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716)Windows SDK で説明されている。  
  
##  <a name="getidealsize"></a>  CLinkCtrl::GetIdealSize  
 リンク テキスト リンクの指定した幅に応じて、現在のリンク コントロールの適切な高さを計算します。  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `cxMaxWidth`|ピクセル単位で、リンクの最大の幅。|  
|[out] * `pSize`|Windows へのポインター[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造体。 このメソッドが戻るとき、`cy`のメンバー、`SIZE`構造で指定されたリンク テキストの幅の理想的なリンク テキストの高さに含まれる`cxMaxWidth`です。 `cx`構造体のメンバーには、実際に必要なリンク テキストの幅が含まれています。|  
  
### <a name="return-value"></a>戻り値  
 適切な高さ (ピクセル単位)、このリンク テキスト。 戻り値は、同じの値として、`cy`のメンバー、`SIZE`構造体。  
  
### <a name="remarks"></a>コメント  
 例については、`GetIdealSize`メソッドの例を参照してください[CLinkCtrl::Create](#create)です。  
  
 このメソッドは、送信、 [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) Windows SDK で説明するメッセージ。  
  
##  <a name="getitem"></a>  CLinkCtrl::GetItem  
 状態とのリンク コントロールのアイテムの属性を取得します。  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)項目情報を受け取る構造です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)Windows SDK で説明されている。  
  
##  <a name="getitemid"></a>  CLinkCtrl::GetItemID  
 リンク コントロールの項目の ID を取得します。  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 *strID*  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)指定した項目の ID を表すオブジェクト。  
  
 *szID*  
 指定した項目の ID を表す、null で終わる文字列。  
  
 *cchID*  
 サイズの文字、 *szID*バッファー。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
> [!NOTE]
>  この関数も返します**FALSE**場合のバッファー *szID または strID*よりも小さい**MAX_LINKID_TEXT**です。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の ID を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) Windows SDK に含まれています。  
  
##  <a name="getitemstate"></a>  CLinkCtrl::GetItemState  
 リンク コントロールの項目の状態を取得します。  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `pnState`  
 指定された状態の項目の値です。  
  
 `stateMask`  
 取得するには、どの状態アイテムを記述するフラグの組み合わせ。 値の一覧は、の説明を参照して、**状態**内のメンバー、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)構造体。 許容される項目はで許可されているものと同じ**状態**です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の指定された状態の項目の値を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) Windows SDK に含まれています。  
  
##  <a name="getitemurl"></a>  CLinkCtrl::GetItemUrl  
 リンク コントロールのアイテムで表される URL を取得します。  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `strUrl`  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)を指定した項目によって表される URL を含むオブジェクトを  
  
 `szUrl`  
 指定した項目によって表される URL を含む null で終わる文字列  
  
 *cchUrl*  
 サイズの文字、 *szURL*バッファー。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
> [!NOTE]
>  この関数も返します**FALSE**場合のバッファー *szUrl または strUrl*よりも小さい**MAX_LINKID_TEXT**です。  
  
### <a name="remarks"></a>コメント  
 指定したリンク コントロールの項目で表される URL を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) Windows SDK に含まれています。  
  
##  <a name="hittest"></a>  CLinkCtrl::HitTest  
 ユーザーが指定されたリンクをクリックしたかどうかを判断します。  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *phti*  
 ポインター、**すべて保持**ユーザーがクリックしたリンクに関する情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722)Windows SDK で説明されている。  
  
##  <a name="setitem"></a>  CLinkCtrl::SetItem  
 状態とのリンク コントロールのアイテムの属性を設定します。  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)設定情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)Windows SDK で説明されている。  
  
##  <a name="setitemid"></a>  CLinkCtrl::SetItemID  
 リンク コントロールの項目の ID を取得します。  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 *szID*  
 指定した項目の ID を表す、null で終わる文字列。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の ID を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) Windows SDK に含まれています。  
  
##  <a name="setitemstate"></a>  CLinkCtrl::SetItemState  
 リンク コントロールの項目の状態を取得します。  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `pnState`  
 設定されている指定された状態の項目の値です。  
  
 `stateMask`  
 設定されている状態の項目を記述するフラグの組み合わせ。 値の一覧は、の説明を参照して、**状態**内のメンバー、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)構造体。 許容される項目はで許可されているものと同じ**状態**です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の指定された状態の項目の値を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) Windows SDK に含まれています。  
  
##  <a name="setitemurl"></a>  CLinkCtrl::SetItemUrl  
 リンク コントロールのアイテムで表される URL を設定します。  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `szUrl`  
 指定した項目によって表される URL を含む null で終わる文字列  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 指定したリンク コントロールの項目で表される URL を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)
