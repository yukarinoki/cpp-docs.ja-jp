---
description: 詳細については、「デバッグとエラー報告のマクロ」を参照してください。
title: デバッグとエラー報告のマクロ
ms.date: 05/06/2019
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
ms.openlocfilehash: 573c3f341ff9f9df58337b75e1080dde960d232c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139946"
---
# <a name="debugging-and-error-reporting-macros"></a>デバッグとエラー報告のマクロ

これらのマクロは、便利なデバッグ機能とトレース機能を提供します。

|名前|説明|
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|が呼び出されたときに検出されたインターフェイスリークを出力ウィンドウに書き込み `_Module.Term` ます。|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|のすべての呼び出しを `QueryInterface` 出力ウィンドウに書き込みます。|
|[ATLASSERT](#atlassert)|は、C ランタイムライブラリの [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) マクロと同じ機能を実行します。|
|[ATLENSURE 保証](#atlensure)|パラメーターの検証を実行します。 必要に応じて呼び出す `AtlThrow`|
|[ATLTRACENOTIMPL](#atltracenotimpl)|指定された関数が実装されていないことをダンプデバイスにメッセージを送信します。|
|[ATLTRACE](#atltrace)|は、指定されたフラグとレベルに従って、デバッガーウィンドウなどの出力デバイスに警告を報告します。 旧バージョンとの互換性のために用意されています。|
|[ATLTRACE2](#atltrace2)|は、指定されたフラグとレベルに従って、デバッガーウィンドウなどの出力デバイスに警告を報告します。|

## <a name="_atl_debug_interfaces"></a><a name="_atl_debug_interfaces"></a> _ATL_DEBUG_INTERFACES

すべてをトレースし、 `AddRef` `Release` コンポーネントのインターフェイスでの呼び出しを出力ウィンドウに追加する ATL ヘッダーファイルを含める前に、このマクロを定義します。

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>解説

トレース出力は次のように表示されます。

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

各トレースの最初の部分は常に `ATL: QIThunk` です。 次に、使用される特定の *インターフェイスサンク* を識別する値を指定します。 インターフェイスサンクは、参照カウントを維持し、ここで使用されるトレース機能を提供するために使用されるオブジェクトです。 インターフェイスの要求を除き、のすべての呼び出しに対して新しいインターフェイスサンクが作成され `QueryInterface` `IUnknown` ます (この場合、COM の id 規則に準拠するために毎回同じサンクが返されます)。

次に、呼び出されたメソッドを確認し `AddRef` `Release` ます。 その後、インターフェイス参照カウントが変更されたオブジェクトを識別する値が表示されます。 トレースされる値は、 **`this`** オブジェクトのポインターです。

トレースされた参照カウントは、 `AddRef` またはが呼び出された後の、そのサンクの参照カウントです `Release` 。 この参照カウントは、オブジェクトの参照カウントと一致しない場合があることに注意してください。 各サンクは、COM の参照カウント規則に完全に準拠できるように、独自の参照カウントを保持します。

トレースされる情報の最後の部分は、オブジェクトの名前と、またはの呼び出しによって影響を受けるインターフェイスです `AddRef` `Release` 。

サーバーがシャットダウンして呼び出されたときに検出されたインターフェイスリークは、次の `_Module.Term` ようにログに記録されます。

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

ここに示されている情報は、前のトレースステートメントで提供された情報に直接マップされるため、インターフェイスサンクの全体の有効期間全体にわたって参照カウントを調べることができます。 さらに、そのインターフェイスサンクの最大参照カウントを示す値を取得します。

> [!NOTE]
> _ATL_DEBUG_INTERFACES は、リテールビルドで使用できます。

## <a name="_atl_debug_qi"></a><a name="_atl_debug_qi"></a> _ATL_DEBUG_QI

のすべての呼び出しを `QueryInterface` 出力ウィンドウに書き込みます。

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>解説

の呼び出しが失敗した場合 `QueryInterface` 、[出力] ウィンドウには次のように表示されます。

*インターフェイス名* - `failed`

## <a name="atlassert"></a><a name="atlassert"></a> ATLASSERT

ATLASSERT マクロは、C ランタイムライブラリの [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) マクロと同じ機能を実行します。

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>パラメーター

*booleanExpression*<br/>
0以外または0に評価される式 (ポインターを含む)。

### <a name="remarks"></a>解説

デバッグビルドでは、ATLASSERT は *booleanExpression* を評価し、結果が false の場合にデバッグレポートを生成します。

### <a name="requirements"></a>要件

**ヘッダー:** atldef. h

## <a name="atlensure"></a><a name="atlensure"></a> ATLENSURE 保証

このマクロは、関数に渡されるパラメーターを検証するために使用されます。

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>パラメーター

*booleanExpression*<br/>
テストするブール式を指定します。

*時間*<br/>
返されるエラーコードを指定します。

### <a name="remarks"></a>解説

これらのマクロは、不適切なパラメーターの使用を検出してユーザーに通知するメカニズムを提供します。

マクロは ATLASSERT を呼び出し、条件が呼び出しに失敗した場合はを呼び出し `AtlThrow` ます。

ATLENSURE で `AtlThrow` は、が E_FAIL を使用して呼び出されます。

ATLENSURE_THROW の場合、 `AtlThrow` 指定した HRESULT を使用してが呼び出されます。

ATLENSURE と ATLASSERT の違いは、ATLENSURE はリリースビルドだけでなくデバッグビルドでも例外をスローすることです。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

### <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="atltracenotimpl"></a><a name="atltracenotimpl"></a> ATLTRACENOTIMPL

ATL のデバッグビルドでは、によって文字列 " *funcname* は実装されていません" がダンプデバイスに送信され、E_NOTIMPL が返されます。

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>パラメーター

*funcname*<br/>
から実装されていない関数の名前を含む文字列。

### <a name="remarks"></a>解説

リリースビルドでは、は単に E_NOTIMPL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

### <a name="requirements"></a>要件

**ヘッダー:** atltrace .h

## <a name="atltrace"></a><a name="atltrace"></a> ATLTRACE

は、指定されたフラグとレベルに従って、デバッガーウィンドウなどの出力デバイスに警告を報告します。 旧バージョンとの互換性のために用意されています。

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>パラメーター

*exp*<br/>
から出力ウィンドウまたはこれらのメッセージをトラップする任意のアプリケーションに送信する文字列と変数。

*category*<br/>
から報告するイベントまたはメソッドの種類。 カテゴリの一覧については、「解説」を参照してください。

*level*<br/>
からレポートするトレースのレベル。 詳細については、「解説」を参照してください。

*lpszFormat*<br/>
からダンプデバイスに送信する、書式設定された文字列。

### <a name="remarks"></a>解説

ATLTRACE の詳細については、「 [ATLTRACE2](#atltrace2) 」を参照してください。 ATLTRACE と ATLTRACE2 の動作は同じですが、旧バージョンとの互換性のために ATLTRACE が含まれています。

## <a name="atltrace2"></a><a name="atltrace2"></a> ATLTRACE2

は、指定されたフラグとレベルに従って、デバッガーウィンドウなどの出力デバイスに警告を報告します。

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>パラメーター

*exp*<br/>
から出力ウィンドウまたはこれらのメッセージをトラップするアプリケーションに送信する文字列。

*category*<br/>
から報告するイベントまたはメソッドの種類。 カテゴリの一覧については、「解説」を参照してください。

*level*<br/>
からレポートするトレースのレベル。 詳細については、「解説」を参照してください。

*lpszFormat*<br/>
から `printf`ダンプデバイスに送信する文字列を作成するために使用するスタイルの書式指定文字列。

### <a name="remarks"></a>解説

短い形式の ATLTRACE2 は、デバッガーの出力ウィンドウに文字列を書き込みます。 2番目の形式の ATLTRACE2 は、デバッガーの出力ウィンドウにも出力を書き込みますが、ATL/MFC トレースツールの設定の対象となります (「 [Atltracetool Sample](../../overview/visual-cpp-samples.md)」を参照してください)。 たとえば、 *level* を4に設定し、ATL/MFC トレースツールをレベル0に設定した場合、メッセージは表示されません。 *level* には、0、1、2、3、または4を指定できます。 既定値は0で、最も重大な問題だけが報告されます。

*Category* パラメーターは、設定するトレースフラグを一覧表示します。 これらのフラグは、レポートを作成するメソッドの種類に対応しています。 次の表は、 *category* パラメーターに使用できる有効なトレースフラグを示しています。

### <a name="atl-trace-flags"></a>ATL トレースフラグ

|ATL カテゴリ|説明|
|------------------|-----------------|
|`atlTraceGeneral`|すべての ATL アプリケーションに関するレポートを作成します。 これが既定値です。|
|`atlTraceCOM`|COM メソッドに関するレポートを作成します。|
|`atlTraceQI`|QueryInterface 呼び出しを報告します。|
|`atlTraceRegistrar`|オブジェクトの登録に関するレポートを作成します。|
|`atlTraceRefcount`|参照カウントが変更されたことを報告します。|
|`atlTraceWindowing`|Windows のメソッドに関するレポートたとえば、は無効なメッセージマップ ID を報告します。|
|`atlTraceControls`|コントロールに関するレポートたとえば、コントロールまたはウィンドウが破棄されたことを報告します。|
|`atlTraceHosting`|メッセージをホストしているレポートたとえば、コンテナー内のクライアントがアクティブ化されたことを報告します。|
|`atlTraceDBClient`|OLE DB コンシューマーテンプレートに関するレポートたとえば、GetData の呼び出しが失敗した場合、出力には HRESULT を含めることができます。|
|`atlTraceDBProvider`|OLE DB プロバイダーテンプレートに関するレポートたとえば、は、列の作成に失敗したかどうかを報告します。|
|`atlTraceSnapin`|MMC スナップインアプリケーションのレポート。|
|`atlTraceNotImpl`|指定された関数が実装されていないことを報告します。|
|`atlTraceAllocation`|Atldbgmem のメモリデバッグツールによって出力されたメッセージを報告します。|

### <a name="mfc-trace-flags"></a>MFC トレースフラグ

|MFC カテゴリ|説明|
|------------------|-----------------|
|`traceAppMsg`|汎用、MFC メッセージ。 常にお勧めします。|
|`traceDumpContext`|[CDumpContext](../../mfc/reference/cdumpcontext-class.md)からのメッセージ。|
|`traceWinMsg`|MFC のメッセージ処理コードからのメッセージ。|
|`traceMemory`|MFC のメモリ管理コードからのメッセージ。|
|`traceCmdRouting`|MFC の Windows コマンドルーティングコードからのメッセージ。|
|`traceHtml`|MFC の DHTML ダイアログサポートからのメッセージ。|
|`traceSocket`|MFC のソケットサポートからのメッセージ。|
|`traceOle`|MFC の OLE サポートからのメッセージ。|
|`traceDatabase`|MFC のデータベースサポートからのメッセージ。|
|`traceInternet`|MFC のインターネットサポートからのメッセージ。|

カスタムトレースカテゴリを宣言するには、次のようにクラスのグローバルインスタンスを宣言し `CTraceCategory` ます。

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

この例で MY_CATEGORY カテゴリ名は *category* パラメーターに指定した名前です。 最初のパラメーターは、ATL/MFC トレースツールに表示されるカテゴリ名です。 2番目のパラメーターは、既定のトレースレベルです。 このパラメーターは省略可能で、既定のトレースレベルは0です。

ユーザー定義のカテゴリを使用するには:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

トレースメッセージをフィルター処理するように指定するには、ステートメントの前にこれらのマクロの定義を Stdafx.h に挿入します。 `#include <atlbase.h>`

または、[ **プロパティページ** ] ダイアログボックスで、プリプロセッサディレクティブのフィルターを設定することもできます。 [ **プリプロセッサ** ] タブをクリックし、[ **プリプロセッサの定義** ] 編集ボックスにグローバルを挿入します。

Atlbase. h には ATLTRACE2 マクロの既定の定義が含まれており、これらの定義は、atlbase. h が処理される前にこれらのシンボルを定義しない場合に使用されます。

リリースビルドでは、ATLTRACE2 はにコンパイルさ `(void) 0` れます。

ATLTRACE2 は、ダンプデバイスに送信される文字列の内容を、書式設定後の1023文字以下に制限します。

ATLTRACE と ATLTRACE2 の動作は同じですが、旧バージョンとの互換性のために ATLTRACE が含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)<br/>
[デバッグとエラー報告のグローバル関数](../../atl/reference/debugging-and-error-reporting-global-functions.md)
