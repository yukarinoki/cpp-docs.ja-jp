---
title: CDataPathProperty クラス
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 89cb8ddcdd42643f52f755516e8845109163c57a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424453"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty クラス

非同期で読み込める OLE コントロール プロパティを実装します。

## <a name="syntax"></a>構文

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|`CDataPathProperty` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CDataPathProperty:: GetControl](#getcontrol)|`CDataPathProperty` オブジェクトに関連付けられた非同期 OLE コントロールを取得します。|
|[CDataPathProperty:: GetPath](#getpath)|プロパティのパス名を取得します。|
|[CDataPathProperty:: Open](#open)|関連付けられた ActiveX (OLE) コントロールの非同期プロパティの読み込みを開始します。|
|[CDataPathProperty:: ResetData](#resetdata)|`CAsyncMonikerFile::OnDataAvailable` を呼び出して、コントロールのプロパティが変更されたことをコンテナーに通知します。|
|[CDataPathProperty:: SetControl](#setcontrol)|プロパティに関連付けられた非同期 ActiveX (OLE) コントロールを設定します。|
|[CDataPathProperty::SetPath](#setpath)|プロパティのパス名を設定します。|

## <a name="remarks"></a>解説

非同期プロパティは、同期の開始後に読み込まれます。

クラス `CDataPathProperty` は `CAysncMonikerFile`から派生します。 OLE コントロールで非同期プロパティを実装するには、`CDataPathProperty`からクラスを派生させ、 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)をオーバーライドします。

インターネットアプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。

- [インターネットの最初の手順: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)

- [インターネットの最初の手順: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

##  <a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty

`CDataPathProperty` オブジェクトを構築します。

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
この `CDataPathProperty` オブジェクトに関連付けられる OLE コントロールオブジェクトへのポインター。

*lpszPath*<br/>
絶対パスまたは相対パスを指定します。このパスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CDataPathProperty` では、ファイル名ではなく Url を使用します。 ファイルの `CDataPathProperty` オブジェクトが必要な場合は、パスに `file://` を付加します。

### <a name="remarks"></a>解説

*Pcontrol*が指す `COleControl` オブジェクトは、`Open` によって使用され、派生クラスによって取得されます。 *Pcontrol*が NULL の場合は、`Open` で使用されるコントロールを `SetControl`で設定する必要があります。 *Lpszpath*が NULL の場合は、`Open` でパスを渡すか、`SetPath`で設定できます。

##  <a name="getcontrol"></a>CDataPathProperty:: GetControl

このメンバー関数を呼び出して、`CDataPathProperty` オブジェクトに関連付けられている `COleControl` オブジェクトを取得します。

```
COleControl* GetControl();
```

### <a name="return-value"></a>戻り値

`CDataPathProperty` オブジェクトに関連付けられた OLE コントロールへのポインターを返します。 コントロールが関連付けられていない場合は NULL です。

##  <a name="getpath"></a>CDataPathProperty:: GetPath

このメンバー関数を呼び出して、パスの取得、`CDataPathProperty` オブジェクトが構築されたとき、または `Open`で指定されたとき、または以前の `SetPath` メンバー関数の呼び出しで指定されたときの設定を行います。

```
CString GetPath() const;
```

### <a name="return-value"></a>戻り値

プロパティ自体にパス名を返します。 パスが指定されていない場合は、空にすることができます。

##  <a name="open"></a>CDataPathProperty:: Open

このメンバー関数を呼び出して、関連付けられているコントロールの非同期プロパティの読み込みを開始します。

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
この `CDataPathProperty` オブジェクトに関連付けられる OLE コントロールオブジェクトへのポインター。

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、が原因になります。

*lpszPath*<br/>
絶対パスまたは相対パスを指定します。このパスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CDataPathProperty` では、ファイル名ではなく Url を使用します。 ファイルの `CDataPathProperty` オブジェクトが必要な場合は、パスに `file://` を付加します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

関数は、コントロールから `IBindHost` インターフェイスを取得しようとします。

パスを指定せずに `Open` を呼び出す前に、プロパティのパスの値を設定する必要があります。 これは、オブジェクトを構築するとき、または `SetPath` メンバー関数を呼び出すことによって行うことができます。

コントロールを使用せずに `Open` を呼び出す前に、ActiveX コントロール (旧称 OLE コントロール) をオブジェクトに関連付けることができます。 これは、オブジェクトが構築されるとき、または `SetControl`を呼び出すことによって行うことができます。

[CAsyncMonikerFile:: Open](../../mfc/reference/casyncmonikerfile-class.md#open)のすべてのオーバーロードは、`CDataPathProperty`からも使用できます。

##  <a name="resetdata"></a>CDataPathProperty:: ResetData

この関数を呼び出して、コントロールのプロパティが変更されたことをコンテナーに通知するための `CAsyncMonikerFile::OnDataAvailable` を取得します。また、非同期に読み込まれたすべての情報は、不要になります。

```
virtual void ResetData();
```

### <a name="remarks"></a>解説

を再起動する必要があります。 派生クラスでは、この関数を異なる既定値に対してオーバーライドできます。

##  <a name="setcontrol"></a>CDataPathProperty:: SetControl

このメンバー関数を呼び出して、非同期 OLE コントロールを `CDataPathProperty` オブジェクトに関連付けます。

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
プロパティに関連付ける非同期 OLE コントロールへのポインター。

##  <a name="setpath"></a>CDataPathProperty::SetPath

このメンバー関数を呼び出して、プロパティのパス名を設定します。

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>パラメーター

*lpszPath*<br/>
非同期的に読み込まれるプロパティへの絶対パスまたは相対パスを指定できます。 `CDataPathProperty` では、ファイル名ではなく Url を使用します。 ファイルの `CDataPathProperty` オブジェクトが必要な場合は、パスに `file://` を付加します。

## <a name="see-also"></a>参照

[MFC のサンプルイメージ](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)
