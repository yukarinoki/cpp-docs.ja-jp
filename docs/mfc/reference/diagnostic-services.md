---
title: 診断サービス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2332090032a93152b6c841336538bf9d45984300
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377322"
---
# <a name="diagnostic-services"></a>診断サービス
Microsoft Foundation Class ライブラりは、プログラムのデバッグをより簡単にする多くの診断サービスを提供します。 これらの診断サービスには、プログラムのメモリー割り当てを追跡したり、実行時にオブジェクトの内容をダンプしたり、実行時にデバッグ メッセージを表示したりできるようにするマクロやグローバル関数が含まれます。 診断サービスのマクロとグローバル関数は、次のカテゴリに分類されます。  
  
-   汎用診断マクロ  
  
-   汎用診断関数と変数  
  
-   オブジェクト診断関数  
  
 これらのマクロと関数は、MFC のデバッグ バージョンとリリース バージョンの `CObject` から派生するすべてのクラスで使用できます。 ただし、 `DEBUG_NEW` および **VERIFY** 以外はすべて、リリース バージョンでは何も実行しません。  
  
 デバッグ ライブラリ内の割り当てられるすべてのメモリ ブロックは、一連の "ガード バイト" で囲まれます。 これらのバイトが間違ったメモリ書き込みによって乱される場合、診断ルーチンが問題を報告できます。 行:  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 実装ファイルにすべての呼び出しに**新しい**メモリの割り当てが行われたファイル名と行の数を格納します。 関数 [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) は、この追加情報を表示して、メモリ リークを識別できるようにします。 診断出力の追加情報については、クラス [CDumpContext](../../mfc/reference/cdumpcontext-class.md) も参照してください。  
  
 さらに、C ランタイム ライブラリは、アプリケーションのデバッグに使用できる診断関数のセットもサポートしています。 詳細については、『ランタイム ライブラリ リファレンス』の「 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md) 」を参照してください。  
  
### <a name="mfc-general-diagnostic-macros"></a>MFC 汎用診断マクロ  
  
|||  
|-|-|  
|[ASSERT](#assert)|ライブラリのデバッグ バージョンで、指定された式が **FALSE** に評価された場合、メッセージを出力し、プログラムを中止します。|  
|[ASSERT_KINDOF](#assert_kindof)|オブジェクトが、指定されたクラスのオブジェクト、または指定されたクラスから派生したクラスのオブジェクトであることをテストします。|  
|[ASSERT_VALID](#assert_valid)|その `AssertValid` メンバー関数 (通常は `CObject`からオーバーライドされる) を呼び出すことにより、オブジェクトの内部の有効性をテストします。|
|[DEBUG_NEW](#debug_new)|デバッグ モードのすべてのオブジェクト割り当てにファイル名と行番号を指定します。これは、メモリー リークを見つけるのに役立ちます。|  
|[DEBUG_ONLY](#debug_only)|**ASSERT** に類似していますが、式の値のテストは行いません。デバッグ モードでのみ実行されるコードで役立ちます。|  
|[確認し、ENSURE_VALID](#ensure)|データの正確性の検証に使用します。|
|[THIS_FILE](#this_file)|コンパイルされるファイルの名前に展開されます。|
|[TRACE](#trace)|ライブラリのデバッグ バージョンで `printf`に類似した機能を提供します。|  
|[VERIFY](#verify)|**ASSERT** と類似していますが、ライブラリのリリース バージョンとデバッグ バージョンで式を評価します。|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC 汎用診断関数と変数  
  
|||  
|-|-|  
|[afxDump](#afxdump)|デバッガー出力ウィンドウまたはデバッグ端末に [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 情報を送信するグローバル変数。|  
|[afxMemDF](#afxmemdf)|デバッグ メモリ アロケーターの動作を制御するグローバル変数。|  
|[AfxCheckError](#afxcheckerror)|エラーかどうかを確認するため、そしてもしエラーであれば、適切なエラーをスローするために、渡される **SCODE** のテストに使用するグローバル変数。|  
|[AfxCheckMemory](#afxcheckmemory)|現在割り当てられているすべてのメモリの整合性を確認します。|  
|[AfxDebugBreak](#afxdebugbreak)|実行で区切りが発生します。|
|[AfxDump](#cdumpcontext_in_mfc)|デバッガーにある間に呼び出さると、デバッグ中にオブジェクトの状態をダンプします。|  
|[AfxDump](#afxdump)|デバッグ中に、オブジェクトの状態をダンプする内部関数です。|
|[AfxDumpStack](#afxdumpstack)|現在のスタックのイメージを生成します。 この関数は、常に、静的にリンクされます。|  
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|メモリ リーク ダンプを有効にします。|  
|[AfxEnableMemoryTracking](#afxenablememorytracking)|メモリのトラッキングをオンまたはオフにします。|  
|[AfxIsMemoryBlock](#afxismemoryblock)|メモリ ブロックが正しく割り当てられていることを確認します。|  
|[AfxIsValidAddress](#afxisvalidaddress)|メモリ アドレスの範囲がプログラムの境界内にあることを確認します。|  
|[AfxIsValidString](#afxisvalidstring)|文字列へのポインターが有効かどうかを判断します。|  
|[AfxSetAllocHook](#afxsetallochook)|各メモリ割り振りでの関数の呼び出しを有効にします。|  
  
### <a name="mfc-object-diagnostic-functions"></a>MFC オブジェクト診断関数  
  
|||  
|-|-|  
|[AfxDoForAllClasses](#afxdoforallclasses)|ランタイム型チェックをサポートする `CObject`から派生したすべてのクラスで、指定された関数を実行します。|  
|[AfxDoForAllObjects](#afxdoforallobjects)|`CObject`new **で割り振られたすべての**から派生したオブジェクトで、指定された関数を実行します。|  

### <a name="mfc-compilation-macros"></a>MFC コンパイル マクロ
|||
|-|-|
|[無効](#afx_secure_no_warnings)|使用されなくなった MFC 関数を使用するためのコンパイラの警告を抑制します。|  


## <a name="afx_secure_no_warnings"></a> 無効
使用されなくなった MFC 関数を使用するためのコンパイラの警告を抑制します。  
   
### <a name="syntax"></a>構文   
```  
_AFX_SECURE_NO_WARNINGS  
```     
### <a name="example"></a>例  
 このコード サンプルと無効が定義されていない場合、コンパイラの警告が発生します。  
  
 ```cpp
// define this before including any afx files in stdafx.h
#define _AFX_SECURE_NO_WARNINGS
```
```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a> AfxDebugBreak
中断が発生するには、この関数を呼び出します (への呼び出しの位置に`AfxDebugBreak`)、MFC アプリケーションのデバッグ バージョンの実行にします。  

### <a name="syntax"></a>構文    
```
void AfxDebugBreak( );    
```  
   
### <a name="remarks"></a>コメント  
 `AfxDebugBreak` リリース バージョンの MFC アプリケーションに影響を与えませんし、削除する必要があります。 この関数は、MFC アプリケーションでのみ使用する必要があります。 Win32 API のバージョンを使用して**DebugBreak**、非 MFC アプリケーションで中断が発生します。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxver_.h   

##  <a name="assert"></a>  ASSERT
 その引数を評価します。  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 (ポインター値を含む) または 0 以外に評価される式を指定します。  
  
### <a name="remarks"></a>コメント  
 結果が 0 の場合、マクロは診断メッセージを表示し、プログラムを中止します。 条件が 0 以外の場合は、何も行われません。  
  
 診断メッセージにフォームがあります  
  
 `assertion failed in file <name> in line <num>`  
  
 場所*名*ソース ファイルの名前を指定および*num*ソース ファイル内に失敗したアサーションの行番号です。  
  
 MFC では、リリース バージョンで**ASSERT**式を評価しませんし、そのため、プログラムは中断しません。 環境に関係なく、式を評価する必要がある場合を使用して、**を確認してください**の代わりにマクロ**ASSERT**です。  
  
> [!NOTE]
>  この関数は MFC のデバッグ バージョンでのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="assert_kindof"></a>  ASSERT_KINDOF  
 このマクロは、指されるオブジェクトは、指定したクラスのオブジェクトには、指定したクラスから派生したクラスのオブジェクトをアサートします。  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>パラメーター  
 *classname*  
 名前、 `CObject`-クラスを派生します。  
  
 *pobject*  
 クラスのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 *Pobject*パラメーター オブジェクトへのポインターにする必要がありますでき、 **const**です。 指されるオブジェクトとクラスをサポートする必要があります`CObject`ランタイム クラス情報。 たとえば、ことを確認する`pDocument`のオブジェクトへのポインター、`CMyDoc`クラス、またはその派生クラスのいずれかをコーディングできます。  
  
 [!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 使用して、`ASSERT_KINDOF`マクロは、コーディングと同じでは正確にします。  
  
 [!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 この機能で宣言されたクラスに対してのみ、[DECLARE_DYNAMIC] (実行の時間のオブジェクトのモデルの services.md #declare_dynamic または[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロです。  
  
> [!NOTE]
>  この関数は MFC のデバッグ バージョンでのみ使用できます。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="assert_valid"></a>  ASSERT_VALID  
 オブジェクトの内部状態の有効性に関する仮定をテストに使用します。  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>パラメーター  
 `pObject`  
 派生したクラスのオブジェクトを指定`CObject`のオーバーライドのバージョンを持つ、`AssertValid`メンバー関数。  
  
### <a name="remarks"></a>コメント  
 `ASSERT_VALID` 呼び出し、`AssertValid`オブジェクトのメンバー関数は、その引数として渡されます。  
  
 MFC では、リリース バージョンで`ASSERT_VALID`何も行われません。 デバッグ バージョンでポインターを検証、に対してチェック**NULL**、オブジェクトの独自の呼び出しと`AssertValid`メンバー関数。 これらのテストが失敗した場合と同じ方法で警告メッセージが表示されます。 [ASSERT](#assert)です。  
  
> [!NOTE]
>  この関数は MFC のデバッグ バージョンでのみ使用できます。  
  
 詳細と例については、次を参照してください。 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW  
 メモリ リークの検出を支援します。  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>コメント  
 使用することができます`DEBUG_NEW`通常使用すると、プログラム内にあるすべての**新しい**ヒープ領域を割り当てる演算子。  
  
 デバッグ モードで (ときに、 **_DEBUG**シンボルが定義されている)、`DEBUG_NEW`のメモリを割り当てた各オブジェクトのファイル名と行番号を追跡します。 次に、使用、 [cmemorystate::dumpallobjectssince](cmemorystate-structure.md#dumpallobjectssince)メンバー関数で割り当てられた各オブジェクト`DEBUG_NEW`が割り当てられているファイル名と行の数で表示します。  
  
 使用する`DEBUG_NEW`、ソース ファイルに次のディレクティブを挿入します。  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 このディレクティブを挿入すると、プリプロセッサは挿入`DEBUG_NEW`任意の場所を使用する**新しい**MFC は、残りの部分とします。 プログラムのリリース バージョンをコンパイルするときに`DEBUG_NEW`は単に解決される**新しい**操作、および、ファイル名と行番号の情報は生成されません。  
  
> [!NOTE]
>  配置に必要な (4.1 およびそれ以前) の MFC の以前のバージョンで、`#define`ステートメントと呼ばれるすべてのステートメントの後に、`IMPLEMENT_DYNCREATE`または`IMPLEMENT_SERIAL`マクロです。 これは必要なくなりました。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY  
 デバッグ モードで (ときに、 **_DEBUG**シンボルが定義されている)、`DEBUG_ONLY`引数を評価します。  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>コメント  
 リリース ビルドで**DEBUG_ONLY**の引数は評価されません。 これは、機能は、デバッグ ビルドでのみ実行されるコードがある場合に便利です。  
  
 `DEBUG_ONLY`マクロは、周囲に相当*式*で **#ifdef _DEBUG**と`#endif`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

 ### <a name="ensure"></a>  確認し、ENSURE_VALID
データの正確性の検証に使用します。  
   
### <a name="syntax"></a>構文    
```
ENSURE(  booleanExpression )  
ENSURE_VALID( booleanExpression  )  
```
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 テストするブール式を指定します。  
   
### <a name="remarks"></a>コメント  
 これらのマクロの目的は、パラメーターの検証を向上させるためにです。 マクロにより、コード内の正しくないパラメーターの処理を続行します。 異なり、 **ASSERT** 、マクロ、**を確認してください**マクロにアサーションを生成するだけでなく例外をスローします。  
  
 マクロは、プロジェクトの構成に従って、2 つの方法で動作します。 マクロ呼び出し**ASSERT**アサーションが失敗した場合、例外をスローします。 したがって、次のデバッグ構成のようになります (つまり、 **_DEBUG**が定義されている)、マクロ、アサーションとリリース構成の中に例外を生成、マクロは、例外は、例外を生成 (**ASSERT**しません。リリース構成内の式を評価)。  
  
 マクロ**ENSURE_ARG**のように動作、**を確認してください**マクロです。  
  
 **ENSURE_VALID**呼び出し、`ASSERT_VALID`マクロ (をデバッグ ビルドでのみ、特殊効果を持つ)。 さらに、 **ENSURE_VALID**ポインターが NULL の場合は、例外をスローします。 NULL のテストは、デバッグとリリースの両方の構成で実行されます。  
  
 これらのテストが失敗した場合と同じ方法で警告メッセージが表示されます。 **ASSERT**です。 マクロは、必要な場合は、無効な引数の例外をスローします。  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [確認してください。](#verify)   
 [ATLENSURE](#altensure)

## <a name="this_file"></a> THIS_FILE
コンパイルされるファイルの名前に展開されます。  
   
### <a name="syntax"></a>構文    
```
THIS_FILE    
```  
   
### <a name="remarks"></a>コメント  
 情報を使って、 **ASSERT**と**を確認してください**マクロです。 アプリケーション ウィザードとコードのウィザードでは、作成したソース コード ファイルにマクロを配置します。  
   
### <a name="example"></a>例  
```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the 
// compiler recognizes. 
```
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [アサート](#assert)   
 [VERIFY](#verify)


##  <a name="trace"></a>  TRACE  
 指定した文字列を現在のアプリケーションのデバッガーに送信します。  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>コメント  
 参照してください[ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2)の詳細については**トレース**です。 **トレース**と`ATLTRACE2`同じように動作します。  
  
 MFC のデバッグ バージョンでは、このマクロは、現在のアプリケーションのデバッガーに指定した文字列を送信します。 リリース ビルドでは、このマクロは、(コードが生成されないすべての) nothing にコンパイルします。  
  
 詳細については、次を参照してください。 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)です。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="verify"></a>  VERIFY  
 MFC のデバッグ バージョンでは、その引数を評価します。  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 (ポインター値を含む) または 0 以外に評価される式を指定します。  
  
### <a name="remarks"></a>コメント  
 結果が 0 の場合、マクロは診断メッセージを表示し、プログラムを停止します。 条件が 0 以外の場合は、何も行われません。  
  
 診断メッセージにフォームがあります  
  
 `assertion failed in file <name> in line <num>`  
  
 場所*名前*ソース ファイルの名前を指定と*num*ソース ファイル内に失敗したアサーションの行番号です。  
  
 MFC では、リリース バージョンで**を確認してください**式の評価が印刷またはしません、プログラムを中断します。 たとえば、式が関数呼び出しの場合は、呼び出しになります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  afxDump (MFC の CDumpContext)  
 アプリケーションで、オブジェクト ダンプの基本的な機能を提供します。  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>コメント  
 `afxDump` 定義済み[CDumpContext](../../mfc/reference/cdumpcontext-class.md)を送信できるようにするオブジェクト`CDumpContext`情報デバッガー出力ウィンドウまたはデバッグ端末にします。 通常、指定する必要が`afxDump`へのパラメーターとして`CObject::Dump`です。  
  
 Windows NT とすべてのバージョンの Windows で`afxDump`アプリケーションをデバッグするときに、出力は Visual C のデバッグ出力ウィンドウに送信します。  
  
 この変数は、MFC のデバッグ バージョンでのみ定義されます。 詳細については`afxDump`を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h


## <a name="afxdump"></a> AfxDump (内部)
MFC を使用してデバッグ中に、オブジェクトの状態をダンプする内部関数です。  

### <a name="syntax"></a>構文    
```
void AfxDump(const CObject* pOb);   
```
### <a name="parameters"></a>パラメーター  
 `pOb`  
 派生したクラスのオブジェクトへのポインター`CObject`です。  
   
### <a name="remarks"></a>コメント  
 **AfxDump**オブジェクトの呼び出し`Dump`メンバー関数を指定した場所に情報を送信、`afxDump`変数。 **AfxDump** MFC のデバッグ バージョンでのみ使用できます。  
  
 プログラミング コードで呼び出さないでください。 **AfxDump**、代わりに呼び出す必要がありますが、`Dump`適切なオブジェクトのメンバー関数。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
   
### <a name="see-also"></a>関連項目  
 [CObject::Dump](cobject-class.md#dump)   



##  <a name="afxmemdf"></a>  afxMemDF  
 この変数は、デバッガーや、プログラムからアクセスできる診断の割り当てを調整することができます。  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>コメント  
 `afxMemDF` 列挙体によって指定される次の値を持つことができます`afxMemDF`:  
  
- **allocMemDF**デバッグ アロケーター (デバッグ ライブラリの既定の設定) をオンにします。  
  
- **delayFreeMemDF**メモリの解放を遅らせます。 プログラムがメモリ ブロックを解放中には、アロケーターは、基になるオペレーティング システムにそのメモリを返しません。 これは、プログラムに最大のメモリ負荷を配置します。  
  
- **checkAlwaysMemDF**呼び出し`AfxCheckMemory`たびにメモリを割り当てまたは解放します。 これは、メモリの割り当てと解放が大幅に低下します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError  
 この関数に渡された**SCODE**するかどうかは、エラーを参照してください。  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>コメント  
 エラーがある場合、関数は例外をスローします。 場合、渡された`SCODE`は**E_OUTOFMEMORY**、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)を呼び出して[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)です。 それ以外の場合、関数、 [COleException](../../mfc/reference/coleexception-class.md)を呼び出して[AfxThrowOleException](exception-processing.md#afxthrowoleexception)です。  
  
 この関数は、アプリケーションで OLE 関数への呼び出しの戻り値を確認して使用できます。 アプリケーションでこの関数の戻り値をテストすることによって最小限のコードでエラー状態に対応できます。  
  
> [!NOTE]
>  この関数では、同じ効果をデバッグし、非デバッグ ビルドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory  
 この関数は、空きメモリ プールを検証し、必要に応じてエラー メッセージを出力します。  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>戻り値  
 メモリ エラーがない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数にメモリの破損が検出されない場合は、何も出力します。  
  
 によって割り当てられたものを含め、ヒープに現在割り当てられているすべてのメモリ ブロックがチェックされます**新しい**など、基になるメモリ アロケーターへの直接呼び出しによって割り当てられたものではありませんが、`malloc`関数または**GlobalAlloc** Windows の機能です。 任意のブロックが壊れている可能性がある場合、メッセージは、デバッガーの出力に出力されます。  
  
 行を追加する場合  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 モジュールでは、プログラム、し、後続の呼び出し`AfxCheckMemory`メモリが割り当てられたファイル名と行番号が表示されます。  
  
> [!NOTE]
>  モジュールには、シリアル化可能なクラスの 1 つまたは複数の実装が含まれるかどうかは、配置する必要があります、`#define`後、最後の行`IMPLEMENT_SERIAL`マクロの呼び出しです。  
  
 この関数は、MFC のデバッグ バージョンでのみ動作します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
 
##  <a name="afxdump"></a>  AfxDump (MFC)  
 デバッグ中に、オブジェクトの状態をダンプするデバッガーでこの関数を呼び出します。  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pOb`  
 派生したクラスのオブジェクトへのポインター`CObject`です。  
  
### <a name="remarks"></a>コメント  
 **AfxDump**オブジェクトの呼び出し`Dump`メンバー関数を指定した場所に情報を送信、`afxDump`変数。 **AfxDump** MFC のデバッグ バージョンでのみ使用できます。  
  
 プログラミング コードで呼び出さないでください。 **AfxDump**、代わりに呼び出す必要がありますが、`Dump`適切なオブジェクトのメンバー関数。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  

### <a name="see-also"></a>関連項目  
 [CObject::Dump](cobject-class.md#dump)   


  
##  <a name="afxdumpstack"></a>  AfxDumpStack  
 現在のスタックのイメージを生成する、このグローバル関数を使用できます。  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTarget*  
 ダンプの出力のターゲットを示します。 可能な値は、ビットごとの OR を使用して結合できます ( **&#124;**) 演算子は、次のようにします。  
  
- **AFX_STACK_DUMP_TARGET_TRACE**の出力を送信、[トレース](#trace)マクロです。 **トレース**マクロでは、デバッグ ビルドのみで出力が生成されます。 リリース ビルドの出力生成なし。 また、**トレース**デバッガー以外のターゲットにリダイレクトすることができます。  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT**送信は、既定のターゲットへの出力をダンプします。 デバッグ ビルドの出力に移動、**トレース**マクロです。 リリース ビルドでは、出力は、クリップボードに移動します。  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD**クリップボードのみに出力を送信します。 テキスト形式を使用してとしてクリップボードにデータを配置している、**エディット**クリップボードの形式です。  
  
- **AFX_STACK_DUMP_TARGET_BOTH**出力クリップボードにされ、送信、**トレース**マクロ、同時にします。  
  
- **出力が**Win32 関数を使用して出力をデバッガーに直接送信**OutputDebugString()** です。 このオプションでは、両方のデバッグでデバッガーの出力を生成し、プロセスにデバッガーをアタッチするときに、リリース ビルドします。 **出力が**(アタッチされている場合、デバッガーを常に到達し、リダイレクトすることはできません。  
  
### <a name="remarks"></a>コメント  
 次の例は、呼び出し元から生成された出力の 1 つの行を反映`AfxDumpStack`MFC ダイアログ アプリケーション ボタン ハンドラーから。  
  
 `=== begin AfxDumpStack output ===`  
  
 `00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes`  
  
 `0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes`  
  
 `0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,`  
  
 `unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct AFX_CMDHANDLE`  
  
 `0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes`  
  
 `00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes`  
  
 `00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned`  
  
 `int,long) + 312 bytes`  
  
 `00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned`  
  
 `int,unsigned int,long,long *) + 83 bytes`  
  
 `00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned`  
  
 `int,unsigned int,long) + 46 bytes`  
  
 `004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct`  
  
 `HWND__ *,unsigned int,unsigned int,long) + 237 bytes`  
  
 `00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned`  
  
 `int,unsigned int,long) + 129 bytes`  
  
 `BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes`  
  
 `BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes`  
  
 `=== end AfxDumpStack() output ===`  
  
 上記の出力の各行には、最後の関数呼び出し、関数呼び出しと呼び出された関数プロトタイプを含むモジュールの完全なパス名のアドレスを示します。 関数の指定したアドレスで、スタック上で、関数呼び出しが発生しない場合、バイト単位のオフセットが表示されます。  
  
 たとえば、次の表では、上記の出力の最初の行について説明します。  
  
|出力|説明|  
|------------|-----------------|  
|`00427D55:`|関数の最後の呼び出しの戻りアドレス。|  
|`DUMP2\DEBUG\DUMP2.EXE!`|関数呼び出しを含むモジュールの完全なパス名。|  
|`void AfxDumpStack(unsigned long)`|関数プロトタイプが呼び出されます。|  
|`+ 181 bytes`|関数プロトタイプのアドレスからのバイト オフセット (この場合、 `void AfxDumpStack(unsigned long)`) リターン アドレスを (この場合、 `00427D55`)。|  
  
 `AfxDumpStack` MFC ライブラリのデバッグおよび非デバッグ バージョンで使用できます。ただし、実行可能ファイルの共有 DLL で MFC を使用している場合でもは、関数は静的にリンクされることは常にされます。 共有ライブラリの実装では、関数は mfcs42 します。LIB ライブラリ (とそのバリエーション)。  
  
 正常にこの関数を使用します。  
  
-   IMAGEHLP ファイル。DLL がパスにする必要があります。 この DLL がない、関数により、エラー メッセージが表示されます。 参照してください[イメージ ヘルプ ライブラリ](http://msdn.microsoft.com/library/windows/desktop/ms680321)IMAGEHLP によって提供される関数のセットについてはします。  
  
-   スタックにフレームを持つモジュールは、デバッグ情報を含める必要があります。 デバッグ情報を含んでいない、関数、スタック トレースによって生成されますが、トレースに含まれる小さい情報します。  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump  
 `AFX_DEBUG_STATE` デストラクター内のメモリ リーク ダンプを有効または無効にします。  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDump`  
 `TRUE` はメモリ リーク ダンプが有効なことを示し、`FALSE` はメモリ リーク ダンプが無効なことを示します。  
  
### <a name="return-value"></a>戻り値  
 このフラグの以前の値。  
  
### <a name="remarks"></a>コメント  
 アプリケーションが MFC ライブラリをアンロードしたときに、MFC ライブラリがメモリ リークを確認します。 を介してユーザーに、メモリ リークを報告するこの時点で、**デバッグ**のウィンドウ[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]します。  
  
 アプリケーションが MFC ライブラリの前に別のライブラリを読み込んだ場合、そのライブラリ内の一部のメモリ割り当てが誤ってメモリ リークとして報告されます。 誤ったメモリ リークが原因で、MFC ライブラリがそれらを報告したときに、アプリケーションがゆっくりと終了する可能性があります。 このような場合、 `AfxEnableMemoryLeakDump` を使用してメモリ リーク ダンプを無効にします。  
  
> [!NOTE]
>  この方法を使用してメモリ リーク ダンプをオフにすると、アプリケーションで有効なメモリ リークのレポートを受け取らなくなります。 この方法を使用するのは、メモリ リーク ダンプに誤ったメモリ リークが含まれているという確信がある場合のみにする必要があります。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking  
 通常、診断メモリ追跡は MFC のデバッグ バージョンで有効です。  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>パラメーター  
 *bTrack*  
 この値を設定**TRUE**メモリ追跡; がオン**FALSE**をオフにします。  
  
### <a name="return-value"></a>戻り値  
 追跡を有効にするフラグの以前の設定。  
  
### <a name="remarks"></a>コメント  
 ブロックの割り当ては正しくわかっているコードのセクションでの追跡を無効にするのにには、この関数を使用します。  
  
 詳細については`AfxEnableMemoryTracking`を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)です。  
  
> [!NOTE]
>  この関数は、MFC のデバッグ バージョンでのみ動作します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxismemoryblock"></a>  AfxIsMemoryBlock  
 テストの診断のバージョンによって割り当てられた現在アクティブなメモリ ブロックを表すかどうかを確認するメモリ アドレス**新しい**です。  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 テストするメモリ ブロックへのポインター。  
  
 `nBytes`  
 メモリ ブロックのバイトの長さが含まれています。  
  
 `plRequestNumber`  
 指す、**長い**整数メモリ ブロックの割り当てのシーケンス番号を使用して入力、または現在アクティブなメモリ ブロックを表していない場合は 0 です。  
  
### <a name="return-value"></a>戻り値  
 メモリ ブロックが現在割り当てられているし、長さが正しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 また、元の割り当てられたサイズに対して指定したサイズを確認します。 割り当て順序番号が返される場合は、関数は、0 以外を返します、`plRequestNumber`です。 この番号は、ブロックが他のすべての基準が割り当てられる順序を表す**新しい**割り当てします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxisvalidaddress"></a>  AfxIsValidAddress  
 プログラムのメモリ領域内に完全に収まっていることを確認する任意のメモリ アドレスをテストします。  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 テストするメモリ アドレスへのポインター。  
  
 `nBytes`  
 テストするメモリのバイト数が含まれています。  
  
 *bReadWrite*  
 メモリの読み取りと書き込みの両方であるかどうかを指定します ( **TRUE**) か、または読み込み ( **FALSE**)。  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、指定されたメモリ ブロックの場合は 0 以外に含まれる完全プログラムのメモリ領域です。それ以外の場合 0 を返します。  
  
 非デバッグ ビルドでは、0 以外の値`lp`は NULL。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 アドレスは割り当てられたブロックに制限されません**新しい**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxisvalidstring"></a>  AfxIsValidString  
 この関数を使用して、文字列へのポインターが有効かどうかを判断します。  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 テストへのポインター。  
  
 `nLength`  
 (バイト単位) をテストする文字列の長さを指定します。 値-1 は、null で終わる文字列をすることを示します。  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、指定したサイズの文字列を指定したポインターが指している場合は 0 以外。それ以外の場合 0 を返します。  
  
 非デバッグ ビルドでは、0 以外の値`lpsz`は NULL。 それ以外の場合に 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxsetallochook"></a>  AfxSetAllocHook  
 各メモリ ブロックが割り当てられる前に、指定された関数の呼び出しをできるようにするフックを設定します。  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>パラメーター  
 *pfnAllocHook*  
 呼び出す関数の名前を指定します。 割り当て関数のプロトタイプの「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 割り当てを許可する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリのデバッグ メモリ アロケーターは、メモリの割り当てを監視して、割り当てが許可されているかどうかを制御するユーザーを許可するユーザー定義フック関数を呼び出すことができます。 割り当てフック関数とおりプロトタイプ宣言されています。  
  
 **BOOL AFXAPI AllocHook (size_t** `nSize` **、BOOL** `bObject` **, LONG** `lRequestNumber` **) です。**  
  
 `nSize`  
 提案されたメモリの割り当てのサイズ。  
  
 `bObject`  
 **TRUE**割り当てがある場合、 `CObject`-派生オブジェクト。 それ以外の場合**FALSE**です。  
  
 `lRequestNumber`  
 メモリ割り当てのシーケンス番号。  
  
 なお、 **AFXAPI**呼び出し規約は、呼び出し先がスタックからパラメーターを削除する必要がありますを意味します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses  
 関数を呼び出す、指定されたイテレーションにすべてシリアル化可能な`CObject`-アプリケーションのメモリ領域内のクラスを派生します。  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pfn`  
 各クラスに対して呼び出されるように反復関数へのポインター。 関数の引数がへのポインター、`CRuntimeClass`オブジェクトと呼び出し元が関数に提供する追加のデータへの void ポインターです。  
  
 `pContext`  
 イテレーション関数を呼び出し元が供給できる省略可能なデータへのポインター。 このポインターは、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 シリアル化可能な`CObject`-派生クラスを使用して派生したクラス、`DECLARE_SERIAL`マクロです。 渡されるポインター`AfxDoForAllClasses`で`pContext`が呼び出されるたびに、指定されたイテレーション関数に渡されます。  
  
> [!NOTE]
>  この関数は、MFC のデバッグ バージョンでのみ動作します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects  
 派生したすべてのオブジェクト用に指定されたイテレーション関数を実行`CObject`使って割り当てられた**新しい**です。  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pfn`  
 各オブジェクトに対して実行するイテレーション関数へのポインター。 関数の引数がへのポインター、`CObject`と呼び出し元が関数に提供する追加のデータへの void ポインターです。  
  
 `pContext`  
 イテレーション関数を呼び出し元が供給できる省略可能なデータへのポインター。 このポインターは、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 スタック、グローバル、または埋め込みオブジェクトは列挙されません。 渡されるポインター`AfxDoForAllObjects`で`pContext`が呼び出されるたびに、指定されたイテレーション関数に渡されます。  
  
> [!NOTE]
>  この関数は、MFC のデバッグ バージョンでのみ動作します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)