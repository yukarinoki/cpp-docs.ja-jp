---
title: コンパイラ オプションに関するマクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- _ATL_ALL_WARNINGS
- _ATL_APARTMENT_THREADED
- '_ATL_CSTRING_EXPLICIT_CONSTRUCTORS '
- _ATL_ENABLE_PTM_WARNING
- _ATL_FREE_THREADED
- _ATL_MULTI_THREADED
- _ATL_NO_AUTOMATIC_NAMESPACE
- _ATL_NO_COM_SUPPORT
- ATL_NO_VTABLE
- ATL_NOINLINE
- _ATL_SINGLE_THREADED
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e84c92e8bbf65ff3b8b54111bcce2306628edb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365854"
---
# <a name="compiler-options-macros"></a>コンパイラ オプション マクロ
これらのマクロは、特定のコンパイラ機能を制御します。  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|エラー ATL の以前のバージョンから変換されたプロジェクトで有効にするシンボル|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|アパートメント スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|によって、`CString`コンス トラクターの明示的な意図しない変換を回避します。|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|C++ 標準準拠の構文、メンバー関数へのポインターを初期化するために非標準の構文を使用する場合、C4867 コンパイラ エラーが発生するを使用するために、このマクロを定義します。|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|1 つまたは複数のオブジェクトの free またはニュートラル スレッドを使用する場合を定義します。|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|プロジェクトを表す記号は、Free または Neutral 両方としてマークされているオブジェクトがあります。 マクロ[_ATL_FREE_THREADED](#_atl_free_threaded)代わりに使用する必要があります。|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|ATL として名前空間を既定で使用できないようにするシンボル|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|これが COM に関連するコードがプロジェクトにコンパイルされていることを防止記号です。|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Vtable ポインターが、クラスのコンス トラクターおよびデストラクター内で初期化されることを防止する記号です。|  
|[ATL_NOINLINE](#atl_noinline)|関数を示す記号をインライン展開することはできません。|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|場合は 1 つのスレッド モデルを使用してすべてのオブジェクトを定義します。|  
  
##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS  
 エラー ATL の以前のバージョンから変換されたプロジェクトで有効にするシンボル  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>コメント  
 Visual C .NET 2002 では、前に、ATL は、多くの警告を無効になりのままにしてユーザー コードで表示されないように無効になっています。 具体的には、次のように使用します。  
  
-   C4127 条件式は定数  
  
-   C4786 'identifier': 識別子は 'number' 文字にデバッグ情報で切り詰められました  
  
-   C4201 標準の拡張機能を使用: 無名構造体/共用体  
  
-   C4103 'filename': #pragma pack の配置を変更するために使用  
  
-   C4291 'declaration': 対応する delete 演算子が見つかりませんでした。初期化は、例外をスローすると、メモリは解放されません。  
  
-   C4268 'identifier': コンパイラによって生成された既定のコンス トラクターで初期化 'const' static/global データ オブジェクトをゼロでの入力  
  
-   C4702 到達不可能なコード  
  
 以前のバージョンから変換されたプロジェクトでこれらの警告が無効のままライブラリ ヘッダーによってです。  
  
 次の行にファイルを追加、stdafx.h ライブラリ ヘッダーをインクルードする前に、この動作を変更できます。  
  
 [!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 この場合`#define`追加されると、ATL ヘッダーは、無効化されていないグローバルように (または、ユーザーが明示的にそれらを有効にしない個々 の警告を無効にする場合) は、これらの警告の状態を保持するように注意してください。  
  
 新しいプロジェクトがあるこの`#define`stdafx.h で既定で設定します。  
  
##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED  
 アパートメント スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>コメント  
 アパートメント スレッドを指定します。 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)他のスレッド オプション、および[オプション、ATL シンプル オブジェクト ウィザード](../../atl/reference/options-atl-simple-object-wizard.md)ATL オブジェクトをモデル化、スレッド処理の詳細についてはします。  
  
##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 によって、`CString`コンス トラクターの明示的な意図しない変換を回避します。  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>コメント  
 これを定義するときを 1 つのパラメーターを受け取るすべての CString コンス トラクターは、明示的なキーワードを入力引数の暗黙の変換が原因でコンパイルされます。 つまり、この例では、_UNICODE が定義されているときに使用しようとすると、char * 文字列を CString コンス トラクター引数として、コンパイラ エラーが発生します。 ナローとワイド文字列型の間の暗黙的な変換を回避する必要がある場合に、このマクロを使用します。  
  
 _T マクロを使用するとすべてのコンス トラクター文字列引数に対して、_ATL_CSTRING_EXPLICIT_CONSTRUCTORS を定義し、_UNICODE が定義されているかどうかに関係なく、コンパイル エラーを回避できます。  
  
##  <a name="_atl_enable_ptm_warning"></a>  _ATL_ENABLE_PTM_WARNING  
 メンバー関数へのポインターの ANSI C 標準に準拠する構文の使用を強制するために、このマクロを定義します。 このマクロを使用すると、メンバー関数へのポインターを初期化するために非標準の構文を使用する場合に生成される C4867 のコンパイラ エラーが発生します。  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>コメント  
 ATL および MFC ライブラリは、Visual C コンパイラの標準的な C++ 準拠の強化を一致するように変更されています。 クラスのメンバー関数へのポインターの構文をする必要があります、ANSI C 標準に従って`&CMyClass::MyFunc`です。  
  
 ときに[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)が定義されていません (既定の場合)、ATL と MFC を無効に (特にメッセージ マップ) マクロ マップで C4867 エラーは以前のバージョンで作成したコードが以前と同様にビルドを継続できるようにします。 定義した場合 **_ATL_ENABLE_PTM_WARNING**コードは C++ 標準に準拠する必要があります。  
  
 ただし、非標準のフォームは廃止されました、C++ 標準に準拠構文に既存のコードを移動する必要があります。 次: たとえば、  
  
 [!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 を変更する必要があります。  
  
 [!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 '&' 文字を追加するマップ マクロでは、追加することする必要がありますいないもう一度、コード内に注意してください。  
  
##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED  
 1 つまたは複数のオブジェクトの free またはニュートラル スレッドを使用する場合を定義します。  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>コメント  
 フリー スレッドを指定します。 フリー スレッドは、マルチ スレッド アパートメント モデルと同じです。 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)他のスレッド オプション、および[オプション、ATL シンプル オブジェクト ウィザード](../../atl/reference/options-atl-simple-object-wizard.md)ATL オブジェクトをモデル化、スレッド処理の詳細についてはします。  
  
##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED  
 プロジェクトを表す記号は、Free または Neutral 両方としてマークされているオブジェクトがあります。  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>コメント  
 このシンボルが定義されている場合は、ATL は正しくグローバル データへのアクセスを同期するコードを取得します。 新しいコードは同等のマクロを使用する必要があります[_ATL_FREE_THREADED](#_atl_free_threaded)代わりにします。  
  
##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE  
 ATL として名前空間を既定で使用できないようにするシンボル  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>コメント  
 このシンボルが定義されていない場合は実行されます atlbase.h を含む**ATL の名前空間を使用して**既定では、名前付けの競合を発生することがあります。 これを回避するには、このシンボルを定義します。  
  
##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT  
 これが COM に関連するコードがプロジェクトにコンパイルされていることを防止記号です。  
  
```
_ATL_NO_COM_SUPPORT```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 A symbol that prevents the vtable pointer from being initialized in the class's constructor and destructor.  
  
```
ATL_NO_VTABLE
```  
  
### Remarks  
 If the vtable pointer is prevented from being initialized in the class's constructor and destructor, the linker can eliminate the vtable and all of the functions to which it points. Expands to **__declspec(novtable)**.  
  
### Example  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 A symbol that indicates a function should not be inlined.  
  
```
    ATL_NOINLINE inline
    myfunction
 { ... }
```  
  
### Parameters  
 *myfunction*  
 The function that should not be inlined.  
  
### Remarks  
 Use this symbol if you want to ensure a function does not get inlined by the compiler, even though it must be declared as inline so that it can be placed in a header file. Expands to **__declspec(noinline)**.  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 Define if all of your objects use the single threading model  
  
```
_ATL_SINGLE_THREADED
```  
  
### Remarks  
 Specifies that the object always runs in the primary COM thread. See [Specifying the Project's Threading Model](../../atl/specifying-the-threading-model-for-a-project-atl.md) for other threading options, and [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) for a description of the threading models available for an ATL object.  
  
## See Also  
 [Macros](../../atl/reference/atl-macros.md)
