---
title: CHotKeyCtrl クラス |Microsoft Docs
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
ms.openlocfilehash: 4a7f5cee986ad82790870bfa7684a99c60dc462e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206267"
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
|[CHotKeyCtrl::Create](#create)|ホット キー コントロールを作成し、それにアタッチします、`CHotKeyCtrl`オブジェクト。|  
|[CHotKeyCtrl::CreateEx](#createex)|指定された Windows の拡張スタイルでホット キー コントロールを作成しにアタッチします、`CHotKeyCtrl`オブジェクト。|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|ホット キー コントロールのホット キーの仮想キー コードと修飾フラグを取得します。|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|ホット キーに割り当てられている、ローカルの文字セットで、キー名を取得します。|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|キー名を指定した仮想キー コードに割り当てられている、ローカルの文字セットを取得します。|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|ホット キー コントロールのホット キーの組み合わせを設定します。|  
|[CHotKeyCtrl::SetRules](#setrules)|無効な組み合わせとホット キー コントロールの既定の修飾子の組み合わせを定義します。|  
  
## <a name="remarks"></a>Remarks  
 「ホット キー コントロール」は、ユーザーは、ホット キーを作成できるウィンドウです。 「ホット キー」は、操作をすばやく実行するユーザーが押すキーの組み合わせです。 (たとえば、ユーザー作成できますを特定のウィンドウをアクティブ化し、Z オーダーの一番上にホット キー)。ホット キー コントロールでは、ユーザーの選択を表示し、ユーザーが有効なキーの組み合わせを選択することにより、します。  
  
 このコントロール (つまり、`CHotKeyCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 ユーザーがキーの組み合わせを選択した場合、アプリケーションはコントロールから、指定したキーの組み合わせを取得し、WM_SETHOTKEY メッセージを使用して、システムで、ホット キーを設定します。 押されたときに、ホット キー、その後、システムの任意の部分から WM_SETHOTKEY メッセージで指定されたウィンドウは SC_HOTKEY を指定する位置であるメッセージを受信します。 このメッセージには、受信するウィンドウがアクティブにします。 ホット キーは WM_SETHOTKEY 終了と呼ばれるアプリケーションまで有効です。  
  
 このメカニズムは WM_HOTKEY メッセージと、Windows に依存する、ホット キーのサポートと異なる[RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309)と[UnregisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646327)関数。  
  
 使用しての詳細については`CHotKeyCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)します。  
  
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
 ホット キー コントロールを作成し、それにアタッチします、`CHotKeyCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 ホット キー コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 参照してください[コモン コントロール スタイル](/windows/desktop/Controls/common-control-styles)詳細については、Windows sdk。  
  
 *rect*  
 ホット キー コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)します。  
  
 *pParentWnd*  
 通常、ホット キー コントロールの親ウィンドウを指定します、 [CDialog](../../mfc/reference/cdialog-class.md)します。 NULL は指定できません。  
  
 *nID*  
 ホット キー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、初期化が成功した場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CHotKeyCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、ホット キー コントロールを作成しにアタッチする`CHotKeyCtrl`オブジェクト。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`します。  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CHotKeyCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK に含まれています。  
  
 *dwStyle*  
 ホット キー コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 詳細については、次を参照してください。[コモン コントロール スタイル](/windows/desktop/Controls/common-control-styles)Windows SDK に含まれています。  
  
 *rect*  
 参照を[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用`CreateEx`の代わりに[作成](#create)、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 ホット キー コントロールのキーボード ショートカットの仮想キー コードと修飾フラグを取得します。  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*wVirtualKeyCode*  
 キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 [out]*と*  
 キーボード ショートカット キーの修飾子キーを示すフラグのビットごとの組み合わせ (OR)。  
  
 修飾フラグは次のとおりです。  
  
|フラグ|対応するキー|  
|----------|-----------------------|  
|HOTKEYF_ALT|ALT キー|  
|HOTKEYF_CONTROL|CTRL キー|  
|HOTKEYF_EXT|拡張キー|  
|HOTKEYF_SHIFT|Shift キー|  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードされたメソッド、仮想キー コードと修飾フラグを含む DWORD。 下位ワードの下位バイトが仮想キー コードが含まれています、下位ワードの高位バイトには、修飾子のフラグが含まれています。 上位ワードは 0 です。  
  
### <a name="remarks"></a>Remarks  
 仮想キー コードと修飾子キーを同時に、キーボード ショートカットを定義します。  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 ホット キーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているホット キーのローカライズされた名前。 選択したホット キーがない場合`GetHotKeyName`空の文字列を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数によって返される名前のキーボード ドライバーに由来します。 キーボードのローカライズされていないドライバーをインストールするには、Windows のローカライズされたバージョンで、またはその逆です。  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 指定した仮想キー コードに割り当てられているキーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>パラメーター  
 *vk*  
 仮想キー コード。  
  
 *fExtended*  
 仮想キー コードが拡張キー、TRUE の場合それ以外の場合は FALSE です。  
  
### <a name="return-value"></a>戻り値  
 指定されたキーのローカライズされた名前、 *vk*パラメーター。 キーがマップの名前を持たない場合`GetKeyName`空の文字列を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数によって返されるキーの名前は、Windows のローカライズ版でローカライズされていないキーボード ドライバーをインストールできるように、キーボード ドライバーから、その逆です。  
  
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
 [in]*wVirtualKeyCode*  
 キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 [in]*と*  
 キーボード ショートカット キーの修飾子キーを示すフラグのビットごとの組み合わせ (OR)。  
  
 修飾フラグは次のとおりです。  
  
|フラグ|対応するキー|  
|----------|-----------------------|  
|HOTKEYF_ALT|ALT キー|  
|HOTKEYF_CONTROL|CTRL キー|  
|HOTKEYF_EXT|拡張キー|  
|HOTKEYF_SHIFT|Shift キー|  
  
### <a name="remarks"></a>Remarks  
 仮想キー コードと修飾子キーを同時に、キーボード ショートカットを定義します。  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 無効な組み合わせとホット キー コントロールの既定の修飾子の組み合わせを定義するには、この関数を呼び出します。  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>パラメーター  
 *wInvalidComb*  
 無効なキーの組み合わせを指定するフラグの配列。 次の値の組み合わせを指定できます。  
  
- HKCOMB_A ALT  
  
- HKCOMB_C CTRL  
  
- HKCOMB_CA CTRL + ALT  
  
- HKCOMB_NONE 変更されていないキー  
  
- HKCOMB_S シフト  
  
- HKCOMB_SA SHIFT + ALT  
  
- CTRL + HKCOMB_SC シフト  
  
- HKCOMB_SCA SHIFT + CTRL + ALT  
  
 *と*  
 ユーザーが、無効な組み合わせを入力するときに使用するキーの組み合わせを指定するフラグの配列。 修飾フラグの詳細については、次を参照してください。 [GetHotKey](#gethotkey)します。  
  
### <a name="remarks"></a>Remarks  
 ユーザーが無効なキーの組み合わせに入ったときに指定されたフラグで定義されている*wInvalidComb*、システムで指定されたフラグで、ユーザーが入力したキーの組み合わせ、OR 演算子を使用する*と*. 結果として得られるキーの組み合わせは文字列に変換し、ホット キー コントロールに表示されます。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



