---
title: アプリケーションの制御
ms.date: 11/04/2016
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 7e18b4504ddbfdd9a4399f33c34c6e6e9900233b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752858"
---
# <a name="application-control"></a>アプリケーションの制御

OLE では、アプリケーションとそのオブジェクトを大幅に制御する必要があります。 OLE システム DLL は、アプリケーションを自動的に起動および解放し、オブジェクトの生成や変更を調整できる必要があります。 このトピックの機能は、これらの要件を満たしています。 OLE システム DLL によって呼び出されるだけでなく、これらの関数もアプリケーションから呼び出す必要があります。

### <a name="application-control"></a>アプリケーションの制御

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|アプリケーションを終了できるかどうかを示します。|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|アプリケーションの現在のメッセージ フィルターを取得します。|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|現在のユーザー コントロール フラグを取得します。|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|ユーザー コントロール フラグを設定またはクリアします。|
|[AfxOleLockApp](#afxolelockapp)|アプリケーション内のアクティブなオブジェクトの数のフレームワークのグローバルカウントをインクリメントします。|
|[AfxOleLockControl](#afxolelockcontrol)| 指定したコントロールのクラス ファクトリをロックします。 |
|[AfxOleUnlockApp](#afxoleunlockapp)|アプリケーション内のアクティブなオブジェクトの数のフレームワークのカウントをデクリメントします。|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| 指定したコントロールのクラス ファクトリのロックを解除します。 |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE システム レジストリにサーバーを登録します。|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|*typename*オブジェクト コマンドのユーザー インターフェイスを実装します。|

## <a name="afxolecanexitapp"></a><a name="afxolecanexitapp"></a>アプソアスキャンエグジットアプリ

アプリケーションを終了できるかどうかを示します。

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>戻り値

アプリケーションが終了できる場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

アプリケーションのオブジェクトへの未解決の参照がある場合、アプリケーションを終了しないでください。 グローバル関数`AfxOleLockApp`と`AfxOleUnlockApp`インクリメントとデクリメントは、それぞれ、アプリケーションのオブジェクトへの参照のカウンターです。 このカウンタが 0 以外の場合、アプリケーションを終了しないでください。 カウンタが 0 以外の場合、ユーザーがシステム メニューから閉じるか、[ファイル] メニューの [終了] を選択すると、アプリケーションのメイン ウィンドウは非表示になります (破棄されません)。 フレームワークは、この関数を`CFrameWnd::OnClose`で呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>メッセージ フィルター

アプリケーションの現在のメッセージ フィルターを取得します。

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>戻り値

現在のメッセージ フィルターへのポインター。

### <a name="remarks"></a>解説

現在のアプリケーション オブジェクトにアクセス`COleMessageFilter`するために呼び出す`AfxGetApp`のと同じように、現在の派生オブジェクトにアクセスします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー**: afxwin.h

## <a name="afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>を取得します。

現在のユーザー コントロール フラグを取得します。

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>戻り値

ユーザーがアプリケーションを制御する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ユーザーが明示的に新しいドキュメントを開いたり作成したりすると、ユーザーはアプリケーションを制御できます。 ユーザーが OLE システム DLL によってアプリケーションを起動しなかった場合、つまり、ユーザーがシステム シェルを使用してアプリケーションを起動した場合、ユーザーは制御することもできます。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>アプソールセットユーザーCtrl

のリファレンスで説明されているユーザーコントロールフラグを設定またはクリアします`AfxOleGetUserCtrl`。

```cpp
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ユーザーコントロールフラグを設定するかクリアするかを指定します。

### <a name="remarks"></a>解説

フレームワークは、ユーザーがドキュメントを作成または読み込むときにこの関数を呼び出しますが、ドキュメントが読み込まれたり、コンテナー アプリケーションから埋め込みオブジェクトを読み込むなどの間接的なアクションによって作成されたりした場合は呼び出されません。

アプリケーション内の他のアクションがユーザーをアプリケーションの制御にする必要がある場合は、この関数を呼び出します。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolelockapp"></a><a name="afxolelockapp"></a>アfxOleロックアプリ

アプリケーション内のアクティブなオブジェクトの数のフレームワークのグローバルカウントをインクリメントします。

```cpp
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>解説

フレームワークは、アプリケーションでアクティブなオブジェクトの数を保持します。 関数`AfxOleLockApp`と`AfxOleUnlockApp`関数は、それぞれ、このカウントをインクリメントおよびデクリメントします。

アクティブなオブジェクト (アクティブなオブジェクトの数が 0 以外のアプリケーション) を持つアプリケーションを閉じようとすると、フレームワークはアプリケーションを完全にシャットダウンするのではなく、ユーザーのビューから隠します。 この`AfxOleCanExitApp`関数は、アプリケーションを終了できるかどうかを示します。

OLE`AfxOleLockApp`インターフェイスを公開するオブジェクトから呼び出す場合は、そのオブジェクトがクライアント アプリケーションで使用されている間に破棄される必要がない場合。 また、`AfxOleUnlockApp`コンストラクター内で呼び出すオブジェクトの`AfxOleLockApp`デストラクターも呼び出します。 既定では、(`COleDocument`および派生クラス) は、アプリケーションを自動的にロックおよびロック解除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxoleunlockapp"></a><a name="afxoleunlockapp"></a>アfxOleロックアプリ

アプリケーション内のアクティブなオブジェクトのフレームワークのカウントをデクリメントします。

```cpp
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>解説

詳細`AfxOleLockApp`については、「」を参照してください。

アクティブなオブジェクトの数がゼロになると呼`AfxOleOnReleaseAllObjects`び出されます。

### <a name="example"></a>例

[AfxOleLockApp](#afxolelockapp)の例を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

指定したコントロールのクラス ファクトリをロックして、コントロールに関連付けられた動的に作成されたデータがメモリ内に残るようにします。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
コントロールの一意のクラス ID。

*をクリックします。*<br/>
コントロールの一意のプログラム ID。

### <a name="return-value"></a>戻り値

コントロールのクラス ファクトリが正常にロックされた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

これにより、コントロールの表示が大幅に高速化されます。 たとえば、ダイアログ ボックスでコントロールを作成し、 で`AfxOleLockControl`コントロールをロックすると、ダイアログが表示または破棄されるたびに、コントロールを作成して終了する必要はありません。 ユーザーがダイアログ ボックスを繰り返し開いて閉じると、コントロールをロックするとパフォーマンスが大幅に向上します。 コントロールを破棄する準備ができたら、 を呼`AfxOleUnlockControl`び出します。

### <a name="example"></a>例

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>クラス

この関数を使用すると、OLE システム レジストリにサーバーを登録できます。

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

*Clsid*<br/>
サーバーの OLE クラス ID への参照。

*クラス名*<br/>
サーバーのオブジェクトのクラス名を含む文字列へのポインター。

*名前を指定します。*<br/>
サーバーのオブジェクトの種類の短い名前を含む文字列へのポインターです 。

*名前を指定します。*<br/>
"Excel 5.0 グラフ" など、サーバーのオブジェクトの種類の長い名前を含む文字列へのポインター。

*アプリの種類*<br/>
OLE アプリケーションの種類を指定して、OLE_APPTYPE列挙体から取得される値。 次の値を指定できます。

- OAT_INPLACE_SERVER サーバーには、サーバーのユーザー インターフェイスが完全に含まれています。

- OAT_SERVER サーバーは埋め込みのみをサポートしています。

- OAT_CONTAINER コンテナは埋め込みへのリンクをサポートしています。

- OAT_DISPATCH_OBJECT`IDispatch`可能なオブジェクトです。

*ルグルプスレジスタ*<br/>
キーの既存の値が見つからない場合に、OLE システム レジストリに追加するキーと値を表す文字列へのポインターの配列。

*上書き*<br/>
指定されたキーの既存の値がレジストリに含まれている場合に、OLE システム レジストリに追加するキーと値を表す文字列へのポインターの配列。

### <a name="return-value"></a>戻り値

サーバー クラスが正常に登録された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ほとんどのアプリケーションは、`COleTemplateServer::Register`アプリケーションのドキュメントタイプを登録するために使用できます。 アプリケーションのシステム レジストリ形式が一般的なパターンに適合しない場合は、より詳細`AfxOleRegisterServerClass`な制御を行うことができます。

レジストリは、キーと値のセットで構成されます。 *rglpszRegister*引数と*rglpszOverwrite*引数は、文字列へのポインターの配列であり、それぞれキーと**NULL**文字 ( )`'\0'`で区切られた値で構成されます。 これらの各文字列には、置換可能なパラメータを持*つことができます。* *%1*

シンボルは次のように入力されます。

|Symbol|値|
|------------|-----------|
|%1|クラス ID (文字列として書式設定)|
|%2|クラス名|
|%3|実行可能ファイルへのパス|
|%4|短い型名|
|%5|ロングタイプ名|

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>メニューを編集します。

*typename*オブジェクト コマンドのユーザー インターフェイスを実装します。

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

*クライアント*<br/>
クライアント OLE アイテムへのポインター。

*メニュー*<br/>
更新するメニュー オブジェクトへのポインター。

*メニュー項目*<br/>
更新するメニュー項目のインデックス。

*nIDVerbMin*<br/>
主動詞に対応するコマンド ID。

*最大の時間*<br/>
最後の動詞に対応するコマンド ID。

*変換を行う*<br/>
[変換] メニュー項目の ID です。

### <a name="remarks"></a>解説

サーバーが主動詞のみを認識する場合、メニュー項目は "動詞*型名*オブジェクト" になり、ユーザーがコマンドを選択すると*nIDVerbMin*コマンドが送信されます。 サーバーが複数の動詞を認識すると、メニュー項目は " *typename* Object " になり、ユーザーがコマンドを選択すると、すべての動詞を一覧表示するサブメニューが表示されます。 ユーザーがサブメニューから動詞を選択すると、最初の動詞が選択されると*nIDVerbMin*が送信され、2 番目の動詞が選択された場合は*nIDVerbMin* + 1 が送信されます。 既定`COleDocument`の実装では、この機能が自動的に処理されます。

クライアントのアプリケーション リソース スクリプト (.RC) ファイル:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>必要条件

**ヘッダー**: afxole.h

## <a name="afxoleunlockcontrol"></a><a name="afxoleunlockcontrol"></a>コントロールをロックします。

指定したコントロールのクラス ファクトリのロックを解除します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
コントロールの一意のクラス ID。

*をクリックします。*<br/>
コントロールの一意のプログラム ID。

### <a name="return-value"></a>戻り値

コントロールのクラス ファクトリのロックが正常に解除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

コントロールは で`AfxOleLockControl`ロックされるため、コントロールに関連付けられた動的に作成されたデータはメモリ内に残ります。 これにより、コントロールが表示されるたびにコントロールを作成および破棄する必要がないため、コントロールの表示速度が大幅に向上します。 コントロールを破棄する準備ができたら、 を呼`AfxOleUnlockControl`び出します。

### <a name="example"></a>例

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
