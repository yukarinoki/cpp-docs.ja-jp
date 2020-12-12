---
description: '詳細情報: CDataPathProperty クラス'
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
ms.openlocfilehash: 7d9ff9f380fd44d5261374879bab63c9925c4442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247957"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty クラス

非同期で読み込める OLE コントロール プロパティを実装します。

## <a name="syntax"></a>構文

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|`CDataPathProperty` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDataPathProperty:: GetControl](#getcontrol)|オブジェクトに関連付けられた非同期 OLE コントロールを取得し `CDataPathProperty` ます。|
|[CDataPathProperty:: GetPath](#getpath)|プロパティのパス名を取得します。|
|[CDataPathProperty:: Open](#open)|関連付けられた ActiveX (OLE) コントロールの非同期プロパティの読み込みを開始します。|
|[CDataPathProperty:: ResetData](#resetdata)|を呼び出して、 `CAsyncMonikerFile::OnDataAvailable` コントロールのプロパティが変更されたことをコンテナーに通知します。|
|[CDataPathProperty:: SetControl](#setcontrol)|プロパティに関連付けられた非同期 ActiveX (OLE) コントロールを設定します。|
|[CDataPathProperty::SetPath](#setpath)|プロパティのパス名を設定します。|

## <a name="remarks"></a>解説

非同期プロパティは、同期の開始後に読み込まれます。

クラス `CDataPathProperty` はから派生 `CAysncMonikerFile` しています。 OLE コントロールで非同期プロパティを実装するには、からクラスを派生させ、 `CDataPathProperty` [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)をオーバーライドします。

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

## <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a> CDataPathProperty::CDataPathProperty

`CDataPathProperty` オブジェクトを構築します。

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
このオブジェクトに関連付けられる OLE コントロールオブジェクトへのポインター `CDataPathProperty` 。

*lpszPath*<br/>
絶対パスまたは相対パスを指定します。このパスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CDataPathProperty` ファイル名ではなく Url を使用します。 ファイルのオブジェクトが必要な場合は `CDataPathProperty` 、パスの前にを付加し `file://` ます。

### <a name="remarks"></a>解説

`COleControl` *Pcontrol* が指すオブジェクトは、によって使用され、 `Open` 派生クラスによって取得されます。 *Pcontrol* が NULL の場合は、で使用されるコントロールを `Open` で設定する必要があり `SetControl` ます。 *Lpszpath* が NULL の場合は、を使用してパスを渡す `Open` か、を使用して設定でき `SetPath` ます。

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a> CDataPathProperty:: GetControl

`COleControl`オブジェクトに関連付けられたオブジェクトを取得するには、このメンバー関数を呼び出し `CDataPathProperty` ます。

```
COleControl* GetControl();
```

### <a name="return-value"></a>戻り値

オブジェクトに関連付けられた OLE コントロールへのポインターを返し `CDataPathProperty` ます。 コントロールが関連付けられていない場合は NULL です。

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a> CDataPathProperty:: GetPath

このメンバー関数を呼び出して、パスの取得、 `CDataPathProperty` オブジェクトが構築されたとき、またはで指定したときの設定、 `Open` またはメンバー関数の前の呼び出しで指定したパスを取得し `SetPath` ます。

```
CString GetPath() const;
```

### <a name="return-value"></a>戻り値

プロパティ自体にパス名を返します。 パスが指定されていない場合は、空にすることができます。

## <a name="cdatapathpropertyopen"></a><a name="open"></a> CDataPathProperty:: Open

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
このオブジェクトに関連付けられる OLE コントロールオブジェクトへのポインター `CDataPathProperty` 。

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、が原因になります。

*lpszPath*<br/>
絶対パスまたは相対パスを指定します。このパスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CDataPathProperty` ファイル名ではなく Url を使用します。 ファイルのオブジェクトが必要な場合は `CDataPathProperty` 、パスの前にを付加し `file://` ます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

関数は、コントロールからインターフェイスを取得しようとし `IBindHost` ます。

`Open`パスを指定せずにを呼び出す前に、プロパティのパスの値を設定する必要があります。 これは、オブジェクトが構築されるとき、またはメンバー関数を呼び出すことによって行うことができ `SetPath` ます。

`Open`コントロールを使用せずにを呼び出す前に、ActiveX コントロール (旧称 OLE コントロール) をオブジェクトに関連付けることができます。 これは、オブジェクトが構築されたとき、またはを呼び出すことによって行うことができ `SetControl` ます。

[CAsyncMonikerFile:: Open](../../mfc/reference/casyncmonikerfile-class.md#open)のすべてのオーバーロードは、からも使用でき `CDataPathProperty` ます。

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a> CDataPathProperty:: ResetData

この関数を呼び出して、 `CAsyncMonikerFile::OnDataAvailable` コントロールのプロパティが変更されたことをコンテナーに通知します。また、非同期に読み込まれたすべての情報は、役に立たなくなります。

```
virtual void ResetData();
```

### <a name="remarks"></a>解説

を再起動する必要があります。 派生クラスでは、この関数を異なる既定値に対してオーバーライドできます。

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a> CDataPathProperty:: SetControl

このメンバー関数を呼び出して、非同期 OLE コントロールをオブジェクトに関連付け `CDataPathProperty` ます。

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
プロパティに関連付ける非同期 OLE コントロールへのポインター。

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a> CDataPathProperty::SetPath

このメンバー関数を呼び出して、プロパティのパス名を設定します。

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>パラメーター

*lpszPath*<br/>
非同期的に読み込まれるプロパティへの絶対パスまたは相対パスを指定できます。 `CDataPathProperty` ファイル名ではなく Url を使用します。 ファイルのオブジェクトが必要な場合は `CDataPathProperty` 、パスの前にを付加し `file://` ます。

## <a name="see-also"></a>関連項目

[MFC のサンプルイメージ](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)
