---
title: コンパイラ オプションに関するマクロ |Microsoft Docs
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
ms.openlocfilehash: 5ec0ebd30f8fc871830e36878446a7cf6b5f875c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879934"
---
# <a name="compiler-options-macros"></a>コンパイラ オプションに関するマクロ
これらのマクロは、特定のコンパイラ機能を制御します。  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|以前のバージョンの ATL から変換されたプロジェクトでのエラーを有効にするシンボル|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|アパートメント スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|によって、`CString`コンス トラクターの明示的な意図しない変換を防止します。|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|C++ 標準準拠の構文、メンバー関数へのポインターを初期化するために非標準の構文を使用する場合、C4867 コンパイラのエラーが発生するを使用するには、このマクロを定義します。|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|無料またはニュートラル スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|プロジェクトを表す記号には、Free または Neutral 両方としてマークされているオブジェクトがあります。 マクロ[_ATL_FREE_THREADED](#_atl_free_threaded)代わりに使用する必要があります。|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|ATL として名前空間を既定で使用できないようにするシンボル|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM に関連するコードがプロジェクトにコンパイルされていることを防止する記号です。|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Vtable ポインターが、クラスのコンス トラクターとデストラクター内で初期化されることを防止する記号です。|  
|[ATL_NOINLINE](#atl_noinline)|関数を示す記号をインライン化することはできません。|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|場合 1 つのスレッド処理モデルを使用して、すべてのオブジェクトを定義します。|  
  
##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS  
 以前のバージョンの ATL から変換されたプロジェクトでのエラーを有効にするシンボル  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Remarks  
 Visual C .NET 2002 では、前に、ATL は、多くの警告を無効になりのままにして、ユーザー コードで表示されないように無効になっています。 具体的には、次のように使用します。  
  
-   C4127 条件式は定数  
  
-   C4786 'identifier': 識別子は 'number' 文字にデバッグ情報で切り詰められました  
  
-   C4201 標準の拡張機能を使用します名前のない構造体/共用体。  
  
-   C4103 'filename': #pragma pack の配置を変更するために使用  
  
-   C4291 'declaration': 一致する演算子が見つかりました削除。初期化が例外をスローすると、メモリは解放されません。  
  
-   C4268 'identifier': 'const' static/global データがコンパイラによって生成された既定のコンス トラクターで初期化オブジェクトをゼロでの入力  
  
-   C4702 到達できないコード  
  
 以前のバージョンから変換されたプロジェクトでこれらの警告は、ライブラリのヘッダーによってまだ無効です。  
  
 次の行を stdafx.h ファイルに追加するとライブラリのヘッダーをインクルードする前に、この動作を変更できます。  
  
 [!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 この場合`#define`追加されると、ATL ヘッダーはグローバルに無効にしないように (または、ユーザーが明示的にそれらを有効にしない個々 の警告を無効にする場合)、これらの警告の状態を保持するために注意してください。  
  
 新しいプロジェクトがあるこの`#define`stdafx.h で、既定で設定します。  
  
##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED  
 アパートメント スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Remarks  
 アパートメント スレッドを指定します。 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)他のオプション、スレッド処理と[オプション、ATL シンプル オブジェクト ウィザード](../../atl/reference/options-atl-simple-object-wizard.md)ATL オブジェクトをモデル化については、スレッド処理します。  
  
##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 によって、`CString`コンス トラクターの明示的な意図しない変換を防止します。  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Remarks  
 これを定義する場合を 1 つのパラメーターを受け取るすべての CString コンス トラクターは、入力引数の暗黙の変換を実行できなくなります。 明示的なキーワードを使用してコンパイルされます。 つまり、_UNICODE が定義されているときに使用しようとすると char * 文字列を CString コンス トラクター引数として、コンパイラ エラーになります。 ナローとワイド文字列型の間の暗黙的な変換を回避する必要がある状況では、このマクロを使用します。  
  
 _T マクロでは、すべてのコンス トラクター文字列引数を使用して _ATL_CSTRING_EXPLICIT_CONSTRUCTORS を定義し、_UNICODE が定義されているかどうかに関係なく、コンパイル エラーを回避できます。  
  
##  <a name="_atl_enable_ptm_warning"></a>  _ATL_ENABLE_PTM_WARNING  
 メンバー関数へのポインターの ANSI C 標準に準拠する構文の使用を強制するには、このマクロを定義します。 このマクロを使用するとすると、メンバー関数へのポインターを初期化するために非標準の構文を使用する場合に生成される C4867 コンパイラのエラーが発生します。  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Remarks  
 Visual C コンパイラの標準的な C++ 準拠の強化を一致するように、ATL と MFC ライブラリが変更されました。 クラスのメンバー関数へのポインターの構文は、ANSI C 標準に従って`&CMyClass::MyFunc`します。  
  
 ときに[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)が定義されていません (既定では、)、ATL と MFC を無効にします (特にメッセージ マップ) マクロ maps C4867 エラー以前のバージョンで作成されたコードが以前と同様にビルドを続行できるようにします。 定義する場合 **_ATL_ENABLE_PTM_WARNING**コードは C++ 標準に準拠する必要があります。  
  
 ただし、非標準のフォームが非推奨とされました、C++ 標準準拠の構文に既存のコードを移動する必要があります。 次: たとえば、  
  
 [!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 を変更する必要があります。  
  
 [!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 '&' 文字を追加するマップ マクロは、追加することする必要がありますいないもう一度、コード内に注意してください。  
  
##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED  
 無料またはニュートラル スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Remarks  
 フリー スレッドを指定します。 フリー スレッドは、マルチ スレッド アパートメント モデルと同じです。 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)他のオプション、スレッド処理と[オプション、ATL シンプル オブジェクト ウィザード](../../atl/reference/options-atl-simple-object-wizard.md)ATL オブジェクトをモデル化については、スレッド処理します。  
  
##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED  
 プロジェクトを表す記号には、Free または Neutral 両方としてマークされているオブジェクトがあります。  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Remarks  
 このシンボルが定義されている場合は、ATL はグローバルなデータへのアクセスを正しく同期するコードを取得します。 新しいコードは同等のマクロを使用する必要があります[_ATL_FREE_THREADED](#_atl_free_threaded)代わりにします。  
  
##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE  
 ATL として名前空間を既定で使用できないようにするシンボル  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Remarks  
 このシンボルが定義されていない場合は実行されます atlbase.h を含む**ATL 名前空間を使用して**既定では、名前の競合をリードする可能性があります。 これを回避するには、このシンボルを定義します。  
  
##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT  
 COM に関連するコードがプロジェクトにコンパイルされていることを防止する記号です。  
  
```
_ATL_NO_COM_SUPPORT
```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 Vtable ポインターが、クラスのコンス トラクターとデストラクター内で初期化されることを防止する記号です。  
  
```
ATL_NO_VTABLE
```  
  
### <a name="remarks"></a>Remarks  
 Vtable ポインターでは、クラスのコンス トラクターとデストラクター内で初期化されることができません、vtable とすべての関数を指す、リンカーは除外できます。 展開すると **__declspec(novtable)** します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 関数を示す記号をインライン化することはできません。  
  
```
    ATL_NOINLINE inline
    myfunction
 {
...
 }
```  
  
### <a name="parameters"></a>パラメーター  
 *myfunction*  
 この関数は、インライン化することはできません。  
  
### <a name="remarks"></a>Remarks  
 ヘッダー ファイルに配置できるようにには、インラインとして宣言する必要がありますが、関数は、コンパイラによってインライン取得しませんを保証する場合は、このシンボルを使用します。 展開すると **__declspec(noinline)** します。  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 場合 1 つのスレッド処理モデルを使用して、すべてのオブジェクトの定義します。  
  
```
_ATL_SINGLE_THREADED
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトが常にプライマリ COM スレッドで実行されることを指定します。 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)他のオプション、スレッド処理と[オプション、ATL シンプル オブジェクト ウィザード](../../atl/reference/options-atl-simple-object-wizard.md)ATL オブジェクトをモデル化については、スレッド処理します。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
