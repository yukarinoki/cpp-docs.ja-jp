---
title: CHotKeyCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 590914ac312a4f998eb759beb08ed2e7935874fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl クラス
Windows コモン ホット キー コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|ホット キー コントロールを作成し、それにアタッチ、`CHotKeyCtrl`オブジェクト。|  
|[CHotKeyCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでホット キー コントロールを作成しにアタッチ、`CHotKeyCtrl`オブジェクト。|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|ホット キー コントロールからホット キーの仮想キー コードと修飾子フラグを取得します。|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|ホット キーに割り当てられている、ローカルの文字セットで、キー名を取得します。|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|キー名を指定した仮想キー コードに割り当てられている、ローカルの文字セットを取得します。|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|ホット キー コントロールのホット キーの組み合わせを設定します。|  
|[CHotKeyCtrl::SetRules](#setrules)|無効な組み合わせとホット キー コントロールの既定の修飾子の組み合わせを定義します。|  
  
## <a name="remarks"></a>コメント  
 「ホット キー コントロール」は、ユーザーがホット キーを作成できるウィンドウです。 「ホット キー」は、キーの組み合わせを押すと、アクションをすばやく実行することです。 (たとえば、ユーザー キーを作成、ホット、特定のウィンドウをアクティブにし、これを Z オーダーの最上位にします。)ホット キー コントロールは、ユーザーの選択肢を表示し、ユーザーが有効なキーの組み合わせを選択することにより、します。  
  
 このコントロール (したがって、`CHotKeyCtrl`クラス) は、Windows 95/98 および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 アプリケーションがコントロールから指定したキーの組み合わせを取得しを使用して、ユーザーがキーの組み合わせを選択すると、ときに、 **WM_SETHOTKEY**システムでホット キーを設定するメッセージ。 押されたときに、ホット キー、その後、システムの任意の部分からの指定された、ウィンドウ、 **WM_SETHOTKEY**メッセージを受信、`WM_SYSCOMMAND`メッセージを指定する**SC_HOTKEY**です。 このメッセージには、それを受信するウィンドウがアクティブにします。 呼び出したアプリケーションまで、ホット キーは有効**WM_SETHOTKEY**が終了します。  
  
 このメカニズムは、ホット キーのサポートに依存している異なる、 **WM_HOTKEY**メッセージと、Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)と[UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327)関数。  
  
 使用する方法について`CHotKeyCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl  
 `CHotKeyCtrl` オブジェクトを構築します。  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>  CHotKeyCtrl::Create  
 ホット キー コントロールを作成し、それにアタッチ、`CHotKeyCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ホット キー コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 参照してください[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)詳細については、Windows SDK に含まれています。  
  
 `rect`  
 ホット キー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)です。  
  
 `pParentWnd`  
 ホット キー コントロールの親ウィンドウを通常を指定します、 [CDialog](../../mfc/reference/cdialog-class.md)です。 なければなりません**NULL**です。  
  
 `nID`  
 ホット キー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CHotKeyCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出す**作成**、ホット キー コントロールを作成しにアタッチする、`CHotKeyCtrl`オブジェクト。  
  
 拡張ウィンドウ スタイルをコントロールに使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**です。  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 コントロールを作成し、(子ウィンドウ) でそれを関連付けるには、この関数を呼び出して、`CHotKeyCtrl`オブジェクト。  
  
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
 ホット キー コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 詳細については、次を参照してください。[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)Windows SDK に含まれています。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体`pParentWnd`です。  
  
 `pParentWnd`  
 コントロールの親であるウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 ホット キー コントロールのキーボード ショートカットの仮想キー コードと修飾子フラグを取得します。  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wVirtualKeyCode`  
 キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 [出力] `wModifiers`  
 キーボード ショートカット キーの修飾子キーを示すフラグのビットごとの組み合わせ (OR)。  
  
 修飾子フラグは次のとおりです。  
  
|フラグ|対応するキー|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT キー|  
|`HOTKEYF_CONTROL`|CTRL キー|  
|`HOTKEYF_EXT`|拡張キー|  
|`HOTKEYF_SHIFT`|Shift キー|  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードされたメソッドを`DWORD`仮想キー コードと修飾子のフラグを格納しています。 下位ワードの下位バイトが仮想キー コードには、下位ワードの高位バイト フラグを含む、修飾子、および上位ワードにはゼロです。  
  
### <a name="remarks"></a>コメント  
 仮想キー コードと修飾子キーを一緒には、キーボード ショートカットを定義します。  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 ホット キーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているホット キーのローカライズされた名前。 選択したホット キーがない場合`GetHotKeyName`空の文字列を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数によって返される名前のキーボード ドライバーに由来します。 ローカライズされたバージョンの Windows でローカライズされていないキーボード ドライバーをインストールして、その逆です。  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 指定した仮想キー コードに割り当てられたキーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>パラメーター  
 `vk`  
 仮想キー コード。  
  
 *fExtended*  
 仮想キー コードは、拡張キー場合**TRUE**それ以外の**FALSE**です。  
  
### <a name="return-value"></a>戻り値  
 指定されたキーのローカライズされた名前、`vk`パラメーター。 キーがマップされている名前を持たない場合`GetKeyName`空の文字列を返します。  
  
### <a name="remarks"></a>コメント  
 この関数によって返されるキーの名前は、ローカライズされたバージョンの Windows でローカライズされていないキーボード ドライバーをインストールできるようにキーボード ドライバーから取得し、その逆です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 ホット キー コントロールのキーボード ショートカットを設定します。  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wVirtualKeyCode`  
 キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 [入力] `wModifiers`  
 キーボード ショートカット キーの修飾子キーを示すフラグのビットごとの組み合わせ (OR)。  
  
 修飾子フラグは次のとおりです。  
  
|フラグ|対応するキー|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT キー|  
|`HOTKEYF_CONTROL`|CTRL キー|  
|`HOTKEYF_EXT`|拡張キー|  
|`HOTKEYF_SHIFT`|Shift キー|  
  
### <a name="remarks"></a>コメント  
 仮想キー コードと修飾子キーを一緒には、キーボード ショートカットを定義します。  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 無効な組み合わせおよびホット キー コントロールの既定の修飾子の組み合わせを定義するには、この関数を呼び出します。  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>パラメーター  
 `wInvalidComb`  
 無効なキーの組み合わせを指定するフラグの配列。 次の値の組み合わせであることができます。  
  
- `HKCOMB_A` ALT キー  
  
- `HKCOMB_C` CTRL キー  
  
- `HKCOMB_CA` CTRL + ALT  
  
- `HKCOMB_NONE` 変更されていないキー  
  
- `HKCOMB_S` SHIFT キー  
  
- `HKCOMB_SA` SHIFT キーを押しながら ALT キー  
  
- `HKCOMB_SC` CTRL + SHIFT キー  
  
- `HKCOMB_SCA` CTRL + ALT + SHIFT +  
  
 `wModifiers`  
 ユーザーが、無効な組み合わせを入力したときに使用するキーの組み合わせを指定するフラグの配列。 修飾子フラグの詳細については、次を参照してください。 [GetHotKey](#gethotkey)です。  
  
### <a name="remarks"></a>コメント  
 ユーザーが無効なキーの組み合わせに入ったときに指定されたフラグの定義に従って`wInvalidComb`、システムでは、OR 演算子を使用して、指定されたフラグを使って、ユーザーが入力したキーの組み合わせ`wModifiers`です。 結果として得られるキーの組み合わせは文字列に変換され、ホット キー コントロールに表示されます。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



