---
title: CFontDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
dev_langs:
- C++
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff998b8be93d1248775d49bcef7680f4c9777fd4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953676"
---
# <a name="cfontdialog-class"></a>CFontDialog クラス
フォントの選択 ダイアログ ボックスをアプリケーションに組み込むことができます。  
  
## <a name="syntax"></a>構文  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](#cfontdialog)|`CFontDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFontDialog::DoModal](#domodal)|ダイアログを表示および選択を行うことができます。|  
|[CFontDialog::GetCharFormat](#getcharformat)|選択したフォントの文字の書式設定を取得します。|  
|[CFontDialog::GetColor](#getcolor)|選択したフォントの色を返します。|  
|[CFontDialog::GetCurrentFont](#getcurrentfont)|現在選択されているフォントの特性を割り当てます、`LOGFONT`構造体。|  
|[CFontDialog::GetFaceName](#getfacename)|選択したフォントの書体名を返します。|  
|[CFontDialog::GetSize](#getsize)|選択したフォントのポイント サイズを返します。|  
|[CFontDialog::GetStyleName](#getstylename)|選択したフォントのスタイル名を返します。|  
|[CFontDialog::GetWeight](#getweight)|選択したフォントの太さを返します。|  
|[CFontDialog::IsBold](#isbold)|フォントが太字かどうかを判断します。|  
|[CFontDialog::IsItalic](#isitalic)|フォントが斜体かどうかを判断します。|  
|[CFontDialog::IsStrikeOut](#isstrikeout)|取り消し線付きで表示されているかどうかを判断します。|  
|[CFontDialog::IsUnderline](#isunderline)|フォントに下線が引かれているかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFontDialog::m_cf](#m_cf)|カスタマイズに使用される構造体、`CFontDialog`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 A`CFontDialog`オブジェクトは、システムに現在インストールされているフォントの一覧がダイアログ ボックス。 ユーザーはリストから、特定のフォントを選択することができ、このオプションを選択し、報告をアプリケーションにします。  
  
 構築するために、`CFontDialog`オブジェクト、指定されたコンス トラクターを使用して、新しいサブクラスを派生させるや独自のカスタム コンス トラクターを使用します。  
  
 1 回、`CFontDialog`オブジェクトが構築された、使用することができます、`m_cf`値やダイアログ ボックスのコントロールの状態を初期化するためにします。 [構造体](#m_cf)構造体は型[CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832)です。 この構造体の詳細については、Windows SDK を参照してください。  
  
 ダイアログ オブジェクトのコントロールを初期化した後、 `DoModal`  ダイアログ ボックスが表示され、フォントを選択するユーザーを許可するメンバー関数。 `DoModal` ユーザーが、[ok] を選択するかどうかを返します ( **IDOK**) か、またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`返します**IDOK**のいずれかを使用することができます`CFontDialog`のユーザーが入力情報を取得するメンバー関数。  
  
 Windows を使用する[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)関数およびエラーに関する詳細については、ダイアログ ボックスの初期化中にエラーが発生するかどうかを決定します。 この関数の詳細については、Windows SDK を参照してください。  
  
 `CFontDialog` COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするからクラスを派生`CFontDialog`拡張コントロールから通知メッセージを処理するメッセージ マップの追加を独自のダイアログ テンプレートを提供します。 基本クラスには、処理されないメッセージを渡す必要があります。  
  
 フック関数をカスタマイズする必要はありません。  
  
 使用する方法についての`CFontDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="cfontdialog"></a>  CFontDialog::CFontDialog  
 `CFontDialog` オブジェクトを構築します。  
  
```  
CFontDialog(
    LPLOGFONT lplfInitial = NULL,  
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,  
    DWORD dwFlags = CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 *plfInitial*  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)フォントの特性の一部を設定できるようにするデータ構造体。  
  
 *charFormat*  
 ポインター、 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)エディット コントロールのデータ構造を機能豊富なフォントの特性のいくつかを設定することができます。  
  
 *dwFlags*  
 1 つ以上のフォント選択フラグを指定します。 ビットごとの OR 演算子を使用して、1 つ以上の事前設定値を組み合わせることができます。 `m_cf.Flag`s 構造体メンバーを変更する場合は、変更内容でビットごとの OR 演算子を使用して、既定の動作をそのままにします。 詳細については、これらのフラグは、の説明を参照して、 [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) Windows SDK 内の構造。  
  
 *pdcPrinter*  
 プリンター デバイス コンテキストへのポインター。 指定すると、このパラメーターはフォントが選択されるプリンターのプリンター デバイス コンテキストを指します。  
  
 *pParentWnd*  
 フォント ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="remarks"></a>Remarks  
 `CHOOSEFONT` 構造体のメンバーはコンストラクターによって自動的に入力されることに注意してください。 既定とは異なるフォント ダイアログが必要な場合にのみ、これらを変更する必要があります。  
  
> [!NOTE]
>  この関数の最初のバージョンは、リッチ エディット コントロールのサポートがない場合にのみ存在します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CFontDialog::DoModal  
 この関数では、Windows に共通の [フォント] ダイアログ ボックスを表示し、ユーザーがフォントを選択できます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**です。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断する関数。  
  
 **IDOK**と**IDCANCEL**ユーザーが、[ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>Remarks  
 メンバーを設定して、さまざまなフォント ダイアログ コントロールを初期化する場合、[構造体](#m_cf)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**、他のメンバーは、ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数で呼び出すことができます。  
  
### <a name="example"></a>例  
  例を参照して[CFontDialog::CFontDialog](#cfontdialog)と[CFontDialog::GetColor](#getcolor)です。  
  
##  <a name="getcharformat"></a>  CFontDialog::GetCharFormat  
 選択したフォントの文字の書式設定を取得します。  
  
```  
void GetCharFormat(CHARFORMAT& cf) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *cf*  
 A [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)選択したフォントの文字の書式設定に関する情報を含む構造体。  
  
##  <a name="getcolor"></a>  CFontDialog::GetColor  
 選択したフォントの色を取得するには、この関数を呼び出します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントの色。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]  
  
##  <a name="getcurrentfont"></a>  CFontDialog::GetCurrentFont  
 メンバーに現在選択されているフォントの特性を割り当てるには、この関数を呼び出して、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
```  
void GetCurrentFont(LPLOGFONT lplf);
```  
  
### <a name="parameters"></a>パラメーター  
 *lplf*  
 ポインター、`LOGFONT`構造体。  
  
### <a name="remarks"></a>Remarks  
 その他の`CFontDialog`現在のフォントの特性を個別にアクセスするメンバー関数が用意されています。  
  
 呼び出し中にこの関数が呼び出された場合[DoModal](#domodal)時に現在の選択範囲を返します (新機能、ユーザーが入れ替わったりがダイアログ ボックスで変更されました)。 呼び出しの後にこの関数が呼び出された場合`DoModal`(場合にのみ、`DoModal`返します**IDOK**)、ユーザーが実際に選択したを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]  
  
##  <a name="getfacename"></a>  CFontDialog::GetFaceName  
 選択したフォントの書体名を取得するには、この関数を呼び出します。  
  
```  
CString GetFaceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択されたフォント フェイス名、 `CFontDialog`  ダイアログ ボックス。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]  
  
##  <a name="getsize"></a>  CFontDialog::GetSize  
 この関数では、選択したフォントのサイズを取得します。  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フォントのサイズ、ポイントの部分の 1/10。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]  
  
##  <a name="getstylename"></a>  CFontDialog::GetStyleName  
 この関数では、選択したフォントのスタイル名を取得します。  
  
```  
CString GetStyleName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フォントのスタイル名。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]  
  
##  <a name="getweight"></a>  CFontDialog::GetWeight  
 この関数では、選択したフォントの太さを取得します。  
  
```  
int GetWeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントの太さ。  
  
### <a name="remarks"></a>Remarks  
 フォントの太さの詳細については、次を参照してください。 [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]  
  
##  <a name="isbold"></a>  CFontDialog::IsBold  
 この関数では、選択したフォントが太字かを判断します。  
  
```  
BOOL IsBold() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントが太字の特性が有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]  
  
##  <a name="isitalic"></a>  CFontDialog::IsItalic  
 この関数では、選択したフォントが斜体かを判断します。  
  
```  
BOOL IsItalic() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントが斜体の特性が有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]  
  
##  <a name="isstrikeout"></a>  CFontDialog::IsStrikeOut  
 選択したフォントが取り消し線付きで表示されるかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL IsStrikeOut() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントに取り消し線特性が有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]  
  
##  <a name="isunderline"></a>  CFontDialog::IsUnderline  
 選択したフォントに下線を付けるかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL IsUnderline() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントが有効である下線の特性を持つ場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]  
  
##  <a name="m_cf"></a>  CFontDialog::m_cf  
 メンバーのダイアログ オブジェクトの特性を格納する構造体。  
  
```  
CHOOSEFONT m_cf;  
```  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CFontDialog`オブジェクトを使用する`m_cf`を呼び出す前に ダイアログ ボックスのさまざまな側面を変更する、`DoModal`メンバー関数。 この構造体の詳細については、次を参照してください。 [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



