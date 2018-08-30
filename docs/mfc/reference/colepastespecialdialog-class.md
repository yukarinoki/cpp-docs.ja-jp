---
title: COlePasteSpecialDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
dev_langs:
- C++
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c3dff52e3607125493c956d46e1bd38c399565e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213340"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog クラス
OLE の [形式を選択して貼り付け] ダイアログ ボックス用に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|`COlePasteSpecialDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|アプリケーションで貼り付けできる形式の一覧には、カスタム書式を追加します。|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|サポートされているクリップボード形式の一覧に新しいエントリを追加します。|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|CF_BITMAP、CF_DIB、CF_METAFILEPICT を追加し、必要に応じて CF_LINKSOURCE 形式の一覧にアプリケーションに貼り付けることができます。|  
|[静的オブジェクト](#createitem)|指定した形式を使用して、コンテナーのドキュメントで、項目を作成します。|  
|[COlePasteSpecialDialog::DoModal](#domodal)|貼り付け特別なダイアログ ボックスが表示されます。|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|かどうかのアイテムをアイコンとして描画するかどうかを指示します。|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|この項目の象徴的な形式に関連付けられているメタファイルを識別するハンドルを取得します。|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|使用可能な貼り付けのオプションのユーザーによって選択されたインデックスを取得します。|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|選択の種類を取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|コントロールをダイアログ ボックスの機能を選択して貼り付け型の構造体。|  
  
## <a name="remarks"></a>Remarks  
 クラスのオブジェクトを作成`COlePasteSpecialDialog`をこのダイアログ ボックスを呼び出す場合します。 後に、`COlePasteSpecialDialog`オブジェクトが構築された、使用することができます、 [AddFormat](#addformat)と[AddStandardFormats](#addstandardformats)  ダイアログ ボックスに、クリップボードの形式を追加するメンバー関数。 使用することも、[塗りつぶす対象となる](#m_ps)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_ps`構造体には、型を選択して貼り付けします。  
  
 詳細については、次を参照してください。、[選択して貼り付け](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipastespeciala)Windows SDK の構造体。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="addformat"></a>  COlePasteSpecialDialog::AddFormat  
 貼り付け操作で、アプリケーションがサポートできる形式の一覧に新しい形式を追加するには、この関数を呼び出します。  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>パラメーター  
 *fmt*  
 追加するデータ型への参照。  
  
 *lpszFormat*  
 ユーザーに形式を説明する文字列。  
  
 *lpszResult*  
 この形式をダイアログ ボックスで選択した場合、結果を説明する文字列。  
  
 *flags*  
 さまざまなリンクと埋め込みこの形式の使用可能なオプションです。 このフラグは、1 つのビットごとの組み合わせや、OLEUIPASTEFLAG で別の値の列挙型。  
  
 *cf*  
 追加するクリップボード形式。  
  
 *tymed*  
 この形式で使用可能なメディアの種類。 これは、1 つのビットごとの組み合わせまたは TYMED 内の値の列挙型。  
  
 *nFormatID*  
 この形式を識別する文字列の ID。 この文字列の形式は、'\n' 文字で区切られた 2 つの文字列です。 最初の文字列で渡されると同じである、 *lpstrFormat*パラメーター、および 2 つ目のと同じでは、 *lpstrResult*パラメーター。  
  
 *bEnableIcon*  
 この形式が、リスト ボックスで選択されたときにアイコンで表示 チェック ボックスが有効かどうかを決定するフラグ。  
  
 *点滅を行う*  
 リスト ボックスで次の形式を選択するとリンクの貼り付けのオプション ボタンが有効かどうかを決定するフラグ。  
  
### <a name="remarks"></a>Remarks  
 この関数は、追加されているテキストまたは呼び出すなどの標準的な形式か、カスタム形式、アプリケーションがシステムに登録されているを呼び出すことができます。 データ オブジェクトを貼り付け、アプリケーションの詳細については、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 詳細については、次を参照してください。、 [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed)列挙型、および[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK の構造体。  
  
 詳細については、次を参照してください。、 [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) Windows SDK の種類を列挙します。  
  
##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry  
 サポートされているクリップボード形式の一覧に新しいエントリを追加します。  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>パラメーター  
 *cf*  
 追加するクリップボード形式。  
  
### <a name="return-value"></a>戻り値  
 [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag)構造体の新しいリンクのエントリの情報を格納します。  
  
##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats  
 貼り付け操作で、アプリケーションがサポートできる形式の一覧に、次のクリップボード形式を追加するには、この関数を呼び出します。  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnableLink*  
 アプリケーション CF_LINKSOURCE を形式の一覧に追加するかどうかを決定するフラグを貼り付けることができます。  
  
### <a name="remarks"></a>Remarks  
  
- CF_BITMAP  
  
- CF_DIB  
  
- CF_METAFILEPICT  
  
- **「埋め込みオブジェクト」**  
  
-   (省略可能)**「リンク元」**  
  
 これらの形式は、埋め込みとリンクをサポートするために使用されます。  
  
##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog  
 `COlePasteSpecialDialog` オブジェクトを構築します。  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 作成フラグには、次のフラグのビットごとの OR 演算子を使用して結合の任意の数が含まれています。  
  
- PSF_SELECTPASTE 指定貼り付けのオプション ボタンとなるチェック最初に、ダイアログ ボックスが呼び出された場合。 PSF_SELECTPASTELINK と組み合わせて使用することはできません。 既定値です。  
  
- PSF_SELECTPASTELINK 指定リンクの貼り付けのオプション ボタンとなるチェック最初に、ダイアログ ボックスが呼び出された場合。 PSF_SELECTPASTE と組み合わせて使用することはできません。  
  
- PSF_CHECKDISPLAYASICON 指定アイコンで表示する チェック ボックスをオンになるチェック最初にダイアログ ボックスが呼び出された場合。  
  
- PSF_SHOWHELP では、ダイアログ ボックスが呼び出されたときに、[ヘルプ] ボタンが表示されることを指定します。  
  
 *pDataObject*  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)貼り付けられます。 この値が NULL の場合は、取得、`COleDataObject`クリップボードから。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>Remarks  
 この関数は、`COlePasteSpecialDialog`オブジェクト。 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。  
  
 詳細については、次を参照してください。、 [OLEUIPASTEFLAG](/windows/desktop/api/oledlg/ne-oledlg-tagoleuipasteflag) Windows SDK の種類を列挙します。  
  
##  <a name="createitem"></a>  静的オブジェクト  
 貼り付け ダイアログ ボックスで選択された新しい項目を作成します。  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNewItem*  
 指す、`COleClientItem`インスタンス。 Nll は指定できません。  
  
### <a name="return-value"></a>戻り値  
 項目が正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は、後にのみ呼び出す必要があります[DoModal](#domodal) IDOK を返します。  
  
##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal  
 貼り付け特別なダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの完了ステータス。 次のいずれかの値です。  
  
- IDOK ダイアログ ボックスが正常に表示されている場合。  
  
- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。  
  
- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、`COleDialog::GetLastError`発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、[選択して貼り付け](/windows/desktop/api/oledlg/nf-oledlg-oleuipastespeciala)Windows SDK 内の関数。  
  
### <a name="remarks"></a>Remarks  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[塗りつぶす対象となる](#m_ps)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します IDOK、他のメンバー、ダイアログ ボックスに、設定やユーザーによって入力された情報を取得する関数を呼び出すことができます。  
  
##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect  
 ユーザーがアイコンとして選択した項目を表示する選択したかどうかを決定します。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、オブジェクトを表示するために必要です。  
  
- アイコンで表示する チェック ボックスをオンしていなかった場合に返される DVASPECT_CONTENT ダイアログ ボックスが終了したときにチェックされます。  
  
- ダイアログ ボックスを閉じたときにアイコンで表示のチェック ボックスがオンの場合、DVASPECT_ICON が返されます。  
  
### <a name="remarks"></a>Remarks  
 この関数の後にのみ呼び出す[DoModal](#domodal) IDOK を返します。  
  
 描画の側面の詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK の構造体。  
  
##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile  
 ユーザーが選択した項目に関連付けられているメタファイルを取得します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択してダイアログ ボックスを閉じたときにアイコンで表示 チェック ボックスが選択された場合は、選択した項目のアイコンの外観を含むメタファイルを識別するハンドル**OK**null それ以外の場合。  
  
##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex  
 取得、ユーザーが選択したエントリに関連付けられているインデックス値。  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列のインデックス`OLEUIPASTEENTRY`ユーザーによって選択された構造体。 貼り付け操作を実行するときに、選択されたインデックスに対応する形式を使用する必要があります。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、 [OLEUIPASTEENTRY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipasteentrya) Windows SDK の構造体。  
  
##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType  
 ユーザーの選択の種類を決定します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択された型を返します。  
  
### <a name="remarks"></a>Remarks  
 戻り値の型の値がで指定された、`Selection`で宣言された列挙型、`COlePasteSpecialDialog`クラス。  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 次にこれらの値の簡単に説明します  
  
- `COlePasteSpecialDialog::pasteLink` リンクの貼り付けのラジオ ボタンが選択されましたが、選択した形式は、標準の OLE 形式です。  
  
- `COlePasteSpecialDialog::pasteNormal` 貼り付けのラジオ ボタンが選択されましたが、選択した形式は、標準の OLE 形式です。  
  
- `COlePasteSpecialDialog::pasteOther` 選択した形式は、標準の OLE 形式ではありません。  
  
- `COlePasteSpecialDialog::pasteStatic` 選択した形式では、メタファイルをしました。  
  
##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps  
 選択して貼り付け型の構造体の貼り付け ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Remarks  
 この構造体のメンバーは、直接またはメンバー関数を使用して変更できます。  
  
 詳細については、次を参照してください。、[選択して貼り付け](/windows/desktop/api/oledlg/ns-oledlg-tagoleuipastespeciala)Windows SDK の構造体。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
