---
title: クラス ファクトリとライセンス
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: e3fed6520cdbe0fd964e4e80e7c9ed9b78296d16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372311"
---
# <a name="class-factories-and-licensing"></a>クラス ファクトリとライセンス

OLE コントロールのインスタンスを作成するには、コンテナー アプリケーションがコントロールのクラス ファクトリのメンバー関数を呼び出します。 コントロールは実際の OLE オブジェクトであるため、コントロールのインスタンスを作成するのはクラス ファクトリです。 すべての OLE コントロール クラスには、クラス ファクトリが必要です。

OLE コントロールのもう 1 つの重要な機能は、ライセンスを強制する機能です。 ControlWizard を使用すると、コントロール プロジェクトの作成時にライセンスを組み込むことができます。 コントロール ライセンスの詳細については[、「ActiveX コントロール: ActiveX コントロールのライセンス」](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)を参照してください。

次の表に、コントロールのクラス ファクトリを宣言および実装し、コントロールのライセンスを取得するために使用するいくつかのマクロと関数を示します。

### <a name="class-factories-and-licensing"></a>クラス ファクトリとライセンス

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE コントロールまたはプロパティ ページのクラス ファクトリを宣言します。|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|コントロールの`GetClassID`関数を実装し、クラス ファクトリのインスタンスを宣言します。|
|[BEGIN_OLEFACTORY](#begin_olefactory)|ライセンス関数の宣言を開始します。|
|[END_OLEFACTORY](#end_olefactory)|ライセンス関数の宣言を終了します。|
|[AfxVerifyLicFile](#afxverifylicfile)|コントロールが特定のコンピュータで使用するライセンスを取得しているかどうかを確認します。|

## <a name="declare_olecreate_ex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX

クラス ファクトリとコントロール クラス`GetClassID`のメンバー関数を宣言します。

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロール クラスの名前。

### <a name="remarks"></a>解説

このマクロは、ライセンスをサポートしないコントロールのコントロール クラス ヘッダー ファイルで使用します。

このマクロは、次のコード サンプルと同じ目的で使用されます。

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="implement_olecreate_ex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX

コントロールのクラス ファクトリとコントロール クラスの[GetClassID](../../mfc/reference/colecontrol-class.md#getclassid)メンバー関数を実装します。

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロールのプロパティ ページ クラスの名前。

*external_name*<br/>
アプリケーションに公開されるオブジェクト名。

*l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*<br/>
クラスの CLSID のコンポーネント。 これらのパラメータの詳細については、「 IMPLEMENT_OLECREATE[の解説](run-time-object-model-services.md#implement_olecreate)」を参照してください。

### <a name="remarks"></a>解説

このマクロは、DECLARE_OLECREATE_EX マクロまたはBEGIN_OLEFACTORYマクロとEND_OLEFACTORYマクロを使用するコントロール クラスの実装ファイルに含める必要があります。 外部名は、他のアプリケーションに公開される OLE コントロールの識別子です。 コンテナーはこの名前を使用して、このコントロール クラスのオブジェクトを要求します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="begin_olefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY

コントロール クラスのヘッダー ファイルでクラス ファクトリの宣言を開始します。

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラス ファクトリが指定されているコントロール クラスの名前を指定します。

### <a name="remarks"></a>解説

クラス ファクトリ ライセンス関数の宣言は、BEGIN_OLEFACTORY直後に開始する必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="end_olefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY

コントロールのクラス ファクトリの宣言を終了します。

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラス ファクトリが指定されたコントロール クラスの名前。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="afxverifylicfile"></a><a name="afxverifylicfile"></a>Afx検証Licファイル

この関数を呼び出して、指定された`pszLicFileName`ライセンス ファイルが OLE コントロールに対して有効であることを確認します。

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
ライセンスを受けたコントロールに関連付けられている DLL のインスタンス ハンドル。

*ファイル名*<br/>
ライセンス ファイル名を含む null で終わる文字列を指します。

*コンテンツ*<br/>
ライセンス ファイルの先頭にあるシーケンスと一致する必要があるバイト シーケンスを指します。

*Cch*<br/>
ファイル*の内容の*文字数。

### <a name="return-value"></a>戻り値

ライセンス ファイルが存在し *、pszLicFileContents*の文字シーケンスで始まる場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*cch*が -1 の場合、この関数は次の値を使用します。

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
