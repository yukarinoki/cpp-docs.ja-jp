---
title: CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数
ms.date: 11/04/2016
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
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
ms.openlocfilehash: 2a794d16b2f94bf8ba66b6c0398dec262d8829e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322554"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数

このトピックでの間でデータを交換するために使用するための DDX_Field 関数、 [CRecordset](../../mfc/reference/crecordset-class.md)と[CRecordView](../../mfc/reference/crecordview-class.md)フォームまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フォーム。

> [!NOTE]
>  DDX_Field 関数は、DDX 関数と同様に、フォームのコントロールにデータを交換します。 ただし、DDX とは異なり、レコード ビュー自体のフィールドではなく、ビューの関連するレコード セット オブジェクトのフィールドでデータを交換します。 詳細については、クラスを参照してください。`CRecordView`と`CDaoRecordView`します。

### <a name="ddxfield-functions"></a>DDX_Field 関数

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|レコード セットのフィールド データ メンバーと、インデックスでコンボ ボックス内の現在の選択範囲の間で整数データを転送する[CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)します。|
|[DDX_FieldCBString](#ddx_fieldcbstring)|転送`CString`レコード セットのフィールド データ メンバーおよびコンボのエディット コントロールの間でデータのボックスに、`CRecordView`または`CDaoRecordView`します。 コントロールに、レコード セットからデータを移動する場合、この関数は、指定した文字列内の文字で始まるコンボ ボックスで、項目を選択します。|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|転送`CString`レコード セットのフィールド データ メンバーおよびコンボのエディット コントロールの間でデータのボックスに、`CRecordView`または`CDaoRecordView`します。 コントロールに、レコード セットからデータを移動する場合、この関数は、指定した文字列と一致するコンボ ボックスで項目を選択します。|
|[DDX_FieldCheck](#ddx_fieldcheck)|レコード セットのフィールド データ メンバーとチェック ボックスを間でのブール型のデータの転送、`CRecordView`または`CDaoRecordView`します。|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|レコード セットのフィールド データ メンバーと、リスト ボックスで現在の選択範囲のインデックス間の整数データを転送する`CRecordView`または`CDaoRecordView`します。|
|[DDX_FieldLBString](#ddx_fieldlbstring)|転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)リスト ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータ。 コントロールに、レコード セットからデータを移動する場合、この関数は、指定した文字列内の文字で始まるリスト ボックスで、項目を選択します。|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|転送を管理`CString`リスト ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータ。 コントロールに、レコード セットからデータを移動する場合、この関数は、指定した文字列と一致する最初の項目を選択します。|
|[DDX_FieldRadio](#ddx_fieldradio)|レコード セットのフィールド データ メンバーとグループのラジオ ボタンの間の整数型のデータの転送、`CRecordView`または`CDaoRecordView`します。|
|[DDX_FieldScroll](#ddx_fieldscroll)|スクロール バー コントロールのスクロール位置を取得または設定します、`CRecordView`または`CDaoRecordView`します。 呼び出し、 [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)関数。|
|[DDX_FieldSlider](#ddx_fieldslider)|レコード ビュー内のスライダー コントロールのサムネイルの位置を同期し、`int`レコード セットのフィールド データ メンバー。 |
|[DDX_FieldText](#ddx_fieldtext)|オーバー ロードされたバージョンが転送に使用できる`int`、 **UINT**、**長い**、 `DWORD`、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 **float**、**二重**、**短い**、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)レコード セットのフィールド データ メンバーと編集の間でデータボックスに、`CRecordView`または`CDaoRecordView`します。|

##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex

`DDX_FieldCBIndex`関数は、レコード ビュー内のコンボ ボックス コントロールのリスト ボックス コントロールで選択した項目のインデックスを同期し、`int`レコード ビューに関連付けられているレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*index*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

この関数がで指定された値に基づいて、コントロールの選択を設定するコントロールに、レコード セットからデータを移動する場合*インデックス*します。 レコード セットからコントロールへの転送では、レコード セットのフィールドが Null の場合 MFC 設定、インデックスの値を 0 にします。 コントロールからレコード セットへの転送時にコントロールが空の場合、または項目が選択されていない場合、レコード セット フィールドが 0 に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 例はのようになります`DDX_FieldCBIndex`します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString

`DDX_FieldCBString`関数の転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビュー内のコンボ ボックス コントロールのエディット コントロールの間でデータと`CString`レコード ビューに関連付けられているレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

コントロールに、レコード セットからデータを移動する場合に指定された文字列内の文字で始まる最初の行にコンボ ボックスの現在の選択範囲を設定します*値*します。 レコード セットから、コントロールへの転送にレコード セットのフィールドが Null の場合は、コンボ ボックスからの選択は解除し、のコンボ ボックス編集コントロールの設定を空にします。 コントロールからレコード セットへの転送時にコントロールが空の場合、レコード セット フィールドは Null に設定フィールドで許可される場合。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 例への呼び出しが含まれています`DDX_FieldCBString`します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact

`DDX_FieldCBStringExact`関数の転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビュー内のコンボ ボックス コントロールのエディット コントロールの間でデータと`CString`レコード ビューに関連付けられているレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

コントロールに、レコード セットからデータを移動する場合に指定された文字列を正確に一致する最初の行にコンボ ボックスの現在の選択範囲を設定します*値*します。 レコード セットから、コントロールへの転送にレコード セットのフィールドが NULL の場合、コンボ ボックスからの選択は解除し、コンボ ボックスの編集ボックスの設定を空にします。 コントロールからレコード セットへの転送時にコントロールが空の場合は、レコード セット フィールドは NULL に設定します。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 呼び出す`DDX_FieldCBStringExact`のようになります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck

`DDX_FieldCheck`関数の転送を管理**int**  ダイアログ ボックスでは、チェック ボックス コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**int**  ダイアログ ボックス、フォーム ビュー、またはコントロールのデータ メンバービュー オブジェクト。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールのプロパティに関連付けられているチェック ボックス コントロールのリソース ID。

*value*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータを交換するのメンバー変数への参照。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

ときに`DDX_FieldCheck`が呼び出され、*値*、チェック ボックス コントロールの現在の状態に設定されているコントロールの状態が に設定されているまたは*値*転送の方向に応じて。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex

`DDX_FieldLBIndex`関数は、レコード ビュー内のリスト ボックス コントロールで選択した項目のインデックスを同期し、 **int**レコード ビューに関連付けられているレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*index*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

この関数がで指定された値に基づいて、コントロールの選択を設定するコントロールに、レコード セットからデータを移動する場合*インデックス*します。 レコード セットからコントロールへの転送では、レコード セットのフィールドが Null の場合 MFC 設定、インデックスの値を 0 にします。 コントロールからレコード セットへの転送時にコントロールが空の場合、レコード セット フィールドが 0 に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString

`DDX_FieldLBString`にレコード ビュー内のリスト ボックス コントロールの現在の選択範囲をコピー、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビューに関連付けられているレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

逆の方向でこの関数は、リスト ボックスで指定された文字列内の文字で始まる最初の行に現在の選択範囲を設定*値*します。 レコード セットからコントロールへの転送にレコード セットのフィールドが Null の場合、選択内容が、リスト ボックスから削除されます。 コントロールからレコード セットへの転送時にコントロールが空の場合は、レコード セット フィールドは Null に設定します。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 呼び出す`DDX_FieldLBString`のようになります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact

`DDX_FieldLBStringExact`関数では、リスト ボックス コントロールの現在の選択範囲をコピーするレコード ビュー内の[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビューに関連付けられているレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

逆の方向でこの関数は、リスト ボックスで指定した文字列と一致する最初の行に現在の選択範囲を設定*値*します。 レコード セットからコントロールへの転送にレコード セットのフィールドが Null の場合、選択内容が、リスト ボックスから削除されます。 コントロールからレコード セットへの転送時にコントロールが空の場合は、レコード セット フィールドは Null に設定します。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 呼び出す`DDX_FieldLBStringExact`のようになります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio

`DDX_FieldRadio`関数は、0 から始まる**int**レコード ビューのラジオ ボタンのグループで現在選択されているラジオ ボタンで、レコード ビューのレコード セットのメンバー変数。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
最初の ID の横にあるラジオ ボタン コントロールの (スタイル WS_GROUP) でのグループに、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

レコード セット フィールドからビューに転送する際に、この関数がオン、 *n 番目*(0 から始まる) ラジオ ボタンをクリックし、その他のボタンを無効にします。 逆の方向では、この関数は、現在 (チェック) 上にあるラジオ ボタンの序数をレコード セットのフィールドを設定します。 レコード セットからコントロールへの転送で、レコード セット フィールドが Null の場合 ボタンが選択されていません。 コントロールからレコード セットへの転送時にコントロールが選択されていない場合、レコード セット フィールドは Null に設定フィールドが許可されている場合。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 呼び出す`DDX_FieldRadio`のようになります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll

`DDX_FieldScroll`関数は、レコード ビュー内のスクロール バー コントロールのスクロール位置を同期し、 **int**レコード ビュー (または整数変数にマップする) に関連付けられたレコード セットのフィールド データ メンバー.

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
最初の ID の横にあるラジオ ボタン コントロールの (スタイル WS_GROUP) でのグループに、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。

### <a name="remarks"></a>Remarks

この関数がで指定された値に、スクロール バー コントロールのスクロール位置を設定するコントロールに、レコード セットからデータを移動する場合*値*します。 レコード セットからコントロールへの転送にレコード セットのフィールドが Null の場合は、スクロール バー コントロールは 0 に設定します。 コントロールからレコード セットへの転送時にコントロールが空の場合、レコード セットのフィールドの値は 0 です。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 呼び出す`DDX_FieldScroll`のようになります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

  ## <a name="ddx_fieldslider"></a>  DDX_FieldSlider
`DDX_FieldSlider`関数は、レコード ビュー内のスライダー コントロールのサムネイルの位置を同期し、 **int**レコード ビュー (または整数変数にマップする) に関連付けられたレコード セットのフィールド データ メンバー。

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

*pDX*<br/>
ポインターを[CDataExchange](cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
スライダー コントロールのリソース ID。

*value*<br/>
交換する値への参照。 このパラメーターを保持またはスライダー コントロールのつまみの現在の位置を設定するために使用されます。

*pRecordset*<br/>
関連付けられているへのポインター`CRecordset`または`CDaoRecordset`オブジェクトを使用するには、データを交換します。

### <a name="remarks"></a>Remarks

この関数がで指定された値をスライダーの位置を設定するデータをレコード セットから、スライダーを移動する場合*値*します。 レコード セットからコントロールへの転送にレコード セットのフィールドが Null の場合は、スライダー コントロールの位置は 0 に設定します。 コントロールから、レコード セットへの転送時にコントロールが空の場合、レコード セットのフィールドの値は 0 です。

`DDX_FieldSlider` 範囲の位置だけではなく、範囲を設定できるスライダー コントロールとの情報を交換しないしません。

ODBC ベースのクラスを使用する場合は、関数の最初のオーバーライドを使用します。 DAO ベースのクラスでは、2 番目のオーバーライドを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について`CRecordView`と`CDaoRecordView`フィールドを参照してください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。 スライダー コントロールの概要については、次を参照してください。[を使用して CSliderCtrl](../using-csliderctrl.md)します。

### <a name="example"></a>例

参照してください[DDX_FieldText](#ddx_fieldtext)全般のための DDX_Field 例。 呼び出す`DDX_FieldSlider`のようになります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

##  <a name="ddx_fieldtext"></a>  DDX_FieldText

`DDX_FieldText`関数の転送を管理**int**、**短い**、**長い**、DWORD、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 **float**、**二重**、 **BOOL**、または**バイト**編集ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータ。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクト。

*value*<br/>
関連付けられているフィールド データ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクト。 値のデータ型のオーバー ロードされたバージョンのうちに依存`DDX_FieldText`を使用します。

*pRecordset*<br/>
ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データを交換するオブジェクト。 このポインターにより`DDX_FieldText`を検出し、Null 値を設定します。

### <a name="remarks"></a>Remarks

[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト、`DDX_FieldText`転送の管理も[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)値。 空の編集ボックス コントロールでは、Null 値を示します。 レコード セットからコントロールへの転送では、レコード セットのフィールドが Null の場合、編集ボックスが設定を空にします。 コントロールからレコード セットへの転送時にコントロールが空の場合は、レコード セット フィールドは Null に設定します。

バージョンを使用して[CRecordset](../../mfc/reference/crecordset-class.md) ODBC ベースのクラスを使用する場合は、パラメーター。 バージョンを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) DAO ベースのクラスを使用する場合は、パラメーター。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事をご覧ください[レコード ビュー](../../data/record-views-mfc-data-access.md)します。

### <a name="example"></a>例

次`DoDataExchange`関数を[CRecordView](../../mfc/reference/crecordview-class.md)が含まれています`DDX_FieldText`3 つのデータ型の関数を呼び出す:`IDC_COURSELIST`コンボ ボックス; は、その他の 2 つのコントロールが編集ボックス。 DAO のプログラミング、 *m_pSet*パラメーターへのポインターを[CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)。

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)
