---
title: OLE コントロールの登録
ms.date: 11/04/2016
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 2f2d7872e8b9369b5eef283e5b52a54c29afd563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372973"
---
# <a name="registering-ole-controls"></a>OLE コントロールの登録

OLE コントロールは、他の OLE サーバー オブジェクトと同様に、他の OLE 対応アプリケーションからアクセスできます。 これは、コントロールのタイプ ライブラリとクラスを登録することで実現されます。

次の関数を使用すると、Windows 登録データベース内のコントロールのクラス、プロパティ ページ、およびタイプ ライブラリを追加および削除できます。

### <a name="registering-ole-controls"></a>OLE コントロールの登録

|||
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|コントロールのクラスを登録データベースに追加します。|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|登録データベースにコントロール プロパティ ページを追加します。|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|コントロールのタイプ ライブラリを登録データベースに追加します。|
|[AfxOleUnregisterClass](#afxoleunregisterclass)|登録データベースからコントロール クラスまたはプロパティ ページ クラスを削除します。|
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|登録データベースからコントロールのタイプ ライブラリを削除します。|

`AfxOleRegisterTypeLib`は通常、コントロール DLL の 実装で`DllRegisterServer`呼び出されます。 同様に`AfxOleUnregisterTypeLib`、 によって`DllUnregisterServer`呼び出されます。 `AfxOleRegisterControlClass`、、`AfxOleRegisterPropertyPageClass`および`AfxOleUnregisterClass`は、通常、コントロール`UpdateRegistry`のクラス ファクトリまたはプロパティ ページのメンバー関数によって呼び出されます。

## <a name="afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a>コントロール クラス

コントロール クラスを Windows 登録データベースに登録します。

```
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,
    REFCLSID clsid,
    LPCTSTR pszProgID,
    UINT idTypeName,
    UINT idBitmap,
    int nRegFlags,
    DWORD dwMiscStatus,
    REFGUID tlid,
    WORD wVerMajor,
    WORD wVerMinor);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
コントロール クラスに関連付けられているモジュールのインスタンス ハンドル。

*Clsid*<br/>
コントロールの一意のクラス ID。

*プシプログID*<br/>
コントロールの一意のプログラム ID。

*idタイプ名*<br/>
コントロールのユーザーが読み取り可能な型名を含む文字列のリソース ID。

*idビットマップ*<br/>
OLE コントロールをツール バーまたはパレットで表すために使用されるビットマップのリソース ID。

*フラグ*<br/>
次のフラグの 1 つ以上を含みます。

- `afxRegInsertable`OLE オブジェクトの [オブジェクトの挿入] ダイアログ ボックスにコントロールを表示できるようにします。

- `afxRegApartmentThreading`レジストリのスレッド モデルをスレッドモデル=アパートメントに設定します。

- `afxRegFreeThreading`レジストリのスレッド モデルをスレッド処理モデル=Free に設定します。

   2 つのフラグ`afxRegApartmentThreading`を組み`afxRegFreeThreading`合わせて、ThreadingModel=Both を設定できます。 スレッド モデルの登録の詳細については、Windows SDK の[InprocServer32](/windows/win32/com/inprocserver32)を参照してください。

> [!NOTE]
> MFC 4.2 以前の MFC バージョンでは **、int** *nRegFlags*パラメーターは BOOL パラメーター *bInsertable*で、オブジェクトの挿入ダイアログ ボックスからコントロールを挿入することを許可または禁止しました。

*ステータス*<br/>
次の状態フラグが 1 つ以上含まれています (フラグの説明については、Windows SDK の OLEMISC 列挙を参照してください)。

- OLEMISC_RECOMPOSEONRESIZE

- OLEMISC_ONLYICONIC

- OLEMISC_INSERTNOTREPLACE

- OLEMISC_STATIC

- OLEMISC_CANTLINKINSIDE

- OLEMISC_CANLINKBYOLE1

- OLEMISC_ISLINKOBJECT

- OLEMISC_INSIDEOUT

- OLEMISC_ACTIVATEWHENVISIBLE

- OLEMISC_RENDERINGISDEVICEINDEPENDENT

- OLEMISC_INVISIBLEATRUNTIME

- OLEMISC_ALWAYSRUN

- OLEMISC_ACTSLIKEBUTTON

- OLEMISC_ACTSLIKELABEL

- OLEMISC_NOUIACTIVATE

- OLEMISC_ALIGNABLE

- OLEMISC_IMEMODE

- OLEMISC_SIMPLEFRAME

- OLEMISC_SETCLIENTSITEFIRST

*トリッド*<br/>
コントロール クラスの一意の ID。

*wVerメジャー*<br/>
コントロール クラスのメジャー バージョン番号。

*wVerMinor*<br/>
コントロール クラスのマイナー バージョン番号。

### <a name="return-value"></a>戻り値

コントロール クラスが登録されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

これにより、OLE コントロールに対応するコンテナでコントロールを使用できるようになります。 `AfxOleRegisterControlClass`システム上のコントロールの名前と場所をレジストリに更新し、レジストリでコントロールがサポートするスレッド モデルを設定します。 詳細については、テクニカル[ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、「OLE コントロールでのアパートメント モデルのスレッド処理」および「Windows SDK の[プロセスとスレッドについて](/windows/win32/ProcThread/about-processes-and-threads)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

上記の例は、挿入`AfxOleRegisterControlClass`可能なフラグとアパートメント モデルの RED のフラグを使用して呼び出して 6 番目のパラメータを作成する方法を示しています。

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

コントロールは、有効なコンテナーの [オブジェクトの挿入] ダイアログ ボックスに表示され、アパートメント モデル対応になります。 アパートメント モデル対応コントロールは、静的クラス データがロックによって保護されるようにする必要があります。 静的データへのアクセスは、クリティカル セクション コードで囲まれます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a>プロパティ ページ クラス

プロパティ ページ クラスを Windows 登録データベースに登録します。

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
プロパティ ページ クラスに関連付けられているモジュールのインスタンス ハンドル。

*Clsid*<br/>
プロパティ ページの一意のクラス ID。

*idタイプ名*<br/>
プロパティ ページのユーザーが読み取り可能な名前を含む文字列のリソース ID。

*フラグ*<br/>
フラグを含む場合があります。

- `afxRegApartmentThreading`レジストリのスレッド モデルを ThreadingModel = アパートメントに設定します。

> [!NOTE]
> MFC 4.2 より前のバージョンでは **、int** *nRegFlags*パラメーターは使用できませんでした。 また、`afxRegInsertable`このフラグはプロパティ ページには有効なオプションではなく、設定されている場合は MFC で ASSERT が発生します。

### <a name="return-value"></a>戻り値

コントロール クラスが登録されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

これにより、OLE コントロールに対応するコンテナでプロパティ ページを使用できるようになります。 `AfxOleRegisterPropertyPageClass`プロパティ ページ名とシステム上の場所を使用してレジストリを更新し、レジストリでコントロールがサポートするスレッド モデルも設定します。 詳細については、テクニカル[ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、「OLE コントロールでのアパートメント モデルのスレッド処理」および「Windows SDK の[プロセスとスレッドについて](/windows/win32/ProcThread/about-processes-and-threads)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a>を使用します。

タイプ ライブラリを Windows 登録データベースに登録し、OLE コントロールに対応する他のコンテナでタイプ ライブラリを使用できるようにします。

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
タイプ ライブラリに関連付けられているアプリケーションのインスタンス ハンドル。

*トリッド*<br/>
タイプ ライブラリの一意の ID。

*ファイル名*<br/>
ローカライズされたタイプ ライブラリ (.コントロールの TLB) ファイル。

*を使用します。*<br/>
タイプ ライブラリのヘルプ ファイルが見つかるディレクトリの名前。 NULL の場合、ヘルプ ファイルはタイプ ライブラリ自体と同じディレクトリにあると見なされます。

### <a name="return-value"></a>戻り値

タイプ ライブラリが登録されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、レジストリをタイプ ライブラリ名とシステム上の場所で更新します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a>クラスを登録します。

Windows 登録データベースからコントロールまたはプロパティ ページ クラス エントリを削除します。

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
コントロールまたはプロパティ ページの一意のクラス ID。

*プシプログID*<br/>
コントロールまたはプロパティ ページの一意のプログラム ID。

### <a name="return-value"></a>戻り値

コントロールまたはプロパティ ページ クラスが正常に登録解除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a>タイプリブを登録します。

Windows 登録データベースからタイプ ライブラリ エントリを削除します。

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>パラメーター

*tlID*<br/>
タイプ ライブラリの一意の ID。

### <a name="return-value"></a>戻り値

タイプ ライブラリが正常に登録解除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
