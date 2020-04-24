---
title: クラス
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
ms.openlocfilehash: 479f5d47d9cff72d36dbd25e434182af1ba01ef4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754650"
---
# <a name="cdatapathproperty-class"></a>クラス

非同期で読み込める OLE コントロール プロパティを実装します。

## <a name="syntax"></a>構文

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティ::Cデータパスプロパティ](#cdatapathproperty)|`CDataPathProperty` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティ::取得コントロール](#getcontrol)|オブジェクトに関連付けられている非同期 OLE`CDataPathProperty`コントロールを取得します。|
|[次のプロパティを使用します。](#getpath)|プロパティのパス名を取得します。|
|[プロパティ::オープン](#open)|関連付けられた ActiveX (OLE) コントロールの非同期プロパティの読み込みを開始します。|
|[プロパティ::リセットデータ](#resetdata)|コントロール`CAsyncMonikerFile::OnDataAvailable`のプロパティが変更されたことをコンテナーに通知する呼び出し。|
|[プロパティ::セットコントロール](#setcontrol)|プロパティに関連付けられている非同期 ActiveX (OLE) コントロールを設定します。|
|[プロパティ::セットパス](#setpath)|プロパティのパス名を設定します。|

## <a name="remarks"></a>解説

非同期プロパティは、同期開始後に読み込まれます。

クラス`CDataPathProperty`は`CAysncMonikerFile`から派生します。 OLE コントロールに非同期プロパティを実装するには、 から`CDataPathProperty`クラスを派生させ、 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)をオーバーライドします。

インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。

- [インターネットの最初の手順: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)

- [インターネットの最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a>プロパティ::Cデータパスプロパティ

`CDataPathProperty` オブジェクトを構築します。

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
この`CDataPathProperty`オブジェクトに関連付ける OLE コントロール オブジェクトへのポインター。

*パス*<br/>
絶対パスまたは相対パスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CDataPathProperty`では、ファイル名ではなく URL を使用します。 ファイルのオブジェクトが`CDataPathProperty`必要な場合は、パスの`file://`前に追加します。

### <a name="remarks"></a>解説

*pControl*によって指されるオブジェクトは`Open``COleControl`、派生クラスによって使用および取得されます。 *pControl*が NULL の場合、`Open`で使用されるコントロール`SetControl`は で設定する必要があります。 *lpszPath*が NULL の場合は、パスを`Open`渡すか、または`SetPath`を使用してパスを設定できます。

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a>プロパティ::取得コントロール

オブジェクトに関連付けられているオブジェクトを`COleControl`取得します。 `CDataPathProperty`

```
COleControl* GetControl();
```

### <a name="return-value"></a>戻り値

オブジェクトに関連付けられた OLE コントロールへの`CDataPathProperty`ポインターを返します。 制御が関連付けられていない場合は NULL。

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a>次のプロパティを使用します。

このメンバー関数を呼び出して、パスを取得`CDataPathProperty`したり、オブジェクトが構築されたか`Open`、 で指定されたか、メンバー関数`SetPath`に対する前回の呼び出しで指定されたか、パスを取得します。

```
CString GetPath() const;
```

### <a name="return-value"></a>戻り値

プロパティ自体へのパス名を返します。 パスが指定されていない場合は、空にすることができます。

## <a name="cdatapathpropertyopen"></a><a name="open"></a>プロパティ::オープン

関連付けられたコントロールの非同期プロパティの読み込みを開始します。

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
この`CDataPathProperty`オブジェクトに関連付ける OLE コントロール オブジェクトへのポインター。

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因に設定されます。

*パス*<br/>
絶対パスまたは相対パスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CDataPathProperty`では、ファイル名ではなく URL を使用します。 ファイルのオブジェクトが`CDataPathProperty`必要な場合は、パスの`file://`前に追加します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、コントロールからインターフェイス`IBindHost`を取得しようとします。

パスを`Open`指定せずに呼び出す前に、プロパティのパスの値を設定する必要があります。 これは、オブジェクトが構築されるとき、またはメンバー関数を`SetPath`呼び出すことによって行うことができます。

コントロールを`Open`使用せずに呼び出す前に、ActiveX コントロール (以前は OLE コントロール) をオブジェクトに関連付けることができます。 これは、オブジェクトが構築されている場合、または を呼び`SetControl`出すことによって行うことができます。

[CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open)のすべてのオーバーロードもから入手できます`CDataPathProperty`。

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a>プロパティ::リセットデータ

コントロールのプロパティが変更`CAsyncMonikerFile::OnDataAvailable`され、非同期に読み込まれた情報がすべて役に立たなくなったことをコンテナーに通知します。

```
virtual void ResetData();
```

### <a name="remarks"></a>解説

開きが再開されます。 派生クラスは、さまざまな既定値に対してこの関数をオーバーライドできます。

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a>プロパティ::セットコントロール

非同期 OLE コントロールをオブジェクトに関連付けるには`CDataPathProperty`、このメンバー関数を呼び出します。

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
プロパティに関連付ける非同期 OLE コントロールへのポインター。

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a>プロパティ::セットパス

プロパティのパス名を設定します。

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
非同期的に読み込まれるプロパティへの絶対パスまたは相対パス。 `CDataPathProperty`では、ファイル名ではなく URL を使用します。 ファイルのオブジェクトが`CDataPathProperty`必要な場合は、パスの`file://`前に追加します。

## <a name="see-also"></a>関連項目

[MFC サンプル イメージ](../../overview/visual-cpp-samples.md)<br/>
[クラスクラス](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスクラス](../../mfc/reference/casyncmonikerfile-class.md)
