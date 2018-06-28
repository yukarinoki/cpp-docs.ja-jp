---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aaf60141747f1ff1db2256815f24e6708307ab7
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042171"
---
# <a name="coleinsertdialog-class"></a>メンバー クラス
OLE の [オブジェクトの挿入] ダイアログ ボックスで使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|`COleInsertDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[クリック](#createitem)|ダイアログ ボックスで選択した項目を作成します。|  
|[COleInsertDialog::DoModal](#domodal)|OLE の [オブジェクトの挿入] ダイアログ ボックスが表示されます。|  
|[COleInsertDialog::GetClassID](#getclassid)|取得、 **CLSID**選択したアイテムに関連付けられています。|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|アイコンとして項目を描画するかどうかを指示します。|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコンの形式に関連付けられているメタファイルへのハンドルを取得します。|  
|[COleInsertDialog::GetPathName](#getpathname)|ダイアログ ボックスで選択したファイルへの完全パスを取得します。|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|選択したオブジェクトの種類を取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|型の構造体**使う** ダイアログ ボックスの動作を制御します。|  
  
## <a name="remarks"></a>Remarks  
 クラスのオブジェクトを作成`COleInsertDialog`をこのダイアログ ボックスを呼び出したいとします。 後に、`COleInsertDialog`オブジェクトが構築された、使用することができます、 [m_io](#m_io)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_io`構造体は型**使う**です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。  
  
 詳細については、次を参照してください。、[使う](http://msdn.microsoft.com/library/windows/desktop/ms691316)Windows SDK 内の構造。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog  
 この関数はのみ、`COleInsertDialog`オブジェクト。  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 任意の数のビットごとの OR 演算子を使用して結合するのには、次の値を含む作成フラグ:  
  
- **IOF_SHOWHELP**  ダイアログ ボックスが呼び出されたときに、ヘルプ ボタンを表示するように指定します。  
  
- **IOF_SELECTCREATENEW**  ダイアログ ボックスが呼び出されたときに、新規作成 をクリックした状態を指定します。 これは、既定値し、では使用できません**IOF_SELECTCREATEFROMFILE**です。  
  
- **IOF_SELECTCREATEFROMFILE** ] ダイアログ ボックスが呼び出されたときに、[ファイルから作成するラジオ ボタンをクリックした状態を指定します。 は使用できません**IOF_SELECTCREATENEW**です。  
  
- **IOF_CHECKLINK**  ダイアログ ボックスが呼び出されたときにリンク チェック ボックスを最初に確認することを指定します。  
  
- **IOF_DISABLELINK**リンク チェック ボックスは無効にする ダイアログ ボックスが呼び出されたときを指定します。  
  
- **IOF_CHECKDISPLAYASICON**アイコンで表示 チェック ボックスが最初にチェックする、現在のアイコンが表示されますおよびダイアログ ボックスが呼び出されたとき、アイコンの変更 ボタンが有効にすることを指定します。  
  
- **IOF_VERIFYSERVERSEXIST**  ダイアログ ボックスが、ダイアログ ボックスが表示される前に、登録情報データベースで指定されたサーバーが存在することを確認して、リスト ボックスに追加のクラスを検証する必要がありますを指定します。 このフラグを設定すると、パフォーマンスが低下することができますが大幅にします。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>Remarks  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。  
  
##  <a name="createitem"></a>  クリック  
 型のオブジェクトを作成するには、この関数を呼び出す[COleClientItem](../../mfc/reference/coleclientitem-class.md)場合にのみ、 [DoModal](#domodal)返します**IDOK**です。  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pItem*  
 作成される項目へのポインター。  
  
### <a name="return-value"></a>戻り値  
 アイテムが作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 割り当てる必要があります、`COleClientItem`オブジェクトの前に、この関数を呼び出すことができます。  
  
##  <a name="domodal"></a>  COleInsertDialog::DoModal  
 OLE の [オブジェクトの挿入] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 次のいずれかの値です。  
  
 `COleInsertDialog::DocObjectsOnly` DocObjects のみを挿入します。  
  
 `COleInsertDialog::ControlsOnly` ActiveX コントロールのみを挿入します。  
  
 0 は、DocObject も ActiveX コントロールを挿入します。 この値は結果の最初のプロトタイプとして同じ実装では、上に示したです。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
-   IDOK、ダイアログ ボックスが正常に表示された場合。  
  
-   IDCANCEL 場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
-   IDABORT 場合はエラーが発生しました。 IDABORT が返される場合は呼び出し、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[使う](http://msdn.microsoft.com/library/windows/desktop/ms694325)Windows SDK 内の関数。  
  
### <a name="remarks"></a>Remarks  
 メンバーを設定してさまざまなダイアログ ボックスのコントロールを初期化する場合、 [m_io](#m_io)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`IDOK を返します関数、ユーザーがダイアログ ボックスに情報入力や設定を取得するその他のメンバーを呼び出すことができます。  
  
##  <a name="getclassid"></a>  COleInsertDialog::GetClassID  
 取得するには、この関数を呼び出す、 **CLSID**場合にのみ、選択した項目に関連付けられている[DoModal](#domodal)を返します**IDOK**選択の種類は**メンバー。createNewItem**です。  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します、 **CLSID**選択した項目に関連付けられています。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect  
 ユーザーがアイコンとして選択した項目を表示する選択したかどうかを判断するには、この関数を呼び出します。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、オブジェクトを表示するために必要です。  
  
- `DVASPECT_CONTENT` アイコンで表示 チェック ボックスがオフかどうかに返されます。  
  
- `DVASPECT_ICON` アイコンで表示 チェック ボックスがオンになっているかどうかに返されます。  
  
### <a name="remarks"></a>Remarks  
 場合にのみ、この関数を呼び出す[DoModal](#domodal)返します**IDOK**です。  
  
 アスペクトの描画の詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内のデータ構造です。  
  
##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile  
 この関数では、選択した項目のアイコンの外観を含むメタファイルへのハンドルを取得します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択して、ダイアログ ボックスが破棄されたときにオンの場合はアイコンで表示 チェック ボックスが選択した項目のアイコンの外観を持つメタファイル ハンドル**OK**それ以外の**NULL**です。  
  
##  <a name="getpathname"></a>  COleInsertDialog::GetPathName  
 場合にのみ、選択したファイルの完全なパスを取得するには、この関数を呼び出す[DoModal](#domodal)返します**IDOK**選択の種類と**フルパス名**です。  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスで選択されたファイルの完全パスです。 選択の種類がある場合`createNewItem`、この関数は、意味のない返します`CString`リリース モードでまたはデバッグ モードでアサーションを発生させます。  
  
##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType  
 選択して、オブジェクトの挿入 ダイアログ ボックスが破棄されたときに選択した型を取得するには、この関数を呼び出す**OK**です。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択内容の種類です。  
  
### <a name="remarks"></a>Remarks  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COleInsertDialog`クラスです。  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 これらの値の簡単な説明に従ってください。  
  
- **フルパス名**新規作成のラジオ ボタンが選択されました。  
  
- **COleInsertDialog::insertFromFile**ファイルから、作成するラジオ ボタンが選択されました、リンク チェック ボックスはチェックされませんでした。  
  
- **COleInsertDialog::linkToFile**ファイルから、作成する ラジオ ボタンが選択され、リンク チェック ボックスがオンになっています。  
  
##  <a name="m_io"></a>  COleInsertDialog::m_io  
 型の構造体**使う**オブジェクトの挿入 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Remarks  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、[使う](http://msdn.microsoft.com/library/windows/desktop/ms691316)Windows SDK 内の構造。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [関数クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
