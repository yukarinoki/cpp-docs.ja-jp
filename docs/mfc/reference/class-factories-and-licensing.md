---
title: クラス ファクトリとライセンス
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.classes
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: 3788d904bf903481d57dd73a28bf6eafadd5f019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392558"
---
# <a name="class-factories-and-licensing"></a>クラス ファクトリとライセンス

OLE コントロールのインスタンスを作成するには、コンテナー アプリケーションは、コントロールのクラス ファクトリのメンバー関数を呼び出します。 コントロールは、実際の OLE オブジェクトであるために、クラス ファクトリが、コントロールのインスタンスを作成する責任を負います。 すべての OLE コントロール クラスには、クラス ファクトリが必要です。

OLE コントロールのもう 1 つの重要な機能では、ライセンスを強制できる点です。 ControlWizard は、コントロール プロジェクトの作成時にライセンスを反映することができます。 コントロールのライセンスの詳細については、この記事を参照してください。 [ActiveX コントロール。ActiveX コントロールのライセンス](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)します。

次の表は、いくつかのマクロと関数を宣言し、コントロールのクラス ファクトリを実装するために使用して、コントロールのライセンス。

### <a name="class-factories-and-licensing"></a>クラス ファクトリとライセンス

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE コントロールまたはプロパティ ページのクラス ファクトリを宣言します。|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|コントロールの実装`GetClassID`関数をクラス ファクトリのインスタンスを宣言します。|
|[BEGIN_OLEFACTORY](#begin_olefactory)|ライセンス関数の宣言を開始します。|
|[END_OLEFACTORY](#end_olefactory)|ライセンス関数の宣言を終了します。|
|[AfxVerifyLicFile](#afxverifylicfile)|コントロールが特定のコンピューターで使用するためにライセンスされているかどうかを確認します。|

##  <a name="declare_olecreate_ex"></a>  DECLARE_OLECREATE_EX

クラス ファクトリを宣言し、`GetClassID`コントロール クラスのメンバー関数。

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロール クラスの名前。

### <a name="remarks"></a>Remarks

ライセンスをサポートしていないコントロールのコントロール クラスのヘッダー ファイルでこのマクロを使用します。

このマクロは、次のコード サンプルと同じ目的ことに注意してください。

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

##  <a name="implement_olecreate_ex"></a>  IMPLEMENT_OLECREATE_EX

コントロールのクラス ファクトリを実装し、 [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid)コントロール クラスのメンバー関数。

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
アプリケーションに公開されるオブジェクトの名前。

*l、-w1、w2、b1、b2、b3、b4、b5、b6、b7、b8*<br/>
クラスの CLSID のコンポーネント。 これらのパラメーターの詳細については、「解説」を参照してください。 [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)します。

### <a name="remarks"></a>Remarks

このマクロは、DECLARE_OLECREATE_EX マクロまたは BEGIN_OLEFACTORY と END_OLEFACTORY マクロを使用するコントロール クラスの実装ファイルに表示する必要があります。 External name は、他のアプリケーションに公開されている OLE コントロールの識別子です。 コンテナーでは、この名前を使用して、このコントロール クラスのオブジェクトを要求します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

##  <a name="begin_olefactory"></a>  BEGIN_OLEFACTORY

コントロール クラスのヘッダー ファイルでクラス ファクトリの宣言を開始します。

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
これは、クラス ファクトリを持つコントロール クラスの名前を指定します。

### <a name="remarks"></a>Remarks

クラス ファクトリのライセンスの関数の宣言は、BEGIN_OLEFACTORY 後すぐに開始する必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

##  <a name="end_olefactory"></a>  END_OLEFACTORY

コントロールのクラス ファクトリの宣言を終了します。

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
これは、クラス ファクトリを持つコントロール クラスの名前。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

##  <a name="afxverifylicfile"></a>  AfxVerifyLicFile

ライセンス ファイルがによってという名前を確認するには、この関数を呼び出す`pszLicFileName`は OLE コントロールに対して有効です。

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
ライセンスされたコントロールに関連付けられている DLL のインスタンス ハンドル。

*pszLicFileName*<br/>
ライセンス ファイル名を含む null で終わる文字列へのポインター。

*pszLicFileContents*<br/>
ライセンス ファイルの先頭にあるシーケンスに一致する必要があるバイト シーケンスを指します。

*cch*<br/>
内の文字数*pszLicFileContents*します。

### <a name="return-value"></a>戻り値

ライセンス ファイルが存在し、文字のシーケンスで始まる場合は 0 以外*pszLicFileContents*。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

場合*cch* -1 で、この関数を使用します。

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
