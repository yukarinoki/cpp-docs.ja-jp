---
title: デバッグと、エラー報告のマクロ |Microsoft ドキュメント
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
ms.openlocfilehash: b99147c9eb9a331d7cc0f9064b858979d00e2804
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365042"
---
# <a name="debugging-and-error-reporting-macros"></a>デバッグと、エラー報告のマクロ
これらのマクロは、デバッグとトレースに役立つ機能を提供します。  
  
|||  
|-|-|  
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|リークを任意のインターフェイスを出力ウィンドウに書き込みますが検出されたときに`_Module.Term`と呼びます。|  
|[_ATL_DEBUG_QI](#_atl_debug_qi)|すべての呼び出しを書き込みます`QueryInterface`出力ウィンドウをします。|  
|[ATLASSERT](#atlassert)|同じ機能を実行、 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロは、C ランタイム ライブラリで見つかりました。|  
|[ATLENSURE](#atlensure)|パラメーターの検証を実行します。 呼び出す`AtlThrow`必要な場合|  
|[ATLTRACENOTIMPL](#atltracenotimpl)|指定された関数は実装されていません、ダンプ デバイスにメッセージを送信します。|  
|[ATLTRACE](#alttrace)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなどの出力デバイスに警告を報告します。 旧バージョンとの互換性のために含まれています。|  
|[ATLTRACE2](#atltrace2)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなどの出力デバイスに警告を報告します。|  
  
##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES  
 ATL ヘッダー ファイルのすべてのトレースをインクルードする前にこのマクロを定義して`AddRef`と**リリース**では、出力ウィンドウに、コンポーネントのインターフェイスを呼び出します。  
  
```
#define _ATL_DEBUG_INTERFACES
```  
  
### <a name="remarks"></a>コメント  
 トレース出力は、次に示すように表示されます。  
  
 `ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`  
  
 各トレースの最初の部分が必ず`ATL: QIThunk`です。 次に、特にを識別する値は、*インターフェイス サンク*使用されています。 インターフェイス サンクは、参照カウントを維持し、ここで使用されるトレース機能を提供するオブジェクトです。 呼び出すたびに新しいインターフェイス サンクが作成された`QueryInterface`に対する要求を除き、 **IUnknown**インターフェイス (この場合、同じサンクが返されますたびに COM の規則に準拠する)。  
  
 次に表示されます`AddRef`または**リリース**呼び出されたメソッドを示すです。 次に、インターフェイスの参照カウントが変更されたオブジェクトを識別する値が表示されます。 トレースされる値は、**この**オブジェクトのポインター。  
  
 トレースされた参照カウントが後にそのサンクの参照カウント`AddRef`または**リリース**が呼び出されました。 この参照カウントがオブジェクトの参照カウントと一致しないことに注意してください。 各サンクは、COM の参照カウントの規則に完全に準拠するための独自の参照カウントを保持します。  
  
 トレースされる情報の最後の部分は、オブジェクトとに影響されるインターフェイスの名前、`AddRef`または**リリース**呼び出します。  
  
 サーバーのシャット ダウン時に検出されたリーク インターフェイスと`_Module.Term`が呼び出されたが次のようにログに記録します。  
  
 `ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`  
  
 ここで以前のトレース ステートメントで提供される情報に直接マップに提供される情報は、インターフェイス サンクの有効期間全体を通じて参照がカウントを調査します。 さらに、そのインターフェイス サンク最大の参照カウントを示す値を取得します。  
  
> [!NOTE]
> `_ATL_DEBUG_INTERFACES` 製品版ビルドで使用できます。  
  
##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI  
 すべての呼び出しを書き込みます`QueryInterface`出力ウィンドウをします。  
  
```
#define _ATL_DEBUG_QI
```  
  
### <a name="remarks"></a>コメント  
 呼び出し`QueryInterface`に失敗しました。 出力ウィンドウに表示されます。  
  
 *インターフェイス名* - `failed`  
  
##  <a name="atlassert"></a>  ATLASSERT  
 `ATLASSERT`マクロと同じ機能を実行する、 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロは、C ランタイム ライブラリで見つかりました。  
  
```
ATLASSERT(booleanExpression);
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 0 以外の値または 0 に評価される式 (ポインターを含む)。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、`ATLASSERT`評価`booleanExpression`し、結果が false の場合は、デバッグ レポートを生成します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldef.h  
    
##  <a name="atlensure"></a>  ATLENSURE  
 このマクロは関数に渡されるパラメーターの検証に使用します。  
  
```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 テストするブール式を指定します。  
  
 `hr`  
 返されるエラー コードを指定します。  
  
### <a name="remarks"></a>コメント  
 これらのマクロは、検出し、正しくないパラメーターの使用方法をユーザーに通知するためのメカニズムを提供します。  
  
 マクロ呼び出し`ATLASSERT`条件には、呼び出しが失敗した場合と`AtlThrow`です。  
  
 **ATLENSURE**場合も、`AtlThrow`は E_FAIL で呼び出されます。  
  
 **ATLENSURE_THROW**場合も、`AtlThrow`は指定した HRESULT で呼び出されます。  
  
 違い**ATLENSURE**と`ATLASSERT`される**ATLENSURE**リリースでは、例外はデバッグ ビルドと同様にも構築がスローされます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  

##  <a name="atltracenotimpl"></a>  ATLTRACENOTIMPL  
 ATL のデバッグ ビルドでは、送信、文字列"`funcname`は実装されていません"ダンプ デバイスを返す**E_NOTIMPL**です。  
  
```
ATLTRACENOTIMPL(funcname);
```  
  
### <a name="parameters"></a>パラメーター  
 `funcname`  
 [in]実装されていない関数の名前を含む文字列。  
  
### <a name="remarks"></a>コメント  
 リリース ビルドでは、単純に返します**E_NOTIMPL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltrace.h 

##  <a name="atltrace"></a>  ATLTRACE
 指定されたフラグとレベルに応じて、デバッガー ウィンドウなどの出力デバイスに警告を報告します。 旧バージョンとの互換性のために含まれています。  
  
```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `exp`  
 [in]文字列と Visual C は、出力ウィンドウまたはこれらのメッセージをトラップするアプリケーションに送信する変数。  
  
 `category`  
 [in]イベントまたはレポートをメソッドの型。 カテゴリの一覧については、「解説」を参照してください。  
  
 `level`  
 [in]レポートへのトレースのレベル。 詳細については、「解説」を参照してください。  
  
 `lpszFormat`  
 [in]ダンプ デバイスに送信する書式指定文字列。  
  
### <a name="remarks"></a>コメント  
 参照してください[ATLTRACE2](#atltrace2)の詳細については**ATLTRACE**です。 **ATLTRACE**と`ATLTRACE2`、同じように動作**ATLTRACE**は旧バージョンとの互換性のために含まれます。  
  
##  <a name="atltrace2"></a>  ATLTRACE2  
 指定されたフラグとレベルに応じて、デバッガー ウィンドウなどの出力デバイスに警告を報告します。  
  
```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `exp`  
 [in]Visual C は、出力ウィンドウまたはこれらのメッセージをトラップするアプリケーションに送信する文字列。  
  
 `category`  
 [in]イベントまたはレポートをメソッドの型。 カテゴリの一覧については、「解説」を参照してください。  
  
 `level`  
 [in]レポートへのトレースのレベル。 詳細については、「解説」を参照してください。  
  
 `lpszFormat`  
 [in]`printf`-ダンプ デバイスに送信する文字列の作成に使用する書式指定文字列のスタイルを設定します。  
  
### <a name="remarks"></a>コメント  
 短縮形の`ATLTRACE2`文字列をデバッガーのウィンドウの出力を書き込みます。 2 番目の形式の`ATLTRACE2`も、デバッガーの出力ウィンドウに出力を書き込みますは ATL/MFC トレース ツールの設定に従います (を参照してください[ATLTraceTool サンプル](../../visual-cpp-samples.md))。 設定する場合など、 `level` 4 および ATL/MFC トレース ツールをレベル 0 の場合は、していないメッセージが表示されます。 *レベル*0、1、2、3、または 4 にすることができます。 既定値は 0 では、最も重大な問題だけを報告します。  
  
 `category`パラメーター リストが、トレース フラグを設定します。 これらのフラグは、レポートに方法の種類に対応します。 次の表は、使用できる有効なトレース フラグを一覧表示、`category`パラメーター。  
  
### <a name="atl-trace-flags"></a>ATL のトレース フラグ  
  
|ATL カテゴリ|説明|  
|------------------|-----------------|  
|`atlTraceGeneral`|ATL のすべてのアプリケーションをレポートします。 これが既定値です。|  
|`atlTraceCOM`|COM メソッドをレポートします。|  
|`atlTraceQI`|QueryInterface 呼び出しをレポートします。|  
|`atlTraceRegistrar`|オブジェクトの登録をレポートします。|  
|`atlTraceRefcount`|参照数の変更をレポートします。|  
|`atlTraceWindowing`|Windows メソッド; 上のレポートたとえば、レポート、無効なメッセージ マップの id。|  
|`atlTraceControls`|コントロールでのレポートたとえば、コントロールまたはそのウィンドウが破棄されるときに報告します。|  
|`atlTraceHosting`|メッセージをホストしているレポートたとえば、コンテナー内のクライアントがアクティブになるときを報告します。|  
|`atlTraceDBClient`|OLE DB コンシューマー テンプレート; 上のレポートたとえば、GetData 失敗した場合、呼び出し時に、出力は、HRESULT を含めることができます。|  
|`atlTraceDBProvider`|OLE DB プロバイダー テンプレート; 上のレポートたとえば、列の作成が失敗したかどうかを報告します。|  
|`atlTraceSnapin`|MMC スナップイン アプリケーションについてレポートします。|  
|`atlTraceNotImpl`|レポートを指定された関数は実装されていません。|  
|**atlTraceAllocation**|Atldbgmem.h のデバッグ ツール、メモリによって出力されるメッセージを報告します。|  
  
### <a name="mfc-trace-flags"></a>MFC のトレース フラグ  
  
|MFC のカテゴリ|説明|  
|------------------|-----------------|  
|**traceAppMsg**|汎用的では、MFC メッセージです。 常にお勧めします。|  
|**traceDumpContext**|メッセージ[CDumpContext](../../mfc/reference/cdumpcontext-class.md)です。|  
|**traceWinMsg**|MFC のメッセージの処理コードからのメッセージ。|  
|**traceMemory**|MFC のメモリ管理コードからのメッセージ。|  
|**traceCmdRouting**|MFC のウィンドウからのメッセージは、ルーティングのコードをコマンドします。|  
|**traceHtml**|MFC の DHTML ダイアログ サポートからのメッセージ。|  
|**traceSocket**|MFC のソケットのサポートからのメッセージ。|  
|**traceOle**|MFC の OLE サポートからのメッセージ。|  
|**traceDatabase**|MFC データベース サポートからのメッセージ。|  
|**traceInternet**|MFC のインターネットからのメッセージをサポートします。|  
  
 カスタム トレース カテゴリを宣言するには、宣言のグローバル インスタンス、`CTraceCategory`クラスの次のようにします。  
  
 [!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]  
  
 カテゴリ名、`MY_CATEGORY`に指定した名前は、この例では、`category`パラメーター。 最初のパラメーターは、ATL/MFC トレース ツールに表示されるカテゴリの名前です。 2 番目のパラメーターは、既定のトレース レベルです。 このパラメーターは省略可能で、既定のトレース レベルは 0 です。  
  
 ユーザー定義のカテゴリを使用します。  
  
 [!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]  
  
 トレース メッセージをフィルター処理することを指定する前に Stdafx.h にこれらのマクロの定義を挿入、`#include <atlbase.h>`ステートメントです。  
  
 代わりに、プリプロセッサ ディレクティブでフィルターを設定することができます、**プロパティ ページ** ダイアログ ボックス。 クリックして、**プリプロセッサ** タブで、グローバルに挿入し、**プリプロセッサの定義**編集ボックス。  
  
 Atlbase.h には既定の定義が含まれています、 `ATLTRACE2` atlbase.h が処理される前に、これらのシンボルを定義しない場合のマクロとこれらの定義が使用されます。  
  
 リリース ビルドで`ATLTRACE2`にコンパイルされる`(void) 0`です。  
  
 `ATLTRACE2` 書式設定後に超える 1023 文字にダンプ デバイスに送信される文字列の内容を制限します。  
  
 **ATLTRACE**と`ATLTRACE2`、同じように動作**ATLTRACE**は旧バージョンとの互換性のために含まれます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [デバッグとエラー報告に関するグローバル関数](../../atl/reference/debugging-and-error-reporting-global-functions.md)
