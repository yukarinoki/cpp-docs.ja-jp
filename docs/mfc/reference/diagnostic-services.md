---
title: 診断サービス
ms.date: 11/04/2016
helpviewer_keywords:
- diagnosi [MFC]s, diagnostic services
- diagnostic macros [MFC], list of general MFC
- services [MFC], diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables [MFC]
- diagnostics [MFC], diagnostic functions and variables
- diagnostics [MFC], list of general MFC
- diagnosis [MFC], diagnostic functions and variables
- diagnosis [MFC], list of general MFC
- general diagnostic macros in MFC
- diagnostic macros [MFC]
- diagnostic services [MFC]
- object diagnostic functions in MFC
- diagnostics [MFC], diagnostic services
- diagnostic functions and variables [MFC]
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
ms.openlocfilehash: 8db12a73d64641a52fea3056de8ab3180c9239b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365796"
---
# <a name="diagnostic-services"></a>診断サービス

Microsoft Foundation Class ライブラりは、プログラムのデバッグをより簡単にする多くの診断サービスを提供します。 これらの診断サービスには、プログラムのメモリー割り当てを追跡したり、実行時にオブジェクトの内容をダンプしたり、実行時にデバッグ メッセージを表示したりできるようにするマクロやグローバル関数が含まれます。 診断サービスのマクロとグローバル関数は、次のカテゴリに分類されます。

- 汎用診断マクロ

- 汎用診断関数と変数

- オブジェクト診断関数

これらのマクロと関数は、MFC のデバッグ バージョンとリリース バージョンの `CObject` から派生するすべてのクラスで使用できます。 ただし、DEBUG_NEWと VERIFY 以外のすべてがリリース バージョンでは何もしません。

デバッグ ライブラリ内の割り当てられるすべてのメモリ ブロックは、一連の "ガード バイト" で囲まれます。 これらのバイトが間違ったメモリ書き込みによって乱される場合、診断ルーチンが問題を報告できます。 行:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

実装ファイルでは **、new**へのすべての呼び出しに、メモリ割り当てが行われたファイル名と行番号が格納されます。 関数[CMemoryState::DumpAllObjectsSince は](cmemorystate-structure.md#dumpallobjectssince)、メモリ リークを識別できるように、この追加情報を表示します。 診断出力の詳細については、クラス[CDumpContext](../../mfc/reference/cdumpcontext-class.md)も参照してください。

さらに、C ランタイム ライブラリは、アプリケーションのデバッグに使用できる診断関数のセットもサポートしています。 詳細については、「ランタイム ライブラリ リファレンス」の[「デバッグ ルーチン](../../c-runtime-library/debug-routines.md)」を参照してください。

### <a name="mfc-general-diagnostic-macros"></a>MFC 汎用診断マクロ

|||
|-|-|
|[アサート](#assert)|ライブラリのデバッグ バージョンで、指定された式が FALSE に評価された場合、メッセージを出力し、プログラムを中止します。|
|[ASSERT_KINDOF](#assert_kindof)|オブジェクトが、指定されたクラスのオブジェクト、または指定されたクラスから派生したクラスのオブジェクトであることをテストします。|
|[ASSERT_VALID](#assert_valid)|その `AssertValid` メンバー関数 (通常は `CObject`からオーバーライドされる) を呼び出すことにより、オブジェクトの内部の有効性をテストします。|
|[Debug_new](#debug_new)|デバッグ モードのすべてのオブジェクト割り当てにファイル名と行番号を指定します。これは、メモリー リークを見つけるのに役立ちます。|
|[DEBUG_ONLY](#debug_only)|ASSERT に類似していますが、式の値のテストは行いません。デバッグ モードでのみ実行されるコードで役立ちます。|
|[保証し、ENSURE_VALID](#ensure)|データの正確性を検証するために使用します。|
|[THIS_FILE](#this_file)|コンパイルされるファイルの名前に展開します。|
|[トレース](#trace)|ライブラリのデバッグ バージョンで `printf`に類似した機能を提供します。|
|[確認](#verify)|ASSERT と類似していますが、ライブラリのリリース バージョンとデバッグ バージョンで式を評価します。|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC 汎用診断関数と変数

|||
|-|-|
|[afxダンプ](#afxdump)|[CDumpContext](../../mfc/reference/cdumpcontext-class.md)情報をデバッガーの出力ウィンドウまたはデバッグ ターミナルに送信するグローバル変数。|
|[アfxミームDF](#afxmemdf)|デバッグ メモリ アロケーターの動作を制御するグローバル変数。|
|[アfx チェック エラー](#afxcheckerror)|エラーかどうかを確認するため、そしてもしエラーであれば、適切なエラーをスローするために、渡される SCODE のテストに使用するグローバル変数。|
|[アfxチェックメモリ](#afxcheckmemory)|現在割り当てられているすべてのメモリの整合性を確認します。|
|[AfxDebugBreak](#afxdebugbreak)|実行の中断を発生させます。|
|[afxDump](#cdumpcontext_in_mfc)|デバッガーにある間に呼び出さると、デバッグ中にオブジェクトの状態をダンプします。|
|[afxDump](#afxdump)|デバッグ中にオブジェクトの状態をダンプする内部関数。|
|[Afxダンプスタック](#afxdumpstack)|現在のスタックのイメージを生成します。 この関数は、常に、静的にリンクされます。|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|メモリ リーク ダンプを有効にします。|
|[AfxEnableメモリトラッキング](#afxenablememorytracking)|メモリのトラッキングをオンまたはオフにします。|
|[をブロックします。](#afxismemoryblock)|メモリ ブロックが正しく割り当てられていることを確認します。|
|[AfxIsValid アドレス](#afxisvalidaddress)|メモリ アドレスの範囲がプログラムの境界内にあることを確認します。|
|[AfxIsValidString](#afxisvalidstring)|文字列へのポインターが有効かどうかを判断します。|
|[AfxSetAllocHook](#afxsetallochook)|各メモリ割り振りでの関数の呼び出しを有効にします。|

### <a name="mfc-object-diagnostic-functions"></a>MFC オブジェクト診断関数

|||
|-|-|
|[AfxDoForAllクラス](#afxdoforallclasses)|ランタイム型チェックをサポートする `CObject`から派生したすべてのクラスで、指定された関数を実行します。|
|[オブジェクト](#afxdoforallobjects)|`CObject`new **で割り振られたすべての**から派生したオブジェクトで、指定された関数を実行します。|

### <a name="mfc-compilation-macros"></a>MFC コンパイル マクロ

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|非推奨の MFC 関数の使用に関するコンパイラ警告を抑制します。|

## <a name="_afx_secure_no_warnings"></a><a name="afx_secure_no_warnings"></a>_AFX_SECURE_NO_WARNINGS

非推奨の MFC 関数の使用に関するコンパイラ警告を抑制します。

### <a name="syntax"></a>構文

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>例

このコード サンプルは、_AFX_SECURE_NO_WARNINGS定義されていない場合、コンパイラ警告を発生させます。

```cpp
// define this before including any afx files in *pch.h* (*stdafx.h* in Visual Studio 2017 and earlier)
#define _AFX_SECURE_NO_WARNINGS
```

```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a><a name="afxdebugbreak"></a>Afx デバッグブレーク

MFC アプリケーションのデバッグ バージョンの実行時に、 に対する`AfxDebugBreak`呼び出しの場所で中断を発生させる場合に、この関数を呼び出します。

### <a name="syntax"></a>構文

```
void AfxDebugBreak( );
```

### <a name="remarks"></a>解説

`AfxDebugBreak`は、MFC アプリケーションのリリース バージョンでは効果がないため、削除する必要があります。 この関数は MFC アプリケーションでのみ使用してください。 Win32 API バージョンを`DebugBreak`使用して、非 MFC アプリケーションで中断を発生させます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxver_.h

## <a name="assert"></a><a name="assert"></a>アサート

引数を評価します。

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
0 以外の値または 0 に評価される式 (ポインター値を含む) を指定します。

### <a name="remarks"></a>解説

結果が 0 の場合、マクロは診断メッセージを出力し、プログラムを中止します。 条件が 0 以外の場合は、何も実行されません。

診断メッセージにフォームがあります

`assertion failed in file <name> in line <num>`

name *name*はソース ファイルの名前で *、num*はソース ファイルで失敗したアサーションの行番号です。

MFC のリリース バージョンでは、ASSERT は式を評価しないため、プログラムを中断しません。 式を環境に関係なく評価する必要がある場合は、ASSERT の代わりに VERIFY マクロを使用します。

> [!NOTE]
> この関数は、MFC のデバッグ バージョンでのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="assert_kindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF

このマクロは、指定したクラスのオブジェクト、または指定したクラスから派生したクラスのオブジェクトであることを示します。

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
派生クラスの`CObject`名前。

*pオブジェクト*<br/>
クラス オブジェクトへのポインター。

### <a name="remarks"></a>解説

*pobject*パラメータはオブジェクトへのポインタである必要があり **、const**を指定できます。 オブジェクトが指し示され、クラスが`CObject`ランタイム クラス情報をサポートしている必要があります。 例として、`pDocument``CMyDoc`クラスのオブジェクトまたはその派生物へのポインタであることを確認するには、次のようにコーディングします。

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

マクロの`ASSERT_KINDOF`使用は、コーディングとまったく同じです。

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

この関数は、DECLARE_DYNAMIC 実行時オブジェクト モデルサービス.md#declare_dynamic マクロまたは[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロで宣言されたクラスに対してのみ機能します。

> [!NOTE]
> この関数は、MFC のデバッグ バージョンでのみ使用できます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="assert_valid"></a><a name="assert_valid"></a>ASSERT_VALID

オブジェクトの内部状態の有効性に関する仮定をテストするために使用します。

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>パラメーター

*pObject*<br/>
オーバーライドするバージョンのメンバー関数を持`CObject`つ派生クラスのオブジェクトを`AssertValid`指定します。

### <a name="remarks"></a>解説

ASSERT_VALID引数`AssertValid`として渡されたオブジェクトのメンバー関数を呼び出します。

MFC のリリース バージョンでは、ASSERT_VALIDは何も実行しません。 デバッグ バージョンでは、ポインターを検証し、NULL をチェックし、オブジェクト自身`AssertValid`のメンバー関数を呼び出します。 これらのテストのいずれかが失敗すると[、ASSERT](#assert)と同じ方法で警告メッセージが表示されます。

> [!NOTE]
> この関数は、MFC のデバッグ バージョンでのみ使用できます。

詳細と例については、「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="debug_new"></a><a name="debug_new"></a>Debug_new

メモリ リークの検出を支援します。

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>解説

通常 **、new**演算子を使用してヒープ記憶域を割り当てる場合は、プログラム内のあらゆる場所でDEBUG_NEWを使用できます。

デバッグモード **(_DEBUG**シンボルが定義されている場合) では、DEBUG_NEWは割り当てる各オブジェクトのファイル名と行番号を追跡します。 次に[、CMemoryState::DumpAllObjectsメンバー](cmemorystate-structure.md#dumpallobjectssince)関数を使用すると、DEBUG_NEWで割り当てられた各オブジェクトが、割り当てられたファイル名と行番号で表示されます。

DEBUG_NEWを使用するには、ソース ファイルに次のディレクティブを挿入します。

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

このディレクティブを挿入すると、プリプロセッサは**新しい**を使用する場所DEBUG_NEWを挿入し、残りの部分は MFC で実行されます。 プログラムのリリースバージョンをコンパイルすると、DEBUG_NEW単純な**新規**操作に解決され、ファイル名と行番号情報は生成されません。

> [!NOTE]
> 以前のバージョンの MFC (4.1 以前) では、IMPLEMENT_DYNCREATE マクロまたはIMPLEMENT_SERIAL マクロを`#define`呼び出したすべてのステートメントの後にステートメントを記述する必要があります。 これはもう不要です。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="debug_only"></a><a name="debug_only"></a>DEBUG_ONLY

デバッグ モード **(_DEBUG**シンボルが定義されている場合) では、DEBUG_ONLY引数を評価します。

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>解説

リリース ビルドでは、DEBUG_ONLY引数は評価されません。 これは、デバッグ ビルドでのみ実行する必要があるコードがある場合に便利です。

DEBUG_ONLY マクロは、 と`#endif`を`#ifdef _DEBUG`使用して周囲の*式*と同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

### <a name="ensure-and-ensure_valid"></a><a name="ensure"></a>保証し、ENSURE_VALID

データの正確性を検証するために使用します。

### <a name="syntax"></a>構文

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
テストするブール式を指定します。

### <a name="remarks"></a>解説

これらのマクロの目的は、パラメーターの検証を改善することです。 マクロは、コード内の間違ったパラメータの処理を防ぎます。 ASSERT マクロとは異なり、ASSERT マクロはアサーションの生成に加えて例外をスローします。

プロジェクトの構成に従って、マクロは 2 つの方法で動作します。 マクロは ASSERT を呼び出し、アサーションが失敗した場合に例外をスローします。 したがって、デバッグ構成 (つまり、_DEBUGが定義されている場合) では、マクロは、リリース構成では、例外を生成する (ASSERT は、リリース構成では式を評価しません) 例外を生成します。

マクロENSURE_ARGは、ENSURE マクロと同じように動作します。

ENSURE_VALIDは、ASSERT_VALID マクロを呼び出します (デバッグ ビルドでのみ有効です)。 さらに、ポインターが NULL の場合は例外をスローENSURE_VALID。 NULL テストは、デバッグ構成とリリース構成の両方で実行されます。

これらのテストのいずれかが失敗した場合、ASSERT と同じ方法で警告メッセージが表示されます。 マクロは、必要に応じて無効な引数例外をスローします。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="this_file"></a><a name="this_file"></a>THIS_FILE

コンパイルされるファイルの名前に展開します。

### <a name="syntax"></a>構文

```
THIS_FILE
```

### <a name="remarks"></a>解説

この情報は、アサートおよび VERIFY マクロによって使用されます。 アプリケーション ウィザードとコード ウィザードは、作成するソース コード ファイルにマクロを配置します。

### <a name="example"></a>例

```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the
// compiler recognizes.
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="trace"></a><a name="trace"></a>トレース

指定した文字列を現在のアプリケーションのデバッガーに送信します。

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>解説

トレースの説明については[、ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2)を参照してください。 トレースと ATLTRACE2 の動作は同じです。

MFC のデバッグ バージョンでは、このマクロは、指定された文字列を現在のアプリケーションのデバッガーに送信します。 リリース ビルドでは、このマクロはコンパイルされません (コードはまったく生成されません)。

詳細については、「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="verify"></a><a name="verify"></a>確認

MFC のデバッグ バージョンでは、その引数を評価します。

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
0 以外の値または 0 に評価される式 (ポインター値を含む) を指定します。

### <a name="remarks"></a>解説

結果が 0 の場合、マクロは診断メッセージを出力し、プログラムを停止します。 条件が 0 以外の場合は、何も実行されません。

診断メッセージにフォームがあります

`assertion failed in file <name> in line <num>`

name *name*はソース ファイルの名前で *、num*はソース ファイルで失敗したアサーションの行番号です。

MFC のリリース バージョンでは、VERIFY は式を評価しますが、プログラムを印刷または中断しません。 たとえば、式が関数呼び出しの場合、呼び出しが行われます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc"></a>afx ダンプ (MFC のコンテキストのコンテキスト)

アプリケーションで基本的なオブジェクト ダンプ機能を提供します。

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>解説

`afxDump`は、デバッガ出力ウィンドウまたはデバッグターミナルに情報を送信`CDumpContext`できる、定義済みの[CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクトです。 通常は、`afxDump`にパラメーターとして指定`CObject::Dump`します。

Windows NT およびすべてのバージョンの`afxDump`Windows では、アプリケーションをデバッグするときに、出力が Visual C++ の出力デバッグ ウィンドウに送信されます。

この変数は、MFC のデバッグ バージョンでのみ定義されます。 の詳細については、「 `afxDump` [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxdump-internal"></a><a name="afxdump"></a>AfxDump (内部)

デバッグ中に MFC がオブジェクトの状態をダンプするために使用する内部関数。

### <a name="syntax"></a>構文

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*Pob*<br/>
から`CObject`派生したクラスのオブジェクトへのポインター。

### <a name="remarks"></a>解説

`AfxDump`オブジェクトの`Dump`メンバー関数を呼び出し、変数で指定された場所に情報`afxDump`を送信します。 `AfxDump`は、MFC のデバッグ バージョンでのみ使用できます。

プログラム コードは 呼`AfxDump`び出すのではなく、適切な`Dump`オブジェクトのメンバー関数を呼び出す必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxmemdf"></a><a name="afxmemdf"></a>アfxミームDF

この変数はデバッガーまたはプログラムからアクセスでき、割り当ての診断を調整できます。

```
int  afxMemDF;
```

### <a name="remarks"></a>解説

`afxMemDF`列挙型`afxMemDF`で指定されたとおりに、次の値を指定できます。

- `allocMemDF`アロケーターのデバッグをオンにします (デバッグ ライブラリの既定の設定)。

- `delayFreeMemDF`メモリの解放を遅らせます。 プログラムがメモリ ブロックを解放する間、アロケーターは、基になるオペレーティング システムにそのメモリを返しません。 これにより、プログラムに最大のメモリ負荷が発生します。

- `checkAlwaysMemDF`メモリ`AfxCheckMemory`が割り当てられるか解放されるたびに呼び出されます。 これにより、メモリの割り当てと割り当て解除が大幅に遅くなります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxcheckerror"></a><a name="afxcheckerror"></a>アfx チェック エラー

この関数は、渡された SCODE をテストして、それがエラーかどうかを調べます。

```
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>解説

エラーの場合、関数は例外をスローします。 渡された SCODE がE_OUTOFMEMORY場合、関数は[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)を呼び出すことによって[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)をスローします。 それ以外の場合、関数は[AfxThrowOleException](exception-processing.md#afxthrowoleexception)を呼び出すことによって[COleException](../../mfc/reference/coleexception-class.md)をスローします。

この関数を使用して、アプリケーション内の OLE 関数の呼び出しの戻り値をチェックできます。 アプリケーションでこの関数を使用して戻り値をテストすることで、最小限のコードでエラー状態に適切に対応できます。

> [!NOTE]
> この関数は、デバッグ ビルドと非デバッグ ビルドで同じ効果を持ちます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxcheckmemory"></a><a name="afxcheckmemory"></a>アfxチェックメモリ

この関数は、空きメモリ プールを検証し、必要に応じてエラー メッセージを出力します。

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>戻り値

メモリ エラーがない場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

関数がメモリ破損を検出しなかった場合は、何も出力しません。

malloc 関数や Windows 関数など、基になるメモリ アロケーターへの直接呼び出しによって割り当てられたメモリ ブロックは、**新しい**メモリ**malloc**によって割り当てられた`GlobalAlloc`ものも含め、ヒープに現在割り当てられているすべてのメモリ ブロックがチェックされます。 ブロックが破損していることが判明した場合、デバッガ出力にメッセージが出力されます。

行を含める場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

プログラムモジュールで、次にメモリが割`AfxCheckMemory`り当てられたファイル名と行番号を表示する後続の呼び出し。

> [!NOTE]
> モジュールにシリアル化可能なクラスの実装が 1 つ以上含まれている場合は`#define`、最後のIMPLEMENT_SERIAL マクロ呼び出しの後に行を置く必要があります。

この関数は、MFC のデバッグ バージョンでのみ動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxdump-mfc"></a><a name="afxdump"></a>アfxダンプ (MFC)

デバッグ中にオブジェクトの状態をダンプするには、デバッガーでこの関数を呼び出します。

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*Pob*<br/>
から`CObject`派生したクラスのオブジェクトへのポインター。

### <a name="remarks"></a>解説

`AfxDump`オブジェクトの`Dump`メンバー関数を呼び出し、変数で指定された場所に情報`afxDump`を送信します。 `AfxDump`は、MFC のデバッグ バージョンでのみ使用できます。

プログラム コードは 呼`AfxDump`び出すのではなく、適切な`Dump`オブジェクトのメンバー関数を呼び出す必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxdumpstack"></a><a name="afxdumpstack"></a>Afxダンプスタック

このグローバル関数を使用して、現在のスタックのイメージを生成できます。

```
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>パラメーター

*dwターゲット*<br/>
ダンプ出力のターゲットを示します。 ビットごとの OR ( **&#124;**) 演算子を使用して組み合わせることができる値は、次のとおりです。

- AFX_STACK_DUMP_TARGET_TRACE [TRACE](#trace)マクロを使用して出力を送信します。 TRACE マクロは、デバッグ ビルドでのみ出力を生成します。リリース ビルドでは出力は生成されません。 また、TRACE は、デバッガー以外の他のターゲットにリダイレクトできます。

- AFX_STACK_DUMP_TARGET_DEFAULT ダンプ出力をデフォルトターゲットに送信します。 デバッグ ビルドの場合、出力は TRACE マクロに送られます。 リリース ビルドでは、出力はクリップボードに送られます。

- AFX_STACK_DUMP_TARGET_CLIPBOARD 出力をクリップボードにのみ送信します。 データは、クリップボード形式を使用してプレーンテキストとしてクリップボードに配置CF_TEXT。

- AFX_STACK_DUMP_TARGET_BOTH出力をクリップボードと TRACE マクロに同時に送信します。

- AFX_STACK_DUMP_TARGET_ODS Win32 関数`OutputDebugString()`を使用して、デバッガーに直接出力を送信します。 このオプションは、デバッガーがプロセスにアタッチされている場合、デバッグ ビルドとリリース ビルドの両方でデバッガー出力を生成します。 AFX_STACK_DUMP_TARGET_ODSは常にデバッガに到達し (アタッチされている場合)、リダイレクトできません。

### <a name="remarks"></a>解説

次の例は、MFC ダイアログ アプリケーションのボタン ハンドラー`AfxDumpStack`からの呼び出しによって生成される出力の 1 行を表します。

```Output
=== begin AfxDumpStack output ===
00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes
0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes
0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,
unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct
AFX_CMDHANDLE
0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes
00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes
00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned
int,long) + 312 bytes
00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned
int,unsigned int,long,long *) + 83 bytes
00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned
int,unsigned int,long) + 46 bytes
004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct
HWND__ *,unsigned int,unsigned int,long) + 237 bytes
00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned
int,unsigned int,long) + 129 bytes
BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes
BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes
=== end AfxDumpStack() output ===
```

上記の出力の各行は、最後の関数呼び出しのアドレス、関数呼び出しを含むモジュールのフルパス名、および呼び出された関数プロトタイプを示します。 スタック上の関数呼び出しが関数の正確なアドレスで行われない場合は、バイトのオフセットが表示されます。

たとえば、次の表は、上記の出力の最初の行を説明します。

|出力|説明|
|------------|-----------------|
|`00427D55:`|最後の関数呼び出しの戻りアドレス。|
|`DUMP2\DEBUG\DUMP2.EXE!`|関数呼び出しを含むモジュールの完全パス名。|
|`void AfxDumpStack(unsigned long)`|関数プロトタイプが呼び出されました。|
|`+ 181 bytes`|関数プロトタイプのアドレス (この場合は)`void AfxDumpStack(unsigned long)`から戻りアドレス (この場合は`00427D55`) までのオフセット (バイト単位)。|

`AfxDumpStack`MFC ライブラリのデバッグ バージョンとデバッグバージョン以外で使用できます。ただし、実行可能ファイルが共有 DLL で MFC を使用している場合でも、関数は常に静的にリンクされます。 共有ライブラリの実装では、関数は MFCS42 にあります。LIB ライブラリ (およびそのバリアント)。

この関数を正常に使用するには、次の手順を実行します。

- ファイルのイメージHLP。DLL はパス上になければなりません。 この DLL がない場合は、エラー メッセージが表示されます。 IMAGEHLP が提供する関数セットについては、[イメージヘルプライブラリ](/windows/win32/Debug/image-help-library)を参照してください。

- スタック上にフレームがあるモジュールには、デバッグ情報が含まれている必要があります。 デバッグ情報が含まれていない場合、関数はスタック トレースを生成しますが、トレースの詳細は少なくなります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>を有効にするメモリ リークダンプ

AFX_DEBUG_STATEデストラクタのメモリ リーク ダンプを有効または無効にします。

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>パラメーター

*bダンプ*<br/>
[in]TRUE は、メモリ リーク ダンプが有効であることを示します。FALSE は、メモリ リーク ダンプが無効であることを示します。

### <a name="return-value"></a>戻り値

このフラグの以前の値。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリをアンロードしたときに、MFC ライブラリがメモリ リークを確認します。 この時点で、メモリ リークは、Visual Studio の**デバッグ**ウィンドウを通じてユーザーに報告されます。

アプリケーションが MFC ライブラリの前に別のライブラリを読み込んだ場合、そのライブラリ内の一部のメモリ割り当てが誤ってメモリ リークとして報告されます。 誤ったメモリ リークが原因で、MFC ライブラリがそれらを報告したときに、アプリケーションがゆっくりと終了する可能性があります。 このような場合、 `AfxEnableMemoryLeakDump` を使用してメモリ リーク ダンプを無効にします。

> [!NOTE]
> この方法を使用してメモリ リーク ダンプをオフにすると、アプリケーションで有効なメモリ リークのレポートを受け取らなくなります。 この方法を使用するのは、メモリ リーク ダンプに誤ったメモリ リークが含まれているという確信がある場合のみにする必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnableメモリトラッキング

診断メモリの追跡は、通常、MFC のデバッグ バージョンで有効にします。

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>パラメーター

*bトラック*<br/>
この値を TRUE に設定すると、メモリの追跡が有効になります。FALSE はそれをオフにします。

### <a name="return-value"></a>戻り値

追跡有効化フラグの以前の設定。

### <a name="remarks"></a>解説

この関数を使用して、ブロックを正しく割り当てていることがわかっているコードのセクションの追跡を無効にします。

の詳細については、「 `AfxEnableMemoryTracking` [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

> [!NOTE]
> この関数は、MFC のデバッグ バージョンでのみ動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxismemoryblock"></a><a name="afxismemoryblock"></a>をブロックします。

メモリ アドレスをテストして、診断バージョンの**new**によって割り当てられた現在アクティブなメモリ ブロックを表していることを確認します。

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>パラメーター

*P*<br/>
テストするメモリ ブロックへのポイント。

*Nbytes*<br/>
メモリ ブロックの長さ (バイト単位) を格納します。

*要求番号*<br/>
メモリ ブロックの割り当てシーケンス番号で埋め込まれる**長整数**を指します。

### <a name="return-value"></a>戻り値

メモリ ブロックが現在割り当てられており、長さが正しい場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

また、指定されたサイズを、元の割り当てサイズと照合します。 関数が 0 以外を返す場合、割り当てシーケンス番号は*plRequestNumber*に返されます。 この番号は、ブロックが他のすべての**新しい**割り当てに対して割り当てられた順序を表します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxisvalidaddress"></a><a name="afxisvalidaddress"></a>AfxIsValid アドレス

メモリ アドレスをテストして、メモリ アドレスがプログラムのメモリ空間に完全に含まれていることを確認します。

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>パラメーター

*Lp*<br/>
テストするメモリ アドレスへのポイント。

*Nbytes*<br/>
テストするメモリのバイト数を格納します。

*書き込み*<br/>
メモリが読み取りと書き込みの両方 (TRUE) か、単なる読み取り (FALSE) かどうかを指定します。

### <a name="return-value"></a>戻り値

デバッグ ビルドで、指定されたメモリ ブロックがプログラムのメモリ空間内に完全に含まれている場合は 0 以外の値を返します。それ以外の場合は 0。

非デバッグ ビルドでは *、lp*が NULL でない場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

アドレスは new**によって割**り当てられたブロックに限定されません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxisvalidstring"></a><a name="afxisvalidstring"></a>文字列

この関数を使用して、文字列へのポインターが有効かどうかを判断します。

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
テストするポインター。

*nレングス*<br/>
テストする文字列の長さをバイト単位で指定します。 値 -1 は、文字列が NULL で終了することを示します。

### <a name="return-value"></a>戻り値

デバッグ ビルドで、指定されたポインターが指定されたサイズの文字列を指している場合は 0 以外。それ以外の場合は 0。

非デバッグ ビルドでは *、lpsz*が NULL でない場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxsetallochook"></a><a name="afxsetallochook"></a>アフセタオロックフック

各メモリ ブロックが割り当てられる前に、指定した関数の呼び出しを有効にするフックを設定します。

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>パラメーター

*プンラロックフック*<br/>
呼び出す関数の名前を指定します。 割り当て関数のプロトタイプについては、「解説」を参照してください。

### <a name="return-value"></a>戻り値

割り当てを許可する場合は 0 以外を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

Microsoft Foundation クラス ライブラリ デバッグ メモリ アロケーターは、ユーザー定義のフック関数を呼び出して、ユーザーがメモリ割り当てを監視したり、割り当てが許可されているかどうかを制御したりできます。 割り当てフック関数は、次のようにプロトタイプ化されます。

**ブールAFXAPIアロックフック(size_t、**`nSize`**ブール**`bObject`**、ロング**`lRequestNumber`**);**

*Nsize*<br/>
提案されたメモリ割り当てのサイズ。

*bオブジェクト*<br/>
派生オブジェクトの割り当て`CObject`である場合は TRUE。それ以外の場合は FALSE。

*要求番号*<br/>
メモリ割り当てのシーケンス番号。

AFXAPI 呼び出し規約は、呼び出し先がスタックからパラメーターを削除する必要があることを意味します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxDoForAllクラス

アプリケーションのメモリ空間にあるすべてのシリアル化可能`CObject`な派生クラスの指定された反復関数を呼び出します。

```
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>パラメーター

*Pfn*<br/>
各クラスに対して呼び出される反復関数へのポイント。 関数の引数は、`CRuntimeClass`オブジェクトへのポインターと、呼び出し元が関数に提供する余分なデータへの void ポインターです。

*pContext*<br/>
呼び出し元が反復関数に提供できる省略可能なデータへのポイント。 このポインターは NULL にできます。

### <a name="remarks"></a>解説

シリアル化`CObject`可能な派生クラスは、DECLARE_SERIAL マクロを使用して派生したクラスです。 `AfxDoForAllClasses` *pContext*で渡されるポインターは、呼び出されるたびに指定された反復関数に渡されます。

> [!NOTE]
> この関数は、MFC のデバッグ バージョンでのみ動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="afxdoforallobjects"></a><a name="afxdoforallobjects"></a>オブジェクト

`CObject` **new**で割り当てられたオブジェクトから派生したすべてのオブジェクトに対して、指定された反復関数を実行します。

```
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>パラメーター

*Pfn*<br/>
各オブジェクトに対して実行する反復関数へのポイント。 関数の引数は、呼び出`CObject`し元が関数に提供する追加データへのポインターと void ポインターです。

*pContext*<br/>
呼び出し元が反復関数に提供できる省略可能なデータへのポイント。 このポインターは NULL にできます。

### <a name="remarks"></a>解説

スタック、グローバル、または埋め込みオブジェクトは列挙されません。 *pContext*で`AfxDoForAllObjects`渡されるポインターは、呼び出されるたびに指定された反復関数に渡されます。

> [!NOTE]
> この関数は、MFC のデバッグ バージョンでのみ動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[オブジェクト::Dウンプ](cobject-class.md#dump)
