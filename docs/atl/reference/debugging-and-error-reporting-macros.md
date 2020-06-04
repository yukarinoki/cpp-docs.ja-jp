---
title: デバッグおよびエラー報告マクロ
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
ms.openlocfilehash: 69ab6e17bfb1ec85ddb5b8c19c18010a9b4f3df6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330184"
---
# <a name="debugging-and-error-reporting-macros"></a>デバッグおよびエラー報告マクロ

これらのマクロは、デバッグ機能とトレース機能を提供します。

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|呼び出されたときに`_Module.Term`検出されたインターフェイス リークを出力ウィンドウに書き込みます。|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|すべての呼び出`QueryInterface`しを出力ウィンドウに書き込みます。|
|[アサート](#atlassert)|C ランタイム ライブラリにある[_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロと同じ機能を実行します。|
|[アトルレエード](#atlensure)|パラメーターの検証を実行します。 必要`AtlThrow`に応じて通話する|
|[アトルトレーストレンプル](#atltracenotimpl)|指定された関数が実装されていないメッセージをダンプ デバイスに送信します。|
|[ATLトレース](#atltrace)|示されたフラグとレベルに従って、デバッガー ウィンドウなどの出力デバイスに警告を報告します。 下位互換性のために含まれています。|
|[ATLTRACE2](#atltrace2)|示されたフラグとレベルに従って、デバッガー ウィンドウなどの出力デバイスに警告を報告します。|

## <a name="_atl_debug_interfaces"></a><a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES

すべての`AddRef`トレースを行う ATL ヘッダー ファイルをインクルード`Release`する前に、このマクロを定義し、コンポーネントのインターフェイスを出力ウィンドウに呼び出します。

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>解説

トレース出力は、次のように表示されます。

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

各トレースの最初の部分は常に`ATL: QIThunk`です。 次に、使用されている特定の*インターフェイス サンクを*識別する値です。 インターフェイス サンクは、参照カウントを維持し、ここで使用されるトレース機能を提供するために使用されるオブジェクトです。 インターフェイスの要求`QueryInterface``IUnknown`を除くすべての呼び出しで新しいインターフェイス サンクが作成されます (この場合、COM の ID ルールに準拠するために毎回同じサンクが返されます)。

次に、呼び`AddRef`出`Release`されたメソッドを表示または示します。 その後、インターフェイス参照カウントが変更されたオブジェクトを識別する値が表示されます。 トレースされる値は、オブジェクトの**this**ポインターです。

トレースされる参照カウントは、そのサンク`AddRef``Release`の参照カウントです。 この参照カウントは、オブジェクトの参照カウントと一致しない場合があることに注意してください。 各サンクは、COM の参照カウント規則に完全に準拠できるように、独自の参照カウントを保持します。

トレースされる最後の情報は、オブジェクトの名前と、 または`AddRef``Release`呼び出しによって影響を受けるインターフェイスです。

サーバーのシャットダウン時に検出されたインターフェイス リークは、`_Module.Term`次のように記録されます。

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

ここで提供される情報は、前のトレース ステートメントで提供された情報に直接マップされるため、インターフェイス サンクの有効期間全体を通して参照カウントを調べることができます。 さらに、そのインターフェイス サンクの最大参照カウントを示します。

> [!NOTE]
> _ATL_DEBUG_INTERFACESは、製品版のビルドで使用できます。

## <a name="_atl_debug_qi"></a><a name="_atl_debug_qi"></a>_ATL_DEBUG_QI

すべての呼び出`QueryInterface`しを出力ウィンドウに書き込みます。

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>解説

呼び出し`QueryInterface`が失敗した場合、出力ウィンドウが表示されます。

*インターフェイス名* - `failed`

## <a name="atlassert"></a><a name="atlassert"></a>アサート

ATLASSERT マクロは、C ランタイム ライブラリにある[_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロと同じ機能を実行します。

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
0 以外の値または 0 に評価される式 (ポインターを含む)。

### <a name="remarks"></a>解説

デバッグ ビルドでは、ATLASSERT は*ブール式*を評価し、結果が false の場合にデバッグ レポートを生成します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldef.h

## <a name="atlensure"></a><a name="atlensure"></a>アトルレエード

このマクロは、関数に渡されるパラメーターを検証するために使用されます。

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
テストするブール式を指定します。

*人事*<br/>
返すエラー コードを指定します。

### <a name="remarks"></a>解説

これらのマクロは、誤ったパラメーターの使用を検出してユーザーに通知するメカニズムを提供します。

マクロは ATLASSERT を呼び出し`AtlThrow`、条件が失敗した場合は 呼び出し。

ATLENSURE の場合、E_FAIL`AtlThrow`と呼ばれます。

ATLENSURE_THROWの場合、`AtlThrow`指定された HRESULT を使用して呼び出されます。

ATLENSURE と ATLASSERT の違いは、リリース ビルドとデバッグ ビルドで、ATLENSURE が例外をスローすることです。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="atltracenotimpl"></a><a name="atltracenotimpl"></a>アトルトレーストレンプル

ATL のデバッグ ビルドでは、文字列 *"funcname*が実装されていません" をダンプ デバイスに送信し、E_NOTIMPL返します。

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>パラメーター

*ファンクナ*<br/>
[in]実装されていない関数の名前を含む文字列。

### <a name="remarks"></a>解説

リリース ビルドでは、単にE_NOTIMPLを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** atltrace.h

## <a name="atltrace"></a><a name="atltrace"></a>ATLトレース

示されたフラグとレベルに従って、デバッガー ウィンドウなどの出力デバイスに警告を報告します。 下位互換性のために含まれています。

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>パラメーター

*Exp*<br/>
[in]出力ウィンドウまたはこれらのメッセージをトラップするアプリケーションに送信する文字列と変数。

*カテゴリ*<br/>
[in]報告するイベントまたはメソッドの種類。 カテゴリの一覧については、「解説」を参照してください。

*レベル*<br/>
[in]レポートするトレースのレベル。 詳細については、「解説」を参照してください。

*フォーマット*<br/>
[in]ダンプ デバイスに送信する書式指定文字列。

### <a name="remarks"></a>解説

[ATLTRACE](#atltrace2)の説明については、ATLTRACE2 を参照してください。 ATLTRACE と ATLTRACE2 の動作は同じですが、後方互換性のために ATLTRACE が含まれています。

## <a name="atltrace2"></a><a name="atltrace2"></a>ATLTRACE2

示されたフラグとレベルに従って、デバッガー ウィンドウなどの出力デバイスに警告を報告します。

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>パラメーター

*Exp*<br/>
[in]出力ウィンドウまたはこれらのメッセージをトラップする任意のアプリケーションに送信する文字列。

*カテゴリ*<br/>
[in]報告するイベントまたはメソッドの種類。 カテゴリの一覧については、「解説」を参照してください。

*レベル*<br/>
[in]レポートするトレースのレベル。 詳細については、「解説」を参照してください。

*フォーマット*<br/>
[in]ダンプ`printf`デバイスに送信する文字列を作成するために使用する -style 書式指定文字列。

### <a name="remarks"></a>解説

ATLTRACE2 の短い形式では、デバッガーの出力ウィンドウに文字列を書き込みます。 ATLTRACE2 の 2 番目の形式も、デバッガーの出力ウィンドウに出力を書き込みますが、ATL/MFC トレース ツールの設定に従います[(ATLTraceTool サンプル](../../overview/visual-cpp-samples.md)を参照)。 たとえば、*レベル*を 4 に設定し、ATL/MFC トレース ツールをレベル 0 に設定した場合、メッセージは表示されません。 *レベル*は、0、1、2、3、または4にすることができます。 デフォルトの 0 は、最も重大な問題のみを報告します。

*category*パラメーターは、設定するトレース フラグを一覧表示します。 これらのフラグは、報告するメソッドの型に対応します。 次の表は *、category*パラメーターに使用できる有効なトレース フラグを示しています。

### <a name="atl-trace-flags"></a>ATL トレース フラグ

|ATL カテゴリ|説明|
|------------------|-----------------|
|`atlTraceGeneral`|すべての ATL アプリケーションについて報告します。 これが既定値です。|
|`atlTraceCOM`|COM メソッドに関するレポート。|
|`atlTraceQI`|クエリ インターフェイス呼び出しを報告します。|
|`atlTraceRegistrar`|オブジェクトの登録に関するレポートを作成します。|
|`atlTraceRefcount`|参照カウントの変更に関するレポート。|
|`atlTraceWindowing`|ウィンドウメソッドに関するレポート。たとえば、無効なメッセージ マップ ID が報告されます。|
|`atlTraceControls`|コントロールに関するレポート。たとえば、コントロールまたはそのウィンドウが破棄された場合に報告します。|
|`atlTraceHosting`|メッセージをホストしているレポート。たとえば、コンテナー内のクライアントがアクティブ化されたときにレポートします。|
|`atlTraceDBClient`|OLE DB コンシューマー テンプレートに関するレポート。たとえば、GetData の呼び出しが失敗した場合、出力には HRESULT を含めることができます。|
|`atlTraceDBProvider`|OLE DB プロバイダ テンプレートに関するレポート。たとえば、列の作成に失敗した場合に報告します。|
|`atlTraceSnapin`|MMC スナップイン アプリケーションのレポート。|
|`atlTraceNotImpl`|指定された関数が実装されていないレポートです。|
|`atlTraceAllocation`|atldbgmem.h のメモリ デバッグ ツールによって出力されたメッセージを報告します。|

### <a name="mfc-trace-flags"></a>MFC トレース フラグ

|MFC カテゴリ|説明|
|------------------|-----------------|
|`traceAppMsg`|汎用、MFC メッセージ。 常にお勧めします。|
|`traceDumpContext`|[CDump コンテキスト](../../mfc/reference/cdumpcontext-class.md)からのメッセージ 。|
|`traceWinMsg`|MFC のメッセージ処理コードからのメッセージ。|
|`traceMemory`|MFC のメモリ管理コードからのメッセージ。|
|`traceCmdRouting`|MFC の Windows コマンド ルーティング コードからのメッセージ。|
|`traceHtml`|MFC の DHTML ダイアログ サポートからのメッセージ。|
|`traceSocket`|MFC のソケット サポートからのメッセージ。|
|`traceOle`|MFC の OLE サポートからのメッセージ。|
|`traceDatabase`|MFC のデータベース サポートからのメッセージ。|
|`traceInternet`|MFC のインターネット サポートからのメッセージ。|

カスタム トレース カテゴリを宣言するには、次のようにクラスの`CTraceCategory`グローバル インスタンスを宣言します。

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

この例では、カテゴリ名*MY_CATEGORY、category*パラメーターに指定する名前です。 最初のパラメーターは、ATL/MFC トレース ツールに表示されるカテゴリ名です。 2 番目のパラメーターは、既定のトレース レベルです。 このパラメーターはオプションで、デフォルトのトレース・レベルは 0 です。

ユーザー定義のカテゴリを使用するには

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

トレース メッセージをフィルター処理するように指定するには、ステートメントの前にこれらのマクロの定義を Stdafx.h に挿入します`#include <atlbase.h>`。

または、[**プロパティ ページ**] ダイアログ ボックスのプリプロセッサ ディレクティブでフィルタを設定することもできます。 [**プリプロセッサ**] タブをクリックし、グローバルを **[プリプロセッサ定義**] 編集ボックスに挿入します。

Atlbase.h には ATLTRACE2 マクロの既定の定義が含まれ、atlbase.h が処理される前にこれらのシンボルを定義しない場合は、これらの定義が使用されます。

リリース ビルドでは、ATLTRACE2 は`(void) 0`にコンパイルします。

ATLTRACE2 は、フォーマット後にダンプ・デバイスに送信されるストリングの内容を 1023 文字以下に制限します。

ATLTRACE と ATLTRACE2 の動作は同じですが、後方互換性のために ATLTRACE が含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)<br/>
[グローバル関数のデバッグとエラー報告](../../atl/reference/debugging-and-error-reporting-global-functions.md)
