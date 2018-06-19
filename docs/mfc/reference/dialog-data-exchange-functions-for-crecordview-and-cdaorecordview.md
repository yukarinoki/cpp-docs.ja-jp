---
title: CRecordView と CDaoRecordView のダイアログ データ交換関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 538acbf4e12c1d18e8d07337c6f428a0a0dc4b1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377518"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数
このトピックの間でデータの交換に使用するための DDX_Field 関数を一覧表示、 [CRecordset](../../mfc/reference/crecordset-class.md)と[CRecordView](../../mfc/reference/crecordview-class.md)フォームまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フォーム。  
  
> [!NOTE]
>  DDX_Field 関数は、DDX 関数と同様に、フォームのコントロールにデータを交換します。 DDX とは異なり、レコード ビュー自体のフィールドではなく、ビューの関連するレコード セット オブジェクトのフィールドでデータを交換します。 詳細については、クラスを参照してください。`CRecordView`と`CDaoRecordView`です。  
  
### <a name="ddxfield-functions"></a>DDX_Field 関数  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|レコード セット フィールド データ メンバーと、インデックス内のコンボ ボックスに現在の選択範囲の間で整数データを転送する[CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)です。|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|転送`CString`コンボのエディット コントロールとレコード セット フィールド データ メンバーの間でデータのボックスに、`CRecordView`または`CDaoRecordView`です。 レコード セットからデータをコントロールに移動するときに、この関数は、指定した文字列内の文字で始まるコンボ ボックスで項目を選択します。|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|転送`CString`コンボのエディット コントロールとレコード セット フィールド データ メンバーの間でデータのボックスに、`CRecordView`または`CDaoRecordView`です。 レコード セットからデータをコントロールに移動するときに、この関数は、指定した文字列と一致するコンボ ボックスで、項目を選択します。|  
|[DDX_FieldCheck](#ddx_fieldcheck)|レコード セット フィールド データ メンバーと内のチェック ボックス間でのブール型のデータの転送、`CRecordView`または`CDaoRecordView`です。|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|レコード セット フィールド データ メンバーと、リスト ボックスで現在の選択範囲のインデックスの間で整数のデータ転送、`CRecordView`または`CDaoRecordView`です。|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|転送を受け持ち[CString](../../atl-mfc-shared/reference/cstringt-class.md)リスト ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータ。 レコード セットからデータをコントロールに移動するときに、この関数は、指定した文字列内の文字で始まるリスト ボックスで項目を選択します。|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|転送を受け持ち`CString`リスト ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータ。 レコード セットからデータをコントロールに移動するときに、この関数は、指定した文字列と一致する最初の項目を選択します。|  
|[DDX_FieldRadio](#ddx_fieldradio)|レコード セット フィールド データ メンバーとのラジオ ボタンのグループ間で整数データを転送する`CRecordView`または`CDaoRecordView`です。|  
|[DDX_FieldScroll](#ddx_fieldscroll)|スクロール バー コントロールのスクロール位置を取得または設定、`CRecordView`または`CDaoRecordView`です。 呼び出す、 [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)関数。|  
|[DDX_FieldSlider](#ddx_fieldslider)|レコード ビュー内のスライダー コントロールのつまみの位置を同期し、`int`レコード セットのフィールド データ メンバーです。 |
|[DDX_FieldText](#ddx_fieldtext)|オーバー ロードされたバージョンは、転送に使用できる`int`、 **UINT**、**長い**、 `DWORD`、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 **float**、**二重**、**短い**、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)レコード セット フィールド データ メンバーと編集の間でデータボックスに、`CRecordView`または`CDaoRecordView`です。|  
  
##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex  
 `DDX_FieldCBIndex`関数は、レコード ビュー内のコンボ ボックス コントロールのリスト ボックス コントロールで選択した項目のインデックスを同期し、`int`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *index*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定された値に基づいてコントロールの選択を設定するレコード セットからデータをコントロールに移動するときに*インデックス*です。 レコード セットからコントロールへの転送では、レコード セットのフィールドが Null の場合、MFC を設定、インデックスの値を 0 にします。 コントロールからレコード セットへの転送時にコントロールが空の場合、または項目が選択されていない場合は、レコード セットのフィールドは 0 に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 この例はのようになります`DDX_FieldCBIndex`です。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString  
 `DDX_FieldCBString`関数の転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビュー内のコンボ ボックス コントロールのエディット コントロールの間でデータと`CString`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定された文字列内の文字で始まる最初の行に、コンボ ボックスの現在の選択範囲を設定、レコード セットからデータをコントロールに移動するときに*値*です。 レコード セットから、コントロールへの転送にレコード セットのフィールドが Null の場合は、コンボ ボックスからの選択は解除し、コンボ ボックスの編集コントロールの設定を空にします。 コントロールからレコード セットへの転送時にコントロールが空の場合、レコード セットのフィールドは Null に設定フィールドで許可される場合。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 この例への呼び出しが含まれています。`DDX_FieldCBString`です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact  
 `DDX_FieldCBStringExact`関数の転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビュー内のコンボ ボックス コントロールのエディット コントロールの間でデータと`CString`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定した文字列と一致する最初の行に、コンボ ボックスの現在の選択範囲を設定、レコード セットからデータをコントロールに移動するときに*値*です。 レコード セットから、コントロールへの転送のレコード セットのフィールドが NULL の場合は、コンボ ボックスからの選択は解除し、コンボ ボックスの編集ボックスの設定を空にします。 コントロールからレコード セットへの転送時にコントロールが、空の場合は、レコード セットのフィールドは NULL に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 呼び出す`DDX_FieldCBStringExact`になります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck  
 `DDX_FieldCheck`関数の転送を管理`int` ダイアログ ボックスでは、チェック ボックス コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているチェック ボックス コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_FieldCheck`が呼び出されると、*値*] チェック ボックス コントロールの現在の状態に設定されているコントロールの状態が [に設定されているまたは*値*転送の方向に応じて、します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex  
 `DDX_FieldLBIndex`関数は、レコード ビュー内のリスト ボックス コントロールで選択した項目のインデックスを同期し、`int`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *index*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定された値に基づいてコントロールの選択を設定するレコード セットからデータをコントロールに移動するときに*インデックス*です。 レコード セットからコントロールへの転送では、レコード セットのフィールドが Null の場合、MFC を設定、インデックスの値を 0 にします。 コントロールからレコード セットへの転送時にコントロールが空の場合は、レコード セットのフィールドは 0 に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString  
 `DDX_FieldLBString`レコード ビューにリスト ボックス コントロールの現在の選択範囲をコピー、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 逆の方向でこの関数がで指定された文字列内の文字で始まる最初の行にあるリスト ボックスで現在の選択範囲を設定*値*です。 レコード セットからコントロールへの転送でレコード セットのフィールドが Null の場合、選択内容が、リスト ボックスから削除されます。 コントロールからレコード セットへの転送時にコントロールが、空の場合は、レコード セットのフィールドは Null に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 呼び出す`DDX_FieldLBString`になります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact  
 `DDX_FieldLBStringExact`関数では、リスト ボックス コントロールの現在の選択範囲をコピーするレコード ビュー内、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 逆の方向でこの関数がで指定した文字列と一致する最初の行にあるリスト ボックスで現在の選択範囲を設定*値*です。 レコード セットからコントロールへの転送でレコード セットのフィールドが Null の場合、選択内容が、リスト ボックスから削除されます。 コントロールからレコード セットへの転送時にコントロールが、空の場合は、レコード セットのフィールドは Null に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 呼び出す`DDX_FieldLBStringExact`になります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio  
 `DDX_FieldRadio`関数は、0 から始まる`int`レコード ビューのラジオ ボタンのグループ内の現在選択されているオプション ボタンを持つレコード ビューのレコード セットのメンバー変数。  
  
```  
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 最初の ID でグループ (スタイルを**WS_GROUP**) にある隣接するラジオ ボタン コントロールの[CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 レコード セット フィールドからビューに転送する際に、この関数がオン、 *n 番目*(0 から始まる) ラジオ ボタンをクリックし、他のボタンを無効にします。 逆方向には、この関数は、現在 (チェック) 上にあるラジオ ボタンの序数をレコード セットのフィールドを設定します。 レコード セットからコントロールへの転送のレコード セットのフィールドが Null の場合、ボタンが選択されていません。 コントロールからレコード セットへの転送にコントロールが選択されていない場合、レコード セットのフィールドは Null に設定フィールドが許可されている場合。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 呼び出す`DDX_FieldRadio`になります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll  
 `DDX_FieldScroll`関数は、レコード ビュー内のスクロール バー コントロールのスクロール位置を同期し、`int`レコード ビュー (またはに関連付けられた整数変数にマップする) レコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 最初の ID でグループ (スタイルを**WS_GROUP**) にある隣接するラジオ ボタン コントロールの[CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定された値にスクロール バー コントロールのスクロール位置を設定するレコード セットからデータをコントロールに移動するときに*値*です。 レコード セットからコントロールへの転送のレコード セットのフィールドが Null の場合は、スクロール バー コントロールは 0 に設定します。 コントロールからレコード セットへの転送時にコントロールが空の場合、レコード セットのフィールドの値は 0 です。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 呼び出す`DDX_FieldScroll`になります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>name="ddx_fieldslider"></a>  DDX_FieldSlider
`DDX_FieldSlider`関数は、レコード ビュー内のスライダー コントロールのつまみの位置を同期し、`int`レコード ビュー (またはに関連付けられた整数変数にマップする) レコード セットのフィールド データ メンバーです。  
   
### <a name="syntax"></a>構文  
  ```
   void AFXAPI DDX_FieldSlider(  
       CDataExchange* pDX,  
       int nIDC,  
       int& value,  
       CRecordset* pRecordset );  

void AFXAPI DDX_FieldSlider(  
     CDataExchange* pDX,  
     int nIDC,  
     int& value,  
     CDaoRecordset* pRecordset );  
```
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 スライダー コントロールのリソース ID です。  
  
 *値*  
 交換する値への参照。 このパラメーターには、スライダー コントロールのつまみの現在の位置を設定するために使用されますか。  
  
 `pRecordset`  
 関連付けられたへのポインター`CRecordset`または`CDaoRecordset`オブジェクトを使用するには、データを交換します。  
   
### <a name="remarks"></a>コメント  
 データをレコード セットから、スライダーを移動するときこの関数で指定された値をスライダーの位置を設定*値*です。 レコード セットからコントロールへの転送のレコード セットのフィールドが Null の場合は、スライダー コントロールの位置は 0 に設定します。 コントロールからレコード セットへの転送時にコントロールが空の場合、レコード セットのフィールドの値は 0 です。  
  
 `DDX_FieldSlider` スライダー コントロールの位置だけではなく、範囲を設定できると範囲の情報を交換しないしません。  
  
 ODBC ベースのクラスを使用している場合は、関数の最初のオーバーライドを使用します。 2 番目の上書きを使用して、DAO ベースのクラスを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について`CRecordView`と`CDaoRecordView`、フィールドを参照してください[レコード ビュー](../../data/record-views-mfc-data-access.md)です。 スライダー コントロールの概要については、次を参照してください。[を使用して CSliderCtrl](../using-csliderctrl.md)です。  
   
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field 例についてはします。 呼び出す`DDX_FieldSlider`になります。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
  
##  <a name="ddx_fieldtext"></a>  DDX_FieldText  
 `DDX_FieldText`関数の転送を管理`int`、**短い**、**長い**、 `DWORD`、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 **float**、**二重**、 **BOOL**、または**バイト**エディット ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータ。  
  
```  
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    UINT& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    short& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BOOL& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleDateTime& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleCurrency& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。  
  
 *値*  
 関連付けられているフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。 値のデータ型によって異なりますのどのオーバー ロードされたバージョンの`DDX_FieldText`を使用します。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。 このポインターにより`DDX_FieldText`を検出し、Null 値を設定します。  
  
### <a name="remarks"></a>コメント  
 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト、`DDX_FieldText`転送も管理[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)値。 空の編集ボックス コントロールは、Null 値を示します。 レコード セットからコントロールへの転送では、レコード セットのフィールドが Null の場合、エディット ボックスが設定を空にします。 コントロールからレコード セットへの転送時にコントロールが、空の場合は、レコード セットのフィールドは Null に設定します。  
  
 バージョンを使用して[CRecordset](../../mfc/reference/crecordset-class.md) ODBC ベースのクラスを使用している場合のパラメーターです。 バージョンを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) DAO ベースのクラスを使用している場合のパラメーターです。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールドでは、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)です。  
  
### <a name="example"></a>例  
 次`DoDataExchange`関数を[CRecordView](../../mfc/reference/crecordview-class.md)が含まれています`DDX_FieldText`関数の 3 つのデータ型: `IDC_COURSELIST` ; コンボ ボックスは、その他の 2 つのコントロールが編集ボックス。 DAO プログラミング、 *m_pSet*パラメーターへのポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)です。  
  
 [!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
