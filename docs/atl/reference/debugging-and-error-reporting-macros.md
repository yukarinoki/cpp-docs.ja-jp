---
title: デバッグとエラー報告のマクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
dev_langs:
- C++
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7100199d7e4ee76bf2f096aba9e20c244ae10ab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070565"
---
# <a name="debugging-and-error-reporting-macros"></a>デバッグとエラー報告のマクロ

これらのマクロは、便利なデバッグとトレース機能を提供します。

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|リークを任意のインターフェイスを出力ウィンドウに書き込みますが検出されたときに`_Module.Term`が呼び出されます。|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|すべての呼び出しを書き込みます`QueryInterface`出力ウィンドウにします。|
|[ATLASSERT](#atlassert)|同じ機能を実行、 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロは、C ランタイム ライブラリが見つかりません。|
|[ATLENSURE](#atlensure)|パラメーターの検証を実行します。 呼び出す`AtlThrow`必要な場合|
|[ATLTRACENOTIMPL](#atltracenotimpl)|指定した関数が実装されていないこと、ダンプ デバイスにメッセージを送信します。|
|[ATLTRACE](#alttrace)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。 旧バージョンとの互換性のために含まれています。|
|[ATLTRACE2](#atltrace2)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。|

##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES

すべてをトレースする ATL ヘッダー ファイルをインクルードする前にこのマクロを定義して`AddRef`と`Release`出力ウィンドウに、コンポーネントのインターフェイスを呼び出します。

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Remarks

次に示すように、トレース出力が表示されます。

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

各トレースの最初の部分は必ず`ATL: QIThunk`します。 次に、特にを識別する値は、*インターフェイス サンク*使用されています。 インターフェイス サンクは、参照カウントを維持し、ここで使用されるトレース機能を提供するために使用するオブジェクトです。 呼び出すたびに新しいインターフェイス サンクが作成された`QueryInterface`の要求を除き、`IUnknown`インターフェイス (この場合、同じサンクが返されますたびに COM の規則に準拠する)。

次に表示されます`AddRef`または`Release`呼び出されたメソッドを示します。 次に、そのインターフェイスの参照カウントが変更されたオブジェクトを識別する値が表示されます。 トレースされる値は、**この**オブジェクトのポインター。

トレースは、参照カウントが後にそのサンクの参照カウント`AddRef`または`Release`が呼び出されました。 この参照カウントでは、オブジェクトの参照カウントが一致しないことに注意してください。 各サンクは、COM の参照カウントの規則に完全に準拠するための独自の参照カウントを保持します。

トレース情報の最後の部分は、オブジェクトとに影響されるインターフェイスの名前、`AddRef`または`Release`呼び出します。

サーバーのシャット ダウン時に検出されたリーク インターフェイスと`_Module.Term`が呼び出されますがこのようなログに記録します。

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

インターフェイス サンクの有効期間全体を通じて、参照がカウントを調べることは、情報はここで指定した以前のトレース ステートメントで提供される情報に直接マップされます。 さらに、そのインターフェイス サンクの最大の参照カウントを示す値を取得します。

> [!NOTE]
> _ATL_DEBUG_INTERFACES は、製品版ビルドで使用できます。

##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI

すべての呼び出しを書き込みます`QueryInterface`出力ウィンドウにします。

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Remarks

呼び出し`QueryInterface`失敗、出力ウィンドウに表示されます。

*インターフェイス名* - `failed`

##  <a name="atlassert"></a>  ATLASSERT

ATLASSERT マクロと同じ機能を実行する、 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロは、C ランタイム ライブラリが見つかりません。

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
0 以外の値または 0 に評価される式 (ポインターを含む)。

### <a name="remarks"></a>Remarks

ATLASSERT を評価するデバッグ ビルドで*ブール式*し、結果が false の場合、デバッグ レポートを生成します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldef.h

##  <a name="atlensure"></a>  ATLENSURE

このマクロは、関数に渡されるパラメーターの検証に使用されます。

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
テストするブール式を指定します。

*hr*<br/>
返されるエラー コードを指定します。

### <a name="remarks"></a>Remarks

これらのマクロは、検出し、正しくないパラメーターの使用法のユーザーに通知するためのメカニズムを提供します。

ATLASSERT と条件に呼び出しが失敗したかどうか、マクロが呼び出す`AtlThrow`します。

ATLENSURE の場合、`AtlThrow`は E_FAIL で呼び出されます。

ATLENSURE_THROW の場合、`AtlThrow`は指定した HRESULT で呼び出されます。

ATLENSURE と ATLASSERT の違いは、ATLENSURE がリリース ビルドとデバッグ ビルドのようにに例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="atltracenotimpl"></a>  ATLTRACENOTIMPL

ATL のデバッグ ビルドでは、文字列を送信します。" *funcname*は実装されていません"に、ダンプ デバイスと E_NOTIMPL を返します。

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>パラメーター

*funcname*<br/>
[in]実装されていない関数の名前を含む文字列。

### <a name="remarks"></a>Remarks

リリース ビルドで単に E_NOTIMPL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** atltrace.h

##  <a name="atltrace"></a>  ATLTRACE

指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。 旧バージョンとの互換性のために含まれています。

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>パラメーター

*exp*<br/>
[in]文字列と、Visual C に送信する変数の出力ウィンドウまたはこれらのメッセージをトラップするアプリケーション。

*category*<br/>
[in]イベントまたはレポートをメソッドの型。 カテゴリの一覧については、「解説」を参照してください。

*レベル*<br/>
[in]レポートへのトレースのレベル。 詳細については、「解説」を参照してください。

*lpszFormat*<br/>
[in]ダンプ デバイスに送信する書式設定された文字列。

### <a name="remarks"></a>Remarks

参照してください[ATLTRACE2](#atltrace2) ATLTRACE の説明についてはします。 ATLTRACE ATLTRACE2 動作と同じ場合、ATLTRACE は旧バージョンとの互換性のために含まれています。

##  <a name="atltrace2"></a>  ATLTRACE2

指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```

### <a name="parameters"></a>パラメーター

*exp*<br/>
[in]Visual C の出力ウィンドウ、またはこれらのメッセージをトラップする任意のアプリケーションに送信する文字列。

*category*<br/>
[in]イベントまたはレポートをメソッドの型。 カテゴリの一覧については、「解説」を参照してください。

*レベル*<br/>
[in]レポートへのトレースのレベル。 詳細については、「解説」を参照してください。

*lpszFormat*<br/>
[in]`printf`-を使用して文字列を作成すると、ダンプ デバイスに送信する書式指定文字列のスタイルを設定します。

### <a name="remarks"></a>Remarks

ATLTRACE2 の短い形式は、デバッガーの出力ウィンドウに文字列を書き込みます。 ATLTRACE2 の 2 番目の形式も、デバッガーの出力ウィンドウに出力を書き込みますが、ATL/MFC トレース ツールの設定に従います (を参照してください[ATLTraceTool サンプル](../../visual-cpp-samples.md))。 たとえば、設定した場合*レベル*4 および ATL/MFC トレース ツールをレベル 0 の場合は、メッセージをしないに表示されます。 *レベル*0、1、2、3、または 4 にすることができます。 0 の場合、既定では、最も重大な問題だけを報告します。

*カテゴリ*パラメーターに設定するトレース フラグが一覧表示されます。 これらのフラグは、レポート方法の種類に対応します。 次の表は、使用できる有効なトレース フラグを一覧表示、*カテゴリ*パラメーター。

### <a name="atl-trace-flags"></a>ATL トレース フラグ

|ATL カテゴリ|説明|
|------------------|-----------------|
|`atlTraceGeneral`|ATL のすべてのアプリケーションについてレポートします。 これが既定値です。|
|`atlTraceCOM`|COM メソッドについてレポートします。|
|`atlTraceQI`|QueryInterface 呼び出しについてレポートします。|
|`atlTraceRegistrar`|オブジェクトの登録についてレポートします。|
|`atlTraceRefcount`|参照カウントの変化についてレポートします。|
|`atlTraceWindowing`|Windows の方法でのレポートたとえば、無効なメッセージ マップ ID を報告します。|
|`atlTraceControls`|コントロール上のレポートたとえば、コントロールまたはそのウィンドウが破棄されるときを報告します。|
|`atlTraceHosting`|メッセージをホストしているレポートたとえば、コンテナー内のクライアントがアクティブになるを報告します。|
|`atlTraceDBClient`|OLE DB コンシューマー テンプレート; 上のレポートたとえば、GetData が失敗した呼び出し、出力は、HRESULT を含めることができます。|
|`atlTraceDBProvider`|OLE DB プロバイダー テンプレート; 上のレポートたとえば、列の作成が失敗したかどうかを報告します。|
|`atlTraceSnapin`|MMC スナップイン アプリケーションについてレポートします。|
|`atlTraceNotImpl`|指定された関数が実装されていないことを報告します。|
|`atlTraceAllocation`|デバッグ ツール atldbgmem.h メモリによって出力されるメッセージを報告します。|

### <a name="mfc-trace-flags"></a>MFC のトレース フラグ

|MFC のカテゴリ|説明|
|------------------|-----------------|
|`traceAppMsg`|一般的な目的は、MFC メッセージ。 常にお勧めします。|
|`traceDumpContext`|メッセージ[CDumpContext](../../mfc/reference/cdumpcontext-class.md)します。|
|`traceWinMsg`|MFC のメッセージの処理コードからのメッセージ。|
|`traceMemory`|MFC のメモリ管理のコードからのメッセージ。|
|`traceCmdRouting`|MFC の Windows からのメッセージは、ルーティングのコードをコマンドします。|
|`traceHtml`|MFC の DHTML ダイアログのサポートからのメッセージ。|
|`traceSocket`|MFC のソケットのサポートからのメッセージ。|
|`traceOle`|MFC の OLE サポートからのメッセージ。|
|`traceDatabase`|MFC のデータベースのサポートからのメッセージ。|
|`traceInternet`|MFC のインターネットからのメッセージをサポートします。|

カスタム トレース カテゴリを宣言するには、宣言のグローバル インスタンス、`CTraceCategory`クラスの次のようにします。

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

カテゴリ名、MY_CATEGORY この例を指定する名前、*カテゴリ*パラメーター。 最初のパラメーターは、ATL/MFC トレース ツールに表示されるカテゴリの名前です。 2 番目のパラメーターは、既定のトレース レベルです。 このパラメーターは省略可能で、既定のトレース レベルは 0 です。

ユーザー定義のカテゴリを使用します。

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

トレース メッセージをフィルター処理することを指定するこれらのマクロの定義を挿入する前に Stdafx.h に、`#include <atlbase.h>`ステートメント。

代わりに、プリプロセッサ ディレクティブでフィルターを設定することができます、**プロパティ ページ** ダイアログ ボックス。 をクリックして、**プリプロセッサ** タブで、グローバルに挿入し、**プリプロセッサの定義**編集ボックス。

Atlbase.h には ATLTRACE2 マクロの既定の定義が含まれています、atlbase.h が処理される前に、これらのシンボルを定義しない場合、これらの定義が使用されます。

リリース ビルドで ATLTRACE2 にコンパイルする`(void) 0`します。

ATLTRACE2 では、書式設定後個 1023 文字まで、ダンプ デバイスに送信される文字列の内容を制限します。

ATLTRACE ATLTRACE2 動作と同じ場合、ATLTRACE は旧バージョンとの互換性のために含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[デバッグとエラー報告に関するグローバル関数](../../atl/reference/debugging-and-error-reporting-global-functions.md)
