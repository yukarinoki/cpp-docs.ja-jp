---
title: アプリケーションの制御
ms.date: 11/04/2016
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 40ac3b6871d13420797279629a2661b22545d1d8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832374"
---
# <a name="application-control"></a>アプリケーションの制御

OLE では、アプリケーションとそのオブジェクトを十分に制御する必要があります。 OLE システム Dll は、アプリケーションを自動的に起動して解放し、オブジェクトの実稼働や変更などを調整できる必要があります。 このトピックの関数は、これらの要件を満たしています。 これらの関数は、OLE システム Dll によって呼び出されるだけでなく、アプリケーションからも呼び出されることがあります。

### <a name="application-control"></a>アプリケーションの制御

| 名前 | 説明 |
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|アプリケーションを終了できるかどうかを示します。|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|アプリケーションの現在のメッセージフィルターを取得します。|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|現在のユーザーコントロールフラグを取得します。|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|ユーザーコントロールフラグを設定または解除します。|
|[AfxOleLockApp](#afxolelockapp)|アプリケーション内のアクティブなオブジェクトの数の、フレームワークのグローバルカウントをインクリメントします。|
|[AfxOleLockControl](#afxolelockcontrol)| 指定したコントロールのクラスファクトリをロックします。 |
|[AfxOleUnlockApp](#afxoleunlockapp)|アプリケーション内のアクティブなオブジェクトの数のフレームワークのカウントをデクリメントします。|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| 指定したコントロールのクラスファクトリのロックを解除します。 |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE システムレジストリにサーバーを登録します。|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|*Typename*オブジェクトコマンドのユーザーインターフェイスを実装します。|

## <a name="afxolecanexitapp"></a><a name="afxolecanexitapp"></a> AfxOleCanExitApp

アプリケーションを終了できるかどうかを示します。

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>戻り値

アプリケーションを終了できる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

オブジェクトへの未処理の参照がある場合、アプリケーションは終了しないでください。 グローバル関数とは、 `AfxOleLockApp` `AfxOleUnlockApp` それぞれアプリケーションのオブジェクトへの参照のカウンターをインクリメントおよびデクリメントします。 このカウンターが0以外の場合、アプリケーションは終了しないでください。 カウンターが0以外の場合、ユーザーが [システム] メニューの [閉じる] を選択するか、[ファイル] メニューの [終了] を選択すると、アプリケーションのメインウィンドウが非表示になります (破棄されません)。 フレームワークは、でこの関数を呼び出し `CFrameWnd::OnClose` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a> AfxOleGetMessageFilter

アプリケーションの現在のメッセージフィルターを取得します。

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>戻り値

現在のメッセージフィルターへのポインター。

### <a name="remarks"></a>解説

現在のから派生したオブジェクトにアクセスするには、現在のアプリケーションオブジェクトにアクセスするときと同じように、この関数を呼び出し `COleMessageFilter` `AfxGetApp` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー**: afxwin.h

## <a name="afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a> AfxOleGetUserCtrl

現在のユーザーコントロールフラグを取得します。

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>戻り値

ユーザーがアプリケーションを制御している場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

ユーザーが新しいドキュメントを明示的に開くか作成した場合、ユーザーはアプリケーションを制御します。 ユーザーは、OLE システム Dll によってアプリケーションが起動されなかった場合 (つまり、ユーザーがシステムシェルでアプリケーションを起動した場合) にも制御されます。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a> AfxOleSetUserCtrl

ユーザーコントロールフラグを設定または解除します。詳細については、「」を参照して `AfxOleGetUserCtrl` ください。

```cpp
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>パラメーター

*bUserCtrl*<br/>
ユーザー制御フラグを設定するか、またはクリアするかを指定します。

### <a name="remarks"></a>解説

フレームワークは、ユーザーがドキュメントを作成または読み込むときに、この関数を呼び出します。ただし、コンテナーアプリケーションからの埋め込みオブジェクトの読み込みなど、間接的なアクションによってドキュメントが読み込まれたり、作成されたりした場合には呼び出されません。

アプリケーションの他のアクションでユーザーがアプリケーションを制御する必要がある場合は、この関数を呼び出します。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolelockapp"></a><a name="afxolelockapp"></a> Afxolelockapp 呼び出し

アプリケーション内のアクティブなオブジェクトの数の、フレームワークのグローバルカウントをインクリメントします。

```cpp
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>解説

フレームワークは、アプリケーションでアクティブになっているオブジェクトの数を保持します。 `AfxOleLockApp`関数と `AfxOleUnlockApp` 関数はそれぞれ、このカウントをインクリメントおよびデクリメントします。

アクティブなオブジェクトを含むアプリケーション (アクティブなオブジェクトの数が0以外のアプリケーション) を終了しようとすると、フレームワークはアプリケーションを完全にシャットダウンするのではなく、ユーザーのビューから非表示にします。 関数は、 `AfxOleCanExitApp` アプリケーションを終了できるかどうかを示します。

`AfxOleLockApp`クライアントアプリケーションによって使用されているときに、そのオブジェクトが破棄されることが望ましくない場合は、OLE インターフェイスを公開する任意のオブジェクトからを呼び出します。 また、 `AfxOleUnlockApp` コンストラクター内でを呼び出すオブジェクトのデストラクターでを呼び出し `AfxOleLockApp` ます。 既定では、 `COleDocument` (および派生クラス) によってアプリケーションが自動的にロックされ、ロックが解除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxoleunlockapp"></a><a name="afxoleunlockapp"></a> AfxOleUnlockApp

アプリケーション内のフレームワークのアクティブなオブジェクトの数をデクリメントします。

```cpp
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>解説

詳細については、「」を参照してください `AfxOleLockApp` 。

アクティブなオブジェクトの数がゼロになると、 `AfxOleOnReleaseAllObjects` が呼び出されます。

### <a name="example"></a>例

[Afxolelockapp 呼び出し](#afxolelockapp)の例を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

コントロールに関連付けられた動的に作成されたデータがメモリ内に保持されるように、指定したコントロールのクラスファクトリをロックします。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
コントロールの一意のクラス ID。

*lpszProgID*<br/>
コントロールの一意のプログラム ID。

### <a name="return-value"></a>戻り値

コントロールのクラスファクトリが正常にロックされた場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

これにより、コントロールの表示速度を大幅に向上させることができます。 たとえば、ダイアログボックスでコントロールを作成し、を使用してコントロールをロックした場合、 `AfxOleLockControl` ダイアログが表示または破棄されるたびに、コントロールを作成して強制終了する必要はありません。 ユーザーがダイアログボックスを繰り返し開いて閉じた場合は、コントロールをロックすることでパフォーマンスを大幅に向上させることができます。 コントロールを破棄する準備ができたら、を呼び出し `AfxOleUnlockControl` ます。

### <a name="example"></a>例

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a> AfxOleRegisterServerClass

この関数を使用すると、サーバーを OLE システムレジストリに登録できます。

```
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,
    LPCTSTR lpszClassName,
    LPCTSTR lpszShortTypeName,
    LPCTSTR lpszLongTypeName,
    OLE_APPTYPE nAppType = OAT_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
サーバーの OLE クラス ID への参照。

*lpszClassName*<br/>
サーバーのオブジェクトのクラス名を格納している文字列へのポインター。

*Lpsz短い Typename*<br/>
サーバーのオブジェクト型の短い名前 ("Chart" など) を含む文字列へのポインター。

*lpszLongTypeName*<br/>
サーバーのオブジェクトの種類の長い名前 ("Microsoft Excel 5.0 Chart" など) を含む文字列へのポインター。

*nAppType*<br/>
OLE_APPTYPE 列挙体から取得した、OLE アプリケーションの種類を指定する値。 次の値を指定できます。

- OAT_INPLACE_SERVER サーバーにはサーバーの完全なユーザーインターフェイスがあります。

- OAT_SERVER サーバーでは、埋め込みのみがサポートされます。

- OAT_CONTAINER コンテナーは、埋め込みへのリンクをサポートしています。

- OAT_DISPATCH_OBJECT `IDispatch` 対応のオブジェクト。

*rglpszRegister*<br/>
キーの既存の値が見つからない場合に、OLE システムレジストリに追加するキーと値を表す文字列へのポインターの配列。

*rglpszOverwrite*<br/>
レジストリに指定されたキーの既存の値が含まれている場合に、OLE システムレジストリに追加するキーと値を表す文字列へのポインターの配列。

### <a name="return-value"></a>戻り値

サーバークラスが正常に登録された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

ほとんどのアプリケーションは `COleTemplateServer::Register` 、を使用して、アプリケーションのドキュメントの種類を登録できます。 アプリケーションのシステムレジストリ形式が一般的なパターンに合わない場合は、を使用して `AfxOleRegisterServerClass` より詳細な制御を行うことができます。

レジストリは、一連のキーと値で構成されます。 *Rglpszregister*引数と*Rglpszregister*引数は、文字列へのポインターの配列です。各文字列は、キーと、 **NULL**文字 () で区切られた値で構成され `'\0'` ます。 これらの各文字列には、文字シーケンス *%1* ~ *%5*でマークされた置換可能なパラメーターを含めることができます。

シンボルは次のように入力されます。

|Symbol|値|
|------------|-----------|
|%1|クラス ID。文字列として書式設定されます。|
|%2|クラス名|
|%3|実行可能ファイルへのパス|
|%4|短い型名|
|%5|長い型名|

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a> AfxOleSetEditMenu

*Typename*オブジェクトコマンドのユーザーインターフェイスを実装します。

```cpp
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,
    CMenu* pMenu,
    UINT iMenuItem,
    UINT nIDVerbMin,
    UINT nIDVerbMax = 0,
    UINT nIDConvert = 0);
```

### <a name="parameters"></a>パラメーター

*pClient*<br/>
クライアント OLE 項目へのポインター。

*pMenu*<br/>
更新するメニューオブジェクトへのポインター。

*iMenuItem*<br/>
更新するメニュー項目のインデックス。

*nIDVerbMin*<br/>
プライマリ動詞に対応するコマンド ID。

*nIDVerbMax*<br/>
最後の動詞に対応するコマンド ID。

*nIDConvert*<br/>
[変換] メニュー項目の ID。

### <a name="remarks"></a>解説

サーバーがプライマリ動詞のみを認識すると、メニュー項目は "動詞 *typename* Object" になり、ユーザーがコマンドを選択すると *nIDVerbMin* コマンドが送信されます。 サーバーで複数の動詞が認識されている場合、メニュー項目は " *typename* Object" になり、ユーザーがコマンドを選択すると、すべての動詞の一覧を示すサブメニューが表示されます。 ユーザーがサブメニューから動詞を選択すると、最初の動詞が選択されると *nIDVerbMin* が送信され、2番目の動詞が選択されている場合は *nIDVerbMin* + 1 が送信されます。 既定の実装では、 `COleDocument` この機能が自動的に処理されます。

クライアントのアプリケーションリソーススクリプト () には、次のステートメントが必要です。RC) ファイル:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>必要条件

**ヘッダー**: afxole

## <a name="afxoleunlockcontrol"></a><a name="afxoleunlockcontrol"></a> AfxOleUnlockControl

指定したコントロールのクラスファクトリのロックを解除します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
コントロールの一意のクラス ID。

*lpszProgID*<br/>
コントロールの一意のプログラム ID。

### <a name="return-value"></a>戻り値

コントロールのクラスファクトリが正常にロック解除された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

コントロールは `AfxOleLockControl` 、コントロールに関連付けられた動的に作成されたデータがメモリ内に保持されるように、でロックされます。 これにより、コントロールが表示されるたびにコントロールを作成したり破棄したりする必要がないため、コントロールの表示速度を大幅に向上させることができます。 コントロールを破棄する準備ができたら、を呼び出し `AfxOleUnlockControl` ます。

### <a name="example"></a>例

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
