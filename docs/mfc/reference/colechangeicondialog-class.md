---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs:
- C++
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b675cfd635fd4dea962c30605072beec1545dda1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="colechangeicondialog-class"></a>メンバー クラス
OLE の [アイコンの変更] ダイアログ ボックスに使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|`COleChangeIconDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|ダイアログ ボックスで指定された変更を実行します。|  
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 アイコンの変更 ダイアログ ボックスが表示されます。|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコンの形式に関連付けられているメタファイルへのハンドルを取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|ダイアログ ボックスの動作を制御する構造体。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleChangeIconDialog`をこのダイアログ ボックスを呼び出したいとします。 後に、`COleChangeIconDialog`オブジェクトが構築された、使用することができます、[各](#m_ci)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_ci`構造体は型**OLEUICHANGEICON**です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
 詳細については、次を参照してください。、 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK 内の構造。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog  
 この関数はのみ、`COleChangeIconDialog`オブジェクト。  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 変換する項目へのポインター。  
  
 `dwFlags`  
 作成フラグは、次の値の任意の数を含む結合演算を使用して、or 演算子。  
  
- **CIF_SELECTCURRENT**  ダイアログ ボックスが呼び出されたときに、現在このオプション ボタンを最初に選択することを指定します。 既定値です。  
  
- **CIF_SELECTDEFAULT**  ダイアログ ボックスが呼び出されたときに既定のオプション ボタンを最初に選択することを指定します。  
  
- **CIF_SELECTFROMFILE**  ダイアログ ボックスが呼び出されたときに、ファイルから ラジオ ボタンをクリックした状態を指定します。  
  
- **CIF_SHOWHELP**  ダイアログ ボックスが呼び出されたときに、ヘルプ ボタンを表示するように指定します。  
  
- **CIF_USEICONEXE**アイコンがで指定された実行可能ファイルから抽出することを指定します、 **szIconExe**フィールド[各](#m_ci)の代わりに、型から取得します。 これは、埋め込みまたは非 OLE ファイルへのリンクに役立ちます。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。  
  
 詳細については、次を参照してください。、 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK 内の構造。  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 後のダイアログ ボックスで選択されている 1 つに項目を表すアイコンを変更するには、この関数を呼び出す[DoModal](#domodal)返します**IDOK**です。  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 アイコンを変更する項目へのポインター。  
  
### <a name="return-value"></a>戻り値  
 変更が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 OLE の [アイコンの変更] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出し、返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) Windows SDK 内の関数。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定してさまざまなダイアログ ボックスのコントロールを初期化する場合、[各](#m_ci)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**設定や、ダイアログ ボックスに、ユーザーが入力した情報を取得する関数の他のメンバーを呼び出すことができます。  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 この関数では、選択した項目のアイコンの外観を含むメタファイルへのハンドルを取得します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハンドルを選択して、ダイアログ ボックスが破棄された場合に、新しいアイコンのアイコンの外観を持つメタファイル **[ok]** 以外の場合はアイコンが、ダイアログ ボックスが表示される前にします。  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 型の構造体**OLEUICHANGEICON**アイコンの変更 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK 内の構造。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
