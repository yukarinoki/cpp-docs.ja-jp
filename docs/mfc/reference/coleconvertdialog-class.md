---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90453d4e8550038493545b691c978b59bda90fad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370290"
---
# <a name="coleconvertdialog-class"></a>メンバー クラス
詳細については、次を参照してください。、 [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Windows SDK 内の構造。  
  
## <a name="syntax"></a>構文  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|`COleConvertDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|ダイアログ ボックスで指定した変換を実行します。|  
|[COleConvertDialog::DoModal](#domodal)|OLE の [項目の変更] ダイアログ ボックスが表示されます。|  
|[COleConvertDialog::GetClassID](#getclassid)|取得、 **CLSID**選択したアイテムに関連付けられています。|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|アイテムをアイコンとして描画するかどうかを指定します。|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコンの形式に関連付けられているメタファイルへのハンドルを取得します。|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|選択の種類を取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|ダイアログ ボックスの動作を制御する構造体。|  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog  
 のみを構築、`COleConvertDialog`オブジェクト。  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 アクティブ化または変換する項目へのポインター。  
  
 `dwFlags`  
 作成フラグは、次の値の任意の数を含む結合演算を使用して、or 演算子。  
  
- **CF_SELECTCONVERTTO**  ダイアログ ボックスが呼び出されたときに、変換 ラジオ ボタンをクリックした状態を指定します。 既定値です。  
  
- **CF_SELECTACTIVATEAS**  ダイアログ ボックスが呼び出されたときに、オプション ボタンを最初に選択することを指定します。  
  
- **CF_SETCONVERTDEFAULT**を指定するクラスが**CLSID**で指定された、 **clsidConvertDefault**のメンバー、`m_cv`構造体は、既定の選択として使用されますクラスのリストに変換するには、オプション ボタンとボックスが選択されます。  
  
- **CF_SETACTIVATEDEFAULT**を指定するクラスが**CLSID**で指定された、 **clsidActivateDefault**のメンバー、`m_cv`構造体は、既定値として使用されますオプション ボタンを選択すると、クラスのリスト ボックスで選択します。  
  
- **CF_SHOWHELPBUTTON**  ダイアログ ボックスが呼び出されたときに、ヘルプ ボタンを表示するように指定します。  
  
 `pClassID`  
 アクティブ化または変換する項目の CLSID を指します。 場合**NULL**、 **CLSID**に関連付けられている`pItem`使用されます。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ ボックスの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。  
  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424)と[OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657)構造体。  
  
##  <a name="doconvert"></a>  COleConvertDialog::DoConvert  
 正常に復帰した後、この関数を呼び出す[DoModal](#domodal)に変換または型のオブジェクトをアクティブ化するか、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)です。  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 アクティブ化または変換する項目へのポインター。 ことはできません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 項目を変換または変換 ダイアログ ボックスでユーザーが選択されている情報に従ってアクティブにします。  
  
##  <a name="domodal"></a>  COleConvertDialog::DoModal  
 OLE 変換 ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出し、返される、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) Windows SDK 内の関数。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定してさまざまなダイアログ ボックスのコントロールを初期化する場合、 [m_cv](#m_cv)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**設定や、ダイアログ ボックスに、ユーザーが入力した情報を取得する関数の他のメンバーを呼び出すことができます。  
  
##  <a name="getclassid"></a>  COleConvertDialog::GetClassID  
 取得するには、この関数を呼び出して、 **CLSID**変換 ダイアログ ボックスで選択された項目に関連付けられています。  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **CLSID**変換 ダイアログ ボックスで選択した項目に関連付けられています。  
  
### <a name="remarks"></a>コメント  
 後にこの関数の呼び出し[DoModal](#domodal)返します**IDOK**です。  
  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK に含まれています。  
  
##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect  
 ユーザーがアイコンとして選択した項目を表示する選択したかどうかを判断するには、この関数を呼び出します。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、オブジェクトを表示するために必要です。  
  
- `DVASPECT_CONTENT` アイコンで表示 チェック ボックスがオフかどうかに返されます。  
  
- `DVASPECT_ICON` アイコンで表示 チェック ボックスがオンになっているかどうかに返されます。  
  
### <a name="remarks"></a>コメント  
 後にこの関数の呼び出し[DoModal](#domodal)返します**IDOK**です。  
  
 アスペクトの描画の詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内のデータ構造です。  
  
##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile  
 この関数では、選択した項目のアイコンの外観を含むメタファイルへのハンドルを取得します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択して、ダイアログ ボックスが破棄されたときにオンの場合はアイコンで表示 チェック ボックスが選択した項目のアイコンの外観を持つメタファイル ハンドル**OK**それ以外の**NULL**です。  
  
##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType  
 [変換] ダイアログ ボックスで選択した変換の種類を確認するには、この関数を呼び出します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択内容の種類です。  
  
### <a name="remarks"></a>コメント  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COleConvertDialog`クラスです。  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 これらの値の簡単な説明に従ってください。  
  
- **COleConvertDialog::noConversion**かどうか ダイアログ ボックスがキャンセルされたか、ユーザーが選択されていない変換が返されます。 場合`COleConvertDialog::DoModal`返される**IDOK**ユーザーに、1 つ選択したものとは異なるアイコンが選択されていることはできます。  
  
- **COleConvertDialog::convertItem**ユーザーに変換する別の項目を選択した変換 ラジオ ボタンが選択した場合、返されると`DoModal`返される**IDOK**です。  
  
- **COleConvertDialog::activateAs**をアクティブ化すると、別のアイテムをユーザーが選択したオプション ボタンが選択した場合、返されると`DoModal`返される**IDOK**です。  
  
##  <a name="m_cv"></a>  COleConvertDialog::m_cv  
 型の構造体**OLEUICONVERT**変換 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、 [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Windows SDK 内の構造。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
