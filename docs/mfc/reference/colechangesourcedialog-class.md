---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08b4095b535724f7132a2b286ce52cb46286932b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037597"
---
# <a name="colechangesourcedialog-class"></a>メンバー クラス
OLE の [ソースの変更] ダイアログ ボックスに使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|`COleChangeSourceDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|OLE の [ソースの変更] ダイアログ ボックスが表示されます。|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|完全なソースの表示名を取得します。|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|元の名前には、ファイル名を取得します。|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|以前のソースのプレフィックスを取得します。|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|元の名前、項目の名前を取得します。|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|新しいソースのプレフィックスを取得します。|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|ソースが有効なかどうかを示します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|ダイアログ ボックスの動作を制御する構造体。|  
  
## <a name="remarks"></a>Remarks  
 クラスのオブジェクトを作成`COleChangeSourceDialog`をこのダイアログ ボックスを呼び出したいとします。 後に、`COleChangeSourceDialog`オブジェクトが構築された、使用することができます、 [m_cs](#m_cs)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_cs`構造体は型[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 内の構造。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog  
 この関数は、作成、`COleChangeSourceDialog`オブジェクト。  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pItem*  
 リンクへのポインター [COleClientItem](../../mfc/reference/coleclientitem-class.md)を更新するにはソース。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>Remarks  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造と[OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK 内の関数。  
  
##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal  
 OLE の [ソースの変更] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出し、返される、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK 内の関数。  
  
### <a name="remarks"></a>Remarks  
 メンバーを設定してさまざまなダイアログ ボックスのコントロールを初期化する場合、 [m_cs](#m_cs)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**関数、ダイアログ ボックスからユーザーが入力した設定や情報を取得するメンバーを呼び出すことができます。 次の一覧は、一般的なクエリ関数を名前します。  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName  
 リンクされたクライアント アイテムの完全な表示名を取得するには、この関数を呼び出します。  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>戻り値  
 完全なソース表示名 (モニカー)、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。  
  
##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName  
 この関数では、ファイル、項目の表示名、リンクされているクライアントのモニカー部分を取得します。  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのモニカーのソースの表示名の部分、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。  
  
### <a name="remarks"></a>Remarks  
 アイテム モニカーと共にファイル モニカーでは、完全な表示名を示します。  
  
##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix  
 この関数では、ソースの以前のプレフィックス文字列を取得します。  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>戻り値  
 ソースの以前のプレフィックス文字列。  
  
### <a name="remarks"></a>Remarks  
 後にこの関数の呼び出し[DoModal](#domodal)返します**IDOK**です。  
  
 この値は直接、 **lpszFrom**のメンバー、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 内の構造。  
  
##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName  
 リンクされているクライアント アイテムの表示名のアイテムのモニカーの部分を取得するには、この関数を呼び出します。  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>戻り値  
 ソースの表示名のアイテムのモニカーの部分、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。  
  
### <a name="remarks"></a>Remarks  
 アイテム モニカーと共にファイル モニカーでは、完全な表示名を示します。  
  
##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix  
 この関数では、ソースの新しいプレフィックス文字列を取得します。  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>戻り値  
 ソースの新しいプレフィックス文字列。  
  
### <a name="remarks"></a>Remarks  
 後にこの関数の呼び出し[DoModal](#domodal)返します**IDOK**です。  
  
 この値は直接、 **lpszTo**のメンバー、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 内の構造。  
  
##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs  
 このデータ メンバーは型の構造体[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)です。  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Remarks  
 `OLEUICHANGESOURCE` OLE の [ソースの変更] ダイアログ ボックスの動作を制御を使用します。 この構造体のメンバーを直接変更することができます。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 内の構造。  
  
##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource  
 この関数では、新しいソースが有効かを判断します。  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>戻り値  
 新しいソースは、有効な場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 後にこの関数の呼び出し[DoModal](#domodal)返します**IDOK**です。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK 内の構造。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
