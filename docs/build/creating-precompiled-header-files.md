---
title: プリコンパイル済みヘッダー ファイル
ms.date: 10/24/2019
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: 158301ec3caacced1663892071b17ef2b8f8e741
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328668"
---
# <a name="precompiled-header-files"></a>プリコンパイル済みヘッダー ファイル

Visual Studio で新しいプロジェクトを作成すると *、pch.h*という名前*のプリコンパイル済みヘッダー ファイル*がプロジェクトに追加されます。 (Visual Studio 2017 以前では、ファイルは*stdafx.h*と呼ばれます。ファイルの目的は、ビルドプロセスを高速化することです。 標準ライブラリヘッダーなどの`<vector>`安定したヘッダーファイルは、ここに含める必要があります。 プリコンパイル済みヘッダーは、そのヘッダー、またはインクルードするファイルが変更された場合にのみコンパイルされます。 プロジェクトのソース コードを変更するだけの場合、ビルドはプリコンパイル済みヘッダーのコンパイルをスキップします。

プリコンパイル済みヘッダーのコンパイラ オプションは[/Y](reference/y-precompiled-headers.md)です。 プロジェクトのプロパティ ページのオプションは、[**構成プロパティ> C/C++ >プリコンパイル済みヘッダー**] にあります。 プリコンパイル済みヘッダーを使用しないように選択したり、ヘッダー ファイル名、出力ファイルの名前とパスを指定したりできます。

## <a name="custom-precompiled-code"></a>カスタム プリコンパイル済みコード

大規模なプロジェクトのビルドに時間がかかる場合は、カスタム プリコンパイル済みファイルの作成を検討することをお考えください。 Microsoft C および C++ コンパイラは、インライン コードを含む、C または C++ コードをプリコンパイルするためのオプションを提供します。 このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。 安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。

## <a name="when-to-precompile-source-code"></a>ソース コードをプリコンパイルする時期

コンパイル時のコードは、コンパイル時間を短縮するために開発サイクル中に役立ちます。

- 頻繁に変更されない大規模なコードを常に使用します。

- プログラムは複数のモジュールで構成され、そのすべてが標準のインクルード ファイルセットと同じコンパイル オプションを使用します。 この場合、すべてのインクルード ファイルを 1 つのプリコンパイル済みヘッダーにプリコンパイルできます。

プリコンパイル済みヘッダー (PCH) ファイルを作成する最初のコンパイルでは、以降のコンパイルよりも少し時間がかかります。 以降のコンパイルは、プリコンパイル済みコードを含めることにより、より迅速に処理できます。

C プログラムと C++ プログラムの両方をプリコンパイルできます。 C++ プログラミングでは、クラス インターフェイス情報をヘッダー ファイルに分けるのが一般的です。 これらのヘッダー ファイルは、後でクラスを使用するプログラムに含めることができます。 これらのヘッダーをプリコンパイルすることで、プログラムのコンパイルにかかる時間を短縮できます。

> [!NOTE]
> ソース ファイルごとに 1 つのプリコンパイル済みヘッダー (.pch) ファイルしか使用できませんが、プロジェクトで複数の .pch ファイルを使用できます。

## <a name="two-choices-for-precompiling-code"></a>コードをプリコンパイルする 2 つの方法

C または C++ の任意のコードをプリコンパイルできます。ヘッダー ファイルのみをプリコンパイルする場合に限られるわけではありません。

プリコンパイルには計画が必要ですが、単純なヘッダー ファイル以外のソース コードをプリコンパイルすると、コンパイルが大幅に高速化されます。

ソース ファイルで共通のヘッダー ファイル セットが使用されているが、同じ順序でインクルードしない場合、またはプリコンパイルにソース コードを含める場合は、コードをプリコンパイルします。

プリコンパイル済みヘッダー オプションは[、/Yc (プリコンパイル済みヘッダー ファイルの作成)](reference/yc-create-precompiled-header-file.md)および[/Yu (プリコンパイル済みヘッダー ファイルを使用) です](reference/yu-use-precompiled-header-file.md)。 プリコンパイル済みヘッダーを作成するには **、/Yc**を使用します。 オプションの[hdrstop](../preprocessor/hdrstop.md)プラグマと共に使用すると **、/Yc**を使用すると、ヘッダー ファイルとソース コードの両方をプリコンパイルできます。 既存のコンパイルで既存のプリコンパイル済みヘッダーを使用する場合は **、/Yu**を選択します。 **/Fp**を **/Yc**オプションおよび **/Yu**オプションと共に使用して、プリコンパイル済みヘッダーの別名を指定することもできます。

**/Yu**および **/Yc**のコンパイラ オプションリファレンス トピックでは、開発環境でこの機能にアクセスする方法について説明します。

## <a name="precompiled-header-consistency-rules"></a>プリコンパイル済みヘッダーの一貫性規則

PCHファイルには、マシン環境に関する情報とプログラムに関するメモリアドレス情報が含まれているため、PCHファイルを使用するのは、そのファイルが作成されたマシン上でのみ使用してください。

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>PCH ファイルの使用時の一貫性規則

[/Yu](reference/yu-use-precompiled-header-file.md)コンパイラ オプションを使用すると、使用する PCH ファイルを指定できます。

PCH ファイルを使用する場合、コンパイラは、特に指定しない限り、PCH ファイルを作成したときに有効であったコンパイル環境と同じコンパイル環境 (一貫性のあるコンパイラ オプション、プラグマなどを使用するもの) を想定します。 コンパイラは、不整合を検出すると警告を発し、可能な限り不整合を識別します。 このような警告は、必ずしも PCH ファイルに問題があることを示しているわけではありません。競合の可能性を警告するだけです。 PCH ファイルの整合性要件については、次のセクションで説明します。

### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性

PCH ファイルを使用すると、次のコンパイラ オプションが不整合警告を引き起こす可能性があります。

- プリプロセッサ (/D) オプションを使用して作成されたマクロは、PCH ファイルを作成したコンパイルと現在のコンパイルの間で同じである必要があります。 定義された定数の状態はチェックされませんが、これらの変更が起こると、予期しない結果が生じる可能性があります。

- PCH ファイルは /E および /EP オプションでは動作しません。

- PCH ファイルを使用する以降のコンパイルでこれらのオプションを使用するには、PCH ファイルを使用する前に、PCH ファイルを作成する前に、ブラウズ情報の生成 (/FR) オプションまたはローカル変数を除外 (/Fr) オプションを使用する必要があります。

### <a name="c-70-compatible-z7"></a>C 7.0 互換 (/Z7)

PCH ファイルの作成時にこのオプションが有効な場合、PCH ファイルを使用する後続のコンパイルでは、デバッグ情報を使用できます。

PCH ファイルの作成時に C 7.0 互換 (/Z7) オプションが有効でない場合、PCH ファイルと /Z7 を使用する後続のコンパイルによって警告がトリガーされます。 デバッグ情報は現在の .obj ファイルに格納され、PCH ファイルで定義されているローカル シンボルはデバッガーで使用できません。

### <a name="include-path-consistency"></a>パスの一貫性を含める

PCH ファイルには、作成時に有効であったインクルード・パスに関する情報は含まれません。 PCH ファイルを使用する場合、コンパイラは常に現在のコンパイルで指定されたインクルード パスを使用します。

### <a name="source-file-consistency"></a>ソース ファイルの整合性

プリコンパイル済みヘッダー ファイルを使用 (/Yu) オプションを指定すると、プリコンパイルされるソース コードに含まれるプリプロセッサ ディレクティブ (プラグマを含む) はすべてコンパイラによって無視されます。 このようなプリプロセッサ ディレクティブで指定されるコンパイルは、プリコンパイル済みヘッダー ファイルの作成 (/Yc) オプションで使用されるコンパイルと同じである必要があります。

### <a name="pragma-consistency"></a>プラグマの一貫性

PCH ファイルの作成時に処理されたプラグマは、通常、PCH ファイルが使用されるファイルに影響します。 および`comment``message`プラグマは、コンパイルの残りの部分には影響しません。

これらのプラグマは PCH ファイル内のコードにのみ影響します。これらは、後で PCH ファイルを使用するコードには影響しません。

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

これらのプラグマはプリコンパイル済みヘッダーの一部として保持され、プリコンパイル済みヘッダーを使用するコンパイルの残りの部分に影響します。

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc および /Yu の一貫性規則

/Yc または /Yu を使用して作成されたプリコンパイル済みヘッダーを使用すると、コンパイラは現在のコンパイル環境を PCH ファイルの作成時に存在したコンパイル環境と比較します。 現在のコンパイルに対しては、前の環境と一貫性のある環境 (一貫性のあるコンパイラ オプション、プラグマなどを使用) を指定してください。 コンパイラは、不整合を検出すると警告を発し、可能な限り不整合を識別します。 このような警告は、必ずしも PCH ファイルに問題があることを示しているわけではありません。競合の可能性を警告するだけです。 次のセクションでは、プリコンパイル済みヘッダーの一貫性の要件について説明します。

### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性

次の表は、プリコンパイル済みヘッダーを使用するときに不整合警告を引き起こす可能性があるコンパイラ オプションを示しています。

|オプション|名前|ルール|
|------------|----------|----------|
|/D|定数とマクロを定義する|プリコンパイル済みヘッダーを作成したコンパイルと現在のコンパイルの間は同じである必要があります。 定義された定数の状態はチェックされませんが、ファイルが変更された定数の値に依存している場合、予期しない結果が生じる可能性があります。|
|/E または /EP|プリプロセッサ出力を標準出力にコピー|プリコンパイル済みヘッダーは、/E または /EP オプションでは動作しません。|
|/Fr または /FR|マイクロソフトソースブラウザ情報を生成する|/Fr オプションと /FR オプションを /Yu オプションで有効にするには、プリコンパイル済みヘッダーの作成時にも有効になっている必要があります。 プリコンパイル済みヘッダーを使用する以降のコンパイルでも、ソース ブラウザー情報が生成されます。 ブラウザー情報は、単一の .sbr ファイルに格納され、CodeView 情報と同様に他のファイルによって参照されます。 ソース ブラウザ情報の配置を上書きすることはできません。|
|/GA、/GD、/GE、/Gw、または /GW|Windows プロトコル オプション|プリコンパイル済みヘッダーを作成したコンパイルと現在のコンパイルの間は同じである必要があります。 これらのオプションが異なる場合は、警告メッセージが表示されます。|
|/ZI|完全なデバッグ情報を生成する|プリコンパイル済みヘッダーの作成時にこのオプションが有効な場合、プリコンパイルを使用する以降のコンパイルでは、そのデバッグ情報を使用できます。 プリコンパイル済みヘッダーの作成時に /Zi が有効でない場合、プリコンパイルと /Zi オプションを使用する後続のコンパイルによって警告が発生します。 デバッグ情報は現在のオブジェクト ファイルに格納され、プリコンパイル済みヘッダーで定義されているローカル シンボルはデバッガーで使用できません。|

> [!NOTE]
> プリコンパイル済みヘッダー機能は、C および C++ ソース ファイルでのみ使用することを目的としています。

## <a name="using-precompiled-headers-in-a-project"></a>プロジェクトでのプリコンパイル済みヘッダーの使用

前のセクションでは、プリコンパイル済みヘッダーの概要を示します: /Yc と /Yu、/Fp オプション、および[hdrstop](../preprocessor/hdrstop.md)プラグマ。 このセクションでは、プロジェクトで手動のプリコンパイル済みヘッダー オプションを使用する方法について説明します。このコードは、makefile の例と、それが管理するコードで終わります。

プロジェクトで手動プリコンパイル済みヘッダー オプションを使用する別の方法については、Visual Studio の既定のセットアップ時に作成される MFC\SRC ディレクトリにあるメイクファイルの 1 つを調べます。 これらのメイクファイルは、このセクションで説明したものと同様のアプローチを採用していますが、Microsoft プログラムメンテナンスユーティリティ (NMAKE) マクロを使用して、ビルドプロセスをより大きく制御できます。

## <a name="pch-files-in-the-build-process"></a>ビルド プロセスでの PCH ファイル

ソフトウェア プロジェクトのコード ベースは、通常、複数の C または C++ ソース ファイル、オブジェクト ファイル、ライブラリ、およびヘッダー ファイルに含まれています。 通常、メイクファイルは、これらの要素の組み合わせを実行可能ファイルに調整します。 次の図は、プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造を示しています。 この図の NMAKE マクロ名とファイル名は[、「PCH のサンプルメイクファイル」および「PCH コード](#sample-makefile-for-pch)[のサンプル」](#example-code-for-pch)に記載されているコード例と一致しています。

図では、3 つの図式デバイスを使用して、ビルド プロセスのフローを示しています。 名前付きの四角形は、各ファイルまたはマクロを表します。3 つのマクロは、1 つ以上のファイルを表します。 シェーディング領域は、各コンパイルアクションまたはリンクアクションを表します。 矢印は、コンパイルまたはリンク処理中に結合されたファイルとマクロを示します。

![プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造](media/vc30ow1.gif "プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造") <br/>
プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造

図の上部から、STABLEHDRS と BOUNDRY は、再コンパイルが必要と思われる可能性が低いファイルを一覧表示する NMAKE マクロです。 これらのファイルは、コマンド文字列によってコンパイルされます。

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

プリコンパイル済みヘッダー ファイル (STABLE.pch) が存在しない場合、または 2 つのマクロに示されているファイルに変更を加えた場合に限ります。 いずれの場合も、コンパイル済みヘッダー ファイルには、STABLEHDRS マクロにリストされているファイルからのコードのみが含まれます。 BOUNDRY マクロでプリコンパイルする最後のファイルをリストします。

これらのマクロに含まれるファイルは、ヘッダー ファイルまたは C または C++ のソース ファイルのいずれかです。 (単一の PCH ファイルは、C モジュールと C++ モジュールの両方で使用することはできません。**hdrstop**マクロを使用して、BOUNDRY ファイル内のある時点でプリコンパイルを停止できます。 詳細については[、hdrstop](../preprocessor/hdrstop.md)を参照してください。

図の下に続いて、APPLIB.obj は最終的なアプリケーションで使用されるサポート コードを表します。 このファイルは、APPLIB.cpp、UNSTABLEHDRS マクロにリストされているファイル、およびプリコンパイル済みヘッダーからのプリコンパイル済みコードから作成されます。

MYAPP.obj は、最終的なアプリケーションを表します。 これは、MYAPP.cpp、UNSTABLEHDRS マクロにリストされているファイル、およびプリコンパイル済みヘッダーからのプリコンパイル済みコードから作成されます。

最後に、実行可能ファイル (MYAPP.EXE) は、OBJS マクロ (APPLIB.obj および MYAPP.obj) に一覧表示されているファイルをリンクして作成されます。

## <a name="sample-makefile-for-pch"></a>PCH のサンプル メイクファイル

次のメイクファイルはマクロと !もし！他！ENDIF フロー・オブ・コントロール・コマンド構造を使用して、プロジェクトへの適合を単純化します。

```NMAKE
# Makefile : Illustrates the effective use of precompiled
#            headers in a project
# Usage:     NMAKE option
# option:    DEBUG=[0|1]
#            (DEBUG not defined is equivalent to DEBUG=0)
#
OBJS = myapp.obj applib.obj
# List all stable header files in the STABLEHDRS macro.
STABLEHDRS = stable.h another.h
# List the final header file to be precompiled here:
BOUNDRY = stable.h
# List header files under development here:
UNSTABLEHDRS = unstable.h
# List all compiler options common to both debug and final
# versions of your code here:
CLFLAGS = /c /W3
# List all linker options common to both debug and final
# versions of your code here:
LINKFLAGS = /nologo
!IF "$(DEBUG)" == "1"
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi
LINKFLAGS = $(LINKFLAGS) /COD
LIBS      = slibce
!ELSE
CLFLAGS   = $(CLFLAGS) /Oselg /Gs
LINKFLAGS = $(LINKFLAGS)
LIBS      = slibce
!ENDIF
myapp.exe: $(OBJS)
    link $(LINKFLAGS) @<<
$(OBJS), myapp, NUL, $(LIBS), NUL;
<<
# Compile myapp
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp
# Compile applib
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp
# Compile headers
stable.pch : $(STABLEHDRS)
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp
```

[ビルドプロセスの PCH](#pch-files-in-the-build-process)ファイルの「プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造」の図に示されている STABLEHDRS、BOUNDRY、および UNSTABLEHDRS マクロ以外に、このメイクファイルは CLFLAGS マクロと LINKFLAGS マクロを提供します。 これらのマクロを使用して、アプリケーションの実行可能ファイルのデバッグ バージョンと最終バージョンのどちらをビルドするかに関係なく、適用されるコンパイラ オプションとリンカー オプションを一覧表示する必要があります。 プロジェクトに必要なライブラリをリストする LIBS マクロもあります。

メイクファイルも使用しています!もし！他！ENDIF を使用して、NMAKE コマンド ラインで DEBUG シンボルを定義するかどうかを検出します。

```NMAKE
NMAKE DEBUG=[1|0]
```

この機能を使用すると、開発中とプログラムの最終バージョンで同じメイクファイルを使用できます。 次のコマンド ラインは同じです。

```NMAKE
NMAKE
NMAKE DEBUG=0
```

メイクファイルの詳細については、「 NMAKE リファレンス 」を[参照してください。](reference/nmake-reference.md) [MSVC コンパイラ オプション](reference/compiler-options.md)および[MSVC リンカ オプション](reference/linker-options.md)も参照してください。

## <a name="example-code-for-pch"></a>PCH のサンプル コード

以下のソース ファイルは[、PCH のビルド プロセス](#pch-files-in-the-build-process)および[PCH のサンプルメイク](#sample-makefile-for-pch)ファイルで説明されているメイクファイルで使用されます。 コメントには重要な情報が含まれていることに注意してください。

```cpp
// ANOTHER.H : Contains the interface to code that is not
//             likely to change.
//
#ifndef __ANOTHER_H
#define __ANOTHER_H
#include<iostream>
void savemoretime( void );
#endif // __ANOTHER_H
```

```cpp
// STABLE.H : Contains the interface to code that is not likely
//            to change. List code that is likely to change
//            in the makefile's STABLEHDRS macro.
//
#ifndef __STABLE_H
#define __STABLE_H
#include<iostream>
void savetime( void );
#endif // __STABLE_H
```

```cpp
// UNSTABLE.H : Contains the interface to code that is
//              likely to change. As the code in a header
//              file becomes stable, remove the header file
//              from the makefile's UNSTABLEHDR macro and list
//              it in the STABLEHDRS macro.
//
#ifndef __UNSTABLE_H
#define __UNSTABLE_H
#include<iostream>
void notstable( void );
#endif // __UNSTABLE_H
```

```cpp
// APPLIB.CPP : This file contains the code that implements
//              the interface code declared in the header
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
using namespace std;
// The following code represents code that is deemed stable and
// not likely to change. The associated interface code is
// precompiled. In this example, the header files STABLE.H and
// ANOTHER.H are precompiled.
void savetime( void )
    { cout << "Why recompile stable code?\n"; }
void savemoretime( void )
    { cout << "Why, indeed?\n\n"; }
// The following code represents code that is still under
// development. The associated header file is not precompiled.
void notstable( void )
    { cout << "Unstable code requires"
            << " frequent recompilation.\n";
    }
```

```cpp
// MYAPP.CPP : Sample application
//             All precompiled code other than the file listed
//             in the makefile's BOUNDRY macro (stable.h in
//             this example) must be included before the file
//             listed in the BOUNDRY macro. Unstable code must
//             be included after the precompiled code.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
int main( void )
{
    savetime();
    savemoretime();
    notstable();
}
```

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
