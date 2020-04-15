---
title: コンパイラ オプション マクロ
ms.date: 08/19/2019
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
ms.openlocfilehash: 702324c3300ff23bb60113529a681e3b8fa99354
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331618"
---
# <a name="compiler-options-macros"></a>コンパイラ オプション マクロ

これらのマクロは、特定のコンパイラ機能を制御します。

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|ATL の以前のバージョンから変換されたプロジェクトでエラーを有効にするシンボル。|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|1 つ以上のオブジェクトがアパートメント スレッドを使用しているかどうかを定義します。|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|特定`CString`のコンストラクターを明示的に指定し、意図しない変換を防止します。|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|このマクロを定義して C++ 標準準拠の構文を使用し、非標準構文を使用してメンバー関数へのポインターを初期化すると C4867 コンパイラ エラーが発生します。|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|1 つ以上のオブジェクトがフリー スレッドまたはニュートラル スレッドを使用しているかどうかを定義します。|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|プロジェクトに両方、自由、またはニュートラルとしてマークされたオブジェクトがあることを示すシンボル。 マクロ[_ATL_FREE_THREADED](#_atl_free_threaded)を代わりに使用する必要があります。|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|既定の ATL として名前空間を使用できないシンボル。|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM 関連のコードがプロジェクトと共にコンパイルされないようにする記号。|
|[ATL_NO_VTABLE](#atl_no_vtable)|クラスのコンストラクターおよびデストラクターで vtable ポインターが初期化されないようにするシンボル。|
|[ATL_NOINLINE](#atl_noinline)|関数をインライン展開してはならないことを示す記号。|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|すべてのオブジェクトがシングル スレッド モデルを使用しているかどうかを定義します。|

## <a name="_atl_all_warnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS

ATL の以前のバージョンから変換されたプロジェクトでエラーを有効にするシンボル。

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>解説

Visual C++ .NET 2002 より前の ATL では、多くの警告を無効にし、ユーザー コードに表示されないように、警告を無効にしました。 具体的な内容は次のとおりです。

- C4127 条件式は定数です

- C4786 '識別子' : 識別子がデバッグ情報の 'number' 文字に切り捨てられました

- C4201 非標準の拡張が使用 : 無名の構造体/共用体

- C4103 'ファイル名' : 配置#pragma変更するためにパックを使用

- C4291 '宣言' : 一致する演算子削除が見つかりません。初期化が例外をスローした場合、メモリは解放されません

- C4268 '識別子' : 'const' の静的/グローバル データは、コンパイラによって生成された既定のコンストラクターで初期化され、オブジェクトに 0 が入力されます。

- C4702 到達不能コード

以前のバージョンから変換されたプロジェクトでは、これらの警告はライブラリヘッダーによって無効にされたままです。

ライブラリ ヘッダーをインクルードする前に、次の行を*pch.h* (Visual Studio 2017 以前のバージョンの*stdafx.h)* ファイルに追加すると、この動作を変更できます。

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

この`#define`オプションを追加すると、ATL ヘッダーは、これらの警告の状態を保持して、グローバルに無効にしないように注意します (または、ユーザーが個々の警告を明示的に無効にした場合は、有効にしないように注意してください)。

新しいプロジェクトでは`#define`、既定で*pch.h* (Visual Studio 2017 以前の*stdafx.h)* にこのセットがあります。

## <a name="_atl_apartment_threaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED

1 つ以上のオブジェクトがアパートメント スレッドを使用しているかどうかを定義します。

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>解説

アパートメント スレッドを指定します。 その他[のスレッドオプションについてはプロジェクトのスレッドモデルの指定](../../atl/specifying-the-threading-model-for-a-project-atl.md)、ATL オブジェクトで使用できるスレッドモデルの説明については[、「ATL シンプル オブジェクト ウィザードのオプション](../../atl/reference/options-atl-simple-object-wizard.md)」を参照してください。

## <a name="_atl_cstring_explicit_constructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS

特定`CString`のコンストラクターを明示的に指定し、意図しない変換を防止します。

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>解説

このコンストラクターが定義されると、1 つのパラメーターを受け取る CString コンストラクターはすべて explicit キーワードを使用してコンパイルされるため、入力引数の暗黙の変換が行われません。 たとえば、_UNICODE定義すると、cString コンストラクタ引数として char* 文字列を使用しようとすると、コンパイラ エラーが発生します。 このマクロは、幅の狭い文字列型と幅の狭い文字列型間の暗黙の変換を防ぐ必要がある場合に使用します。

すべてのコンストラクター文字列引数で _T マクロを使用すると、_ATL_CSTRING_EXPLICIT_CONSTRUCTORS定義でき、_UNICODE定義されているかどうかに関係なくコンパイル エラーを回避できます。

## <a name="_atl_enable_ptm_warning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING

このマクロを定義して、メンバー関数へのポインターに ANSI C++ 標準準拠構文を使用するようにします。 このマクロを使用すると、非標準構文を使用してメンバー関数へのポインターを初期化すると、C4867 コンパイラ エラーが生成されます。

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>解説

ATL および MFC ライブラリは、Microsoft C++ コンパイラの改良された標準 C++ 準拠に合わせて変更されました。 ANSI C++ 標準に従って、クラス メンバー関数へのポインターの構文は`&CMyClass::MyFunc`.

[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)が定義されていない場合 (既定の場合)、ATL/MFC はマクロ マップ (特にメッセージ マップ) で C4867 エラーを無効にし、以前のバージョンで作成されたコードは以前と同じ方法でビルドを続行できます。 **_ATL_ENABLE_PTM_WARNING**を定義する場合、コードは C++ 標準準拠である必要があります。

ただし、非標準形式は非推奨になりました。 既存のコードを C++ 標準準拠の構文に移動する必要があります。 コード例を次に示します。

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

次のように変更する必要があります。

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

マップ マクロの場合は、アンパサンドの '&' 文字を追加します。 コードに文字を追加し直す必要はありません。

## <a name="_atl_free_threaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED

1 つ以上のオブジェクトがフリー スレッドまたはニュートラル スレッドを使用しているかどうかを定義します。

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>解説

フリー スレッドを指定します。 フリー スレッドは、マルチスレッド アパートメント モデルと同じです。 その他[のスレッドオプションについてはプロジェクトのスレッドモデルの指定](../../atl/specifying-the-threading-model-for-a-project-atl.md)、ATL オブジェクトで使用できるスレッドモデルの説明については[、「ATL シンプル オブジェクト ウィザードのオプション](../../atl/reference/options-atl-simple-object-wizard.md)」を参照してください。

## <a name="_atl_multi_threaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED

プロジェクトに両方、自由、またはニュートラルとしてマークされたオブジェクトがあることを示すシンボル。

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>解説

このシンボルが定義されている場合、ATL はグローバル データへのアクセスを正しく同期するコードを取得します。 新しいコードでは、同等のマクロ[_ATL_FREE_THREADEDを](#_atl_free_threaded)代わりに使用する必要があります。

## <a name="_atl_no_automatic_namespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE

既定の ATL として名前空間を使用できないシンボル。

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>解説

このシンボルが定義されていない場合、atlbase.h を含む名前空間**ATL を使用して**既定で実行され、名前の競合が発生する可能性があります。 これを防ぐには、この記号を定義します。

## <a name="_atl_no_com_support"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT

COM 関連のコードがプロジェクトと共にコンパイルされないようにする記号。

```
_ATL_NO_COM_SUPPORT
```

## <a name="atl_no_vtable"></a><a name="atl_no_vtable"></a>ATL_NO_VTABLE

クラスのコンストラクターおよびデストラクターで vtable ポインターが初期化されないようにするシンボル。

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>解説

vtable ポインターがクラスのコンストラクターとデストラクターで初期化されないようにすると、リンカーは vtable とそれが指すすべての関数を除去できます。 **__declspec (novtable)** に展開します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

## <a name="atl_noinline"></a><a name="atl_noinline"></a>ATL_NOINLINE

関数をインライン展開してはならないことを示す記号。

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>パラメーター

*マイファンクション*<br/>
インライン化してはならない関数。

### <a name="remarks"></a>解説

関数がインライン関数でインライン化されないようにするには、この記号を使用します。 **__declspec (noinline)** に展開します。

## <a name="_atl_single_threaded"></a><a name="_atl_single_threaded"></a>_ATL_SINGLE_THREADED

すべてのオブジェクトがシングル スレッド モデルを使用するかどうかの定義

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>解説

オブジェクトが常にプライマリ COM スレッドで実行されることを指定します。 その他[のスレッドオプションについてはプロジェクトのスレッドモデルの指定](../../atl/specifying-the-threading-model-for-a-project-atl.md)、ATL オブジェクトで使用できるスレッドモデルの説明については[、「ATL シンプル オブジェクト ウィザードのオプション](../../atl/reference/options-atl-simple-object-wizard.md)」を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
