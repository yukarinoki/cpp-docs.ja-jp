---
title: CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数
ms.date: 09/17/2019
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
ms.openlocfilehash: 3128b1ba459cb017d1cdb2321bc55d865aa4f8b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365774"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数

このトピックでは[、C レコード セット](../../mfc/reference/crecordset-class.md)と C レコード ビュー フォームまたは CDao レコードビュー フォームと[CDaoRecordView](../../mfc/reference/cdaorecordset-class.md)フォームの間でデータを交換するために使用されるDDX_Field関数を示[CRecordView](../../mfc/reference/crecordview-class.md)[します](../../mfc/reference/cdaorecordview-class.md)。 DAO は Access データベースで使用され、Office 2013 を通じてサポートされます。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

> [!NOTE]
> DDX_Field関数は、フォーム内のコントロールとデータを交換するという DDX 関数に似ています。 ただし、DDX とは異なり、レコード ビュー自体のフィールドではなく、ビューの関連レコードセット オブジェクトのフィールドとデータを交換します。 詳細については、クラス`CRecordView`と`CDaoRecordView`を参照してください。

### <a name="ddx_field-functions"></a>DDX_Field関数

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|レコードセット フィールドのデータ メンバーと[、CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)のコンボ ボックス内の現在の選択範囲のインデックスとの間で整数データを転送します。|
|[DDX_FieldCBString](#ddx_fieldcbstring)|または`CString`内のコンボ ボックスのエディット コントロールとレコードセット フィールドのデータ`CRecordView``CDaoRecordView`メンバー間でデータを転送します。 レコードセットからコントロールにデータを移動するときに、この関数は、指定した文字列の文字で始まる項目をコンボ ボックス内で選択します。|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|または`CString`内のコンボ ボックスのエディット コントロールとレコードセット フィールドのデータ`CRecordView``CDaoRecordView`メンバー間でデータを転送します。 レコードセットからコントロールにデータを移動するときに、この関数は、指定した文字列と完全に一致する項目をコンボ ボックス内で選択します。|
|[DDX_FieldCheck](#ddx_fieldcheck)|レコードセット フィールドのデータ メンバと、 または`CRecordView``CDaoRecordView`のチェック ボックスとの間でブール型データを転送します。|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|レコードセット フィールドのデータ メンバーと、 または`CRecordView``CDaoRecordView`のリスト ボックス内の現在の選択範囲のインデックスとの間で整数データを転送します。|
|[DDX_FieldLBString](#ddx_fieldlbstring)|リスト ボックス コントロールとレコードセットのフィールド データ メンバー間で[の CString](../../atl-mfc-shared/reference/cstringt-class.md)データの転送を管理します。 レコードセットからコントロールにデータを移動するときに、この関数は、指定された文字列の文字で始まる項目をリスト ボックスから選択します。|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|リスト ボックス コントロール`CString`とレコードセットのフィールド データ メンバー間のデータ転送を管理します。 レコードセットからコントロールにデータを移動するときに、この関数は、指定した文字列と完全に一致する最初の項目を選択します。|
|[DDX_FieldRadio](#ddx_fieldradio)|レコードセット フィールドのデータ メンバーと、 または`CRecordView``CDaoRecordView`内のラジオ ボタンのグループとの間で整数データを転送します。|
|[DDX_FieldScroll](#ddx_fieldscroll)|または のスクロール バー コントロールのスクロール位置を`CRecordView`設定または`CDaoRecordView`取得します。 [関数](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)から呼び出します。|
|[DDX_FieldSlider](#ddx_fieldslider)|レコード ビューのスライダー コントロールとレコードセットのフィールド データ`int`メンバのつまみの位置を同期します。 |
|[DDX_FieldText](#ddx_fieldtext)|オーバーロードされた`int`バージョンは、 **UINT**、 **long**、 `DWORD` [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 浮動小数点数 、**倍精度**、**短****い**、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)の各レコードセット フィールド データ メンバーと エディット ボックスの間で`CRecordView`転送できます。 `CDaoRecordView`|

## <a name="ddx_fieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex

この`DDX_FieldCBIndex`関数は、レコード ビューのコンボ ボックス コントロールのリスト ボックス コントロール内の選択された項目のインデックス`int`と、レコード ビューに関連付けられたレコードセットのフィールド データ メンバのインデックスを同期します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*index*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセットからコントロールにデータを移動する場合、この関数は*index*で指定された値に基づいてコントロール内の選択を設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、MFC はインデックスの値を 0 に設定します。 コントロールからレコードセットへの転送で、コントロールが空の場合、または項目が選択されていない場合、レコードセット フィールドは 0 に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 この例は、 の`DDX_FieldCBIndex`例と似ています。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="ddx_fieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString

`DDX_FieldCBString` 関数は、レコードビュー内のコンボボックスコントロールの編集コントロールと、レコードビューに関連付けられているレコードセットの `CString` フィールドデータメンバーとの間で、[CString](../../atl-mfc-shared/reference/cstringt-class.md)データの転送を管理します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセットからコントロールにデータを移動するときに、コンボ ボックスの現在の選択範囲を value*で指定*された文字列の文字で始まる最初の行に設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、コンボ ボックスから選択内容が削除され、コンボ ボックスのエディット コントロールが空に設定されます。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドが許可されている場合は、レコードセット フィールドが Null に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 この例には、 への`DDX_FieldCBString`呼び出しが含まれています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact

`DDX_FieldCBStringExact` 関数は、レコードビュー内のコンボボックスコントロールの編集コントロールと、レコードビューに関連付けられているレコードセットの `CString` フィールドデータメンバーとの間で、[CString](../../atl-mfc-shared/reference/cstringt-class.md)データの転送を管理します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセットからコントロールにデータを移動するときに、コンボ ボックスの現在の選択範囲を value*で指定*した文字列と完全に一致する最初の行に設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが NULL の場合、コンボ ボックスから選択内容が削除され、コンボ ボックスのエディット ボックスが空に設定されます。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドは NULL に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 への呼`DDX_FieldCBStringExact`び出しは似ています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck

この`DDX_FieldCheck`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのチェック ボックス コントロールと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int**データ メンバとの間で**int**データを転送する処理を管理します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているチェック ボックス コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

呼`DDX_FieldCheck`び出されると、*値*はチェック ボックス コントロールの現在の状態に設定されるか、コントロールの状態が転送方向に応じて*value*に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex

この`DDX_FieldLBIndex`関数は、レコード ビューのリスト ボックス コントロール内の選択された項目のインデックスと、レコード ビューに関連付けられたレコードセットの**int**フィールド データ メンバを同期します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*index*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセットからコントロールにデータを移動する場合、この関数は*index*で指定された値に基づいてコントロール内の選択を設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、MFC はインデックスの値を 0 に設定します。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドは 0 に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString

レコード`DDX_FieldLBString`ビュー内のリスト ボックス コントロールの現在の選択内容を、レコード ビューに関連付けられたレコードセットの[CString](../../atl-mfc-shared/reference/cstringt-class.md)フィールド データ メンバにコピーします。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

逆方向に、この関数はリスト ボックスの現在の選択を value*で指定*された文字列の文字で始まる最初の行に設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、リスト ボックスから選択内容が削除されます。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドは Null に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 への呼`DDX_FieldLBString`び出しは似ています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact

この`DDX_FieldLBStringExact`関数は、レコード ビュー内のリスト ボックス コントロールの現在の選択を、レコード ビューに関連付けられたレコードセットの[CString](../../atl-mfc-shared/reference/cstringt-class.md)フィールド データ メンバにコピーします。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

逆方向に、この関数はリスト ボックスの現在の選択を value*で指定*した文字列と完全に一致する最初の行に設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、リスト ボックスから選択内容が削除されます。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドは Null に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 への呼`DDX_FieldLBStringExact`び出しは似ています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio

この`DDX_FieldRadio`関数は、レコード ビューのレコードセットの 0 から始まる**int**メンバ変数を、レコード ビューのラジオ ボタンのグループで現在選択されているラジオ ボタンに関連付けます。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
[CRecordView または CDaoRecordView](../../mfc/reference/crecordview-class.md)オブジェクト内の隣接するラジオ ボタン コントロールのグループ[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)(スタイル WS_GROUP) 内の最初の ID。

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセット フィールドからビューに転送する場合、この関数は*n 番目*のオプション ボタン (0 から始まるボタン) をオンにし、他のボタンをオフにします。 逆方向に、この関数は、現在オンになっている (オンになっている) オプション ボタンの序数にレコードセット フィールドを設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、ボタンは選択されません。 コントロールからレコードセットへの転送で、コントロールが選択されていない場合、レコードセット フィールドで許可されている場合は、レコードセット フィールドが Null に設定されます。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 への呼`DDX_FieldRadio`び出しは似ています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll

この`DDX_FieldScroll`関数は、レコード ビューのスクロール バー コントロールと、レコード ビューに関連付けられたレコードセットの**int**フィールド データ メンバー (またはマップする整数変数) のスクロール位置を同期します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
[CRecordView または CDaoRecordView](../../mfc/reference/crecordview-class.md)オブジェクト内の隣接するラジオ ボタン コントロールのグループ[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)(スタイル WS_GROUP) 内の最初の ID。

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセットからコントロールにデータを移動するときに、この関数は、スクロール バー コントロールのスクロール位置を*value*で指定された値に設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、スクロール バー コントロールは 0 に設定されます。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドの値は 0 になります。

ODBC ベースのクラスを使用する場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用する場合は、2 番目のバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 への呼`DDX_FieldScroll`び出しは似ています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="ddx_fieldslider"></a><a name="ddx_fieldslider"></a>DDX_FieldSlider

この`DDX_FieldSlider`関数は、レコード ビューのスライダー コントロールと、レコード ビューに関連付けられたレコードセットの**int**フィールド データ メンバーのサム位置 (またはマップする整数変数) を同期します。

### <a name="syntax"></a>構文

```cpp
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

*Pdx*<br/>
[オブジェクト](cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
スライダー コントロールのリソース ID。

*value*<br/>
交換する値への参照。 このパラメータは、スライダー コントロールの現在のつまみ位置を設定するために使用されます。

*pRecordset*<br/>
データが交換される関連`CRecordset`付`CDaoRecordset`けられたオブジェクトまたはオブジェクトへのポインター。

### <a name="remarks"></a>解説

レコードセットからスライダーにデータを移動する場合、この関数はスライダーの位置を*value*で指定された値に設定します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、スライダー コントロールの位置は 0 に設定されます。 コントロールからレコードセットへの転送時に、コントロールが空の場合、レコードセット フィールドの値は 0 になります。

`DDX_FieldSlider`は、単に位置を設定するのではなく、範囲を設定できるスライダーコントロールと範囲情報を交換しません。

ODBC ベースのクラスを操作する場合は、関数の最初のオーバーライドを使用します。 DAO ベースのクラスで 2 番目のオーバーライドを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../dialog-data-exchange-and-validation.md)」を参照してください。 DDX の`CRecordView`フィールドとフィールドの例と`CDaoRecordView`詳細については、「[レコード ビュー](../../data/record-views-mfc-data-access.md)」を参照してください。 スライダー コントロールの詳細については、「 [CSliderCtrl](../using-csliderctrl.md)の使用 」を参照してください。

### <a name="example"></a>例

一般的なDDX_Fieldの例については[、DDX_FieldText](#ddx_fieldtext)を参照してください。 への呼`DDX_FieldSlider`び出しは似ています。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="ddx_fieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText

この`DDX_FieldText`関数は、編集ボックス コントロールとレコードセットのフィールド データ メンバとの間の**int**、 **short**、 **long**、 DWORD 、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、**浮動小数点**数 、**倍精度**浮動小数点数 、**ブール**値 、**または BYTE**データの転送を管理します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
オブジェクト内の[コントロールの](../../mfc/reference/crecordview-class.md)[ID。](../../mfc/reference/cdaorecordview-class.md)

*value*<br/>
関連付けられた`CRecordset`または`CDaoRecordset`オブジェクト内のフィールド データ メンバーへの参照。 値のデータ型は、使用するオーバーロードされたバージョンによって`DDX_FieldText`異なります。

*pRecordset*<br/>
データが交換される[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトへのポインター。 このポインタは`DDX_FieldText`、Null 値を検出して設定できます。

### <a name="remarks"></a>解説

[オブジェクト](../../mfc/reference/cdaorecordset-class.md)の場合は`DDX_FieldText`[、COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)値の転送も管理します。 空のエディット ボックス コントロールは Null 値を示します。 レコードセットからコントロールへの転送時に、レコードセット フィールドが Null の場合、エディット ボックスは空に設定されます。 コントロールからレコードセットへの転送で、コントロールが空の場合、レコードセット フィールドは Null に設定されます。

ODBC ベースのクラスを使用する場合は[、CRecordset](../../mfc/reference/crecordset-class.md)パラメーターと共にバージョンを使用します。 DAO ベースのクラスを使用する場合は[、CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)パラメーターを持つバージョンを使用します。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 例と C レコードビューと[CDao](../../mfc/reference/crecordview-class.md) [レコードビュー](../../mfc/reference/cdaorecordview-class.md)フィールドの DDX の詳細については、[記事レコード ビューを参照してください](../../data/record-views-mfc-data-access.md)。

### <a name="example"></a>例

[CRecordView](../../mfc/reference/crecordview-class.md)の次`DoDataExchange`の関数には`DDX_FieldText`、3 つのデータ型の`IDC_COURSELIST`関数呼び出しが含まれています。他の 2 つのコントロールはエディット ボックスです。 DAO プログラミングの場合 *、m_pSet*パラメータは CRecordset または[CDaoRecordset](../../mfc/reference/crecordset-class.md)へのポインタ[です](../../mfc/reference/cdaorecordset-class.md)。

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)
