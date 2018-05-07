---
title: プロパティ ページ (MFC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0895cd22870b3a4a266e9be12f0000fae7f7101a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="property-pages-mfc"></a>プロパティ ページ (MFC)
プロパティ ページでは、表示およびダイアログ データ エクス (チェンジ DDX) に基づくデータ マッピング メカニズムをサポートすることによって編集用のカスタマイズ可能なグラフィカル インターフェイスで特定の OLE コントロール プロパティの現在の値が表示されます。  
  
 このデータ マッピング メカニズムは、プロパティ ページのコントロールを OLE コントロールの個々 のプロパティにマップします。 コントロールのプロパティの値には、状態やプロパティ ページのコントロールの内容が反映されます。 プロパティ ページのコントロールとプロパティ間のマッピングがで指定された**ddp _** 関数呼び出しにプロパティ ページの`DoDataExchange`メンバー関数。 次の一覧は**ddp _** コントロールのプロパティ ページを使用して入力データを交換する関数。  
  
### <a name="property-page-data-transfer"></a>プロパティ ページのデータ転送  
  
|||  
|-|-|  
|[DDP_CBIndex](#ddp_cbindex)|コントロールのプロパティを持つコンボ ボックスで選択した文字列のインデックスをリンクします。|  
|[DDP_CBString](#ddp_cbstring)|コントロールのプロパティを持つコンボ ボックスで選択された文字列をリンクします。 選択された文字列は、プロパティの値と同じ文字で始まることができますが、完全に一致する必要はありません。|  
|[DDP_CBStringExact](#ddp_cbstringexact)|コントロールのプロパティを持つコンボ ボックスで選択された文字列をリンクします。 選択した文字列とプロパティの文字列値が正確に一致する必要があります。|  
|[DDP_Check](#ddp_check)|コントロールのプロパティを使用して、コントロールのプロパティ ページでチェック ボックスをリンクします。|  
|[DDP_LBIndex](#ddp_lbindex)|コントロールのプロパティを使用して、リスト ボックスで選択した文字列のインデックスをリンクします。|  
|[DDP_LBString](#ddp_lbstring)|コントロールのプロパティを使用して、リスト ボックスで選択された文字列をリンクします。 選択された文字列は、プロパティの値と同じ文字で始まることができますが、完全には一致しなくてもかまいません。|  
|[DDP_LBStringExact](#ddp_lbstringexact)|コントロールのプロパティを使用して、リスト ボックスで選択された文字列をリンクします。 選択した文字列とプロパティの文字列値が正確に一致する必要があります。|  
|[DDP_PostProcessing](#ddp_postprocessing)|コントロールからプロパティ値の転送を完了します。|  
|[DDP_Radio](#ddp_radio)|リンク コントロールのプロパティを使用して、コントロールのプロパティ ページでのラジオ ボタン グループです。|  
|[DDP_Text](#ddp_text)|コントロールのプロパティを使用して、コントロールのプロパティ ページ内のコントロールをリンクします。 この関数はさまざまな種類のプロパティの処理など**二重**、**短い**、 `BSTR`、および**長い**です。|  
  
 詳細については、`DoDataExchange`関数とプロパティ ページでは、記事を参照して[ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)です。  
  
 作成および OLE コントロールのプロパティ ページの管理に使用されるマクロの一覧を次に示します。  
  
### <a name="property-pages"></a>プロパティ ページ  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|プロパティ ページ Id の一覧を開始します。|  
|[END_PROPPAGEIDS](#end_proppageids)|プロパティ ページ Id のリストを終了します。|  
|[PROPPAGEID](#proppageid)|コントロールのクラスのプロパティ ページを宣言します。|  
  
##  <a name="ddp_cbindex"></a>  DDP_CBIndex  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`プロパティ ページにコンボ ボックス内の現在の選択範囲のインデックスを持つ整数のプロパティの値を同期するために機能します。  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 コンボ ボックスのリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボックス`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたコンボ ボックス コントロールと交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_CBIndex`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_cbstring"></a>  DDP_CBString  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`プロパティ ページで、コンボ ボックスで、現在の選択内容の文字列プロパティの値を同期するために機能します。  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 コンボ ボックスのリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボックス`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたコンボ ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_CBString`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`プロパティ ページのコンボ ボックスの現在の選択を正確に一致する文字列プロパティの値を同期するために機能します。  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 コンボ ボックスのリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボックス`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたコンボ ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_CBStringExact`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_check"></a>  DDP_Check  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`関連付けられているプロパティ ページ チェック ボックス コントロールでプロパティの値を同期するために機能します。  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 指定されたコントロールのプロパティに関連付けられているチェック ボックス コントロールのリソース ID`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたチェック ボックス コントロールと交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_Check`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_lbindex"></a>  DDP_LBIndex  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`プロパティ ページにあるリスト ボックスで現在の選択範囲のインデックスを持つ整数のプロパティの値を同期するために機能します。  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 一覧のリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボックス`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたリスト ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_LBIndex`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_lbstring"></a>  DDP_LBString  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`プロパティ ページにあるリスト ボックスで、現在の選択内容の文字列プロパティの値を同期するために機能します。  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 一覧のリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボックス`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたリスト ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_LBString`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`プロパティ ページにあるリスト ボックスの現在の選択を正確に一致する文字列プロパティの値を同期するために機能します。  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 一覧のリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボックス`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたリスト ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_LBStringExact`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing  
 プロパティ ページのこの関数を呼び出す`DoDataExchange`関数、プロパティの値が保存されるときに、プロパティ ページから、コントロールへのプロパティの値の転送を完了します。  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
### <a name="remarks"></a>コメント  
 すべてのデータ交換関数が完了した後は、この関数を呼び出す必要があります。 例えば:  
  
 [!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_radio"></a>  DDP_Radio  
 コントロールのこの関数を呼び出す`DoPropExchange`関連付けられているプロパティ ページのオプション ボタン コントロールとプロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 無線のリソース ID で指定されたコントロールのプロパティに関連付けられたコントロールのボタン`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたオプション ボタン コントロールと交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_Radio`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="ddp_text"></a>  DDP_Text  
 コントロールのこの関数を呼び出す`DoDataExchange`関連付けられているプロパティ ページのコントロールでプロパティの値を同期するために機能します。  
  
```   
void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    BYTE & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    UINT & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    long & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    DWORD & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    float & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    double & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    CString & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 指定されたコントロールのプロパティに関連付けられたコントロールのリソース ID`pszPropName`です。  
  
 `member`  
 指定されたプロパティのページ コントロールに関連付けられているメンバー変数`id`によって指定されたプロパティおよび`pszPropName`です。  
  
 `pszPropName`  
 指定されたコントロールと交換するコントロール プロパティのプロパティ名`id`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_Text`関数呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS  
 コントロールのプロパティ ページ Id のリストの定義を開始します。  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 ページが指定されているプロパティ、コントロール クラスの名前。  
  
 *count*  
 コントロール クラスによって使用されるプロパティ ページの数。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイル、プロパティ ページの一覧でを起動、`BEGIN_PROPPAGEIDS`マクロ、[プロパティ ページ] の各マクロ エントリを追加しのプロパティ ページの一覧を完了、`END_PROPPAGEIDS`マクロです。  
  
 プロパティ ページの詳細については、記事を参照してください。 [ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="end_proppageids"></a>  END_PROPPAGEIDS  
 プロパティ ページ ID のリストの定義を終了します。  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 プロパティ ページを所有するコントロール クラスの名前。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="proppageid"></a>  PROPPAGEID  
 OLE コントロールが使用するためのプロパティ ページを追加します。  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 プロパティ ページの一意のクラス ID。  
  
### <a name="remarks"></a>コメント  
 すべて`PROPPAGEID`マクロは、間に配置する必要があります、`BEGIN_PROPPAGEIDS`と`END_PROPPAGEIDS`コントロールの実装ファイル内のマクロです。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
