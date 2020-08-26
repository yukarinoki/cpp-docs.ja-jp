---
title: プリコンパイル済みヘッダー ファイル
ms.date: 10/24/2019
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: c68de0ee8e6376731254adf965fb9a81f10f2861
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838855"
---
# <a name="precompiled-header-files"></a>プリコンパイル済みヘッダー ファイル

Visual Studio で新しいプロジェクトを作成すると、*pch.h* という名前の "*プリコンパイル済みヘッダーファイル*" がプロジェクトに追加されます。 (Visual Studio 2017 以前では、このファイルは *stdafx.h* と呼ばれていました。)このファイルの目的は、ビルド プロセスを高速化することです。 安定したヘッダー ファイル (たとえば `<vector>` などの、標準ライブラリのヘッダー) はここに含まれています。 プリコンパイル済みヘッダーは、そのヘッダーまたはそこに含まれるファイルが変更された場合にのみコンパイルされます。 プロジェクトのソース コードにだけ変更を加えた場合、ビルド時にプリコンパイル済みヘッダーのコンパイルはスキップされます。

プリコンパイル済みヘッダーのコンパイラ オプションは [/Y](reference/y-precompiled-headers.md) です。 プロジェクトのプロパティ ページでは、オプションは **[構成プロパティ] > [C/ C++] > [プリコンパイル済みヘッダー]** にあります。 プリコンパイル済みヘッダーを使用しないことも選択でき、ヘッダー ファイル名と、出力ファイルの名前とパスを指定できます。

## <a name="custom-precompiled-code"></a>カスタムのプリコンパイル済みコード

ビルドに長時間かかる大規模なプロジェクトの場合、カスタムのプリコンパイル済みファイルの作成を検討することをお勧めします。 Microsoft C および C++ コンパイラは、インライン コードを含む、C または C++ コードをプリコンパイルするためのオプションを提供します。 このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。 安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。

## <a name="when-to-precompile-source-code"></a>ソース コードをプリコンパイルする時期

プリコンパイル済みのコードは、特に次の場合、開発サイクル中のコンパイル時間の短縮に役立ちます。

- 頻繁には変更されない大規模なコード本体を常に使用している。

- プログラムが複数のモジュールで構成され、そのすべてで、標準セットのインクルード ファイルと、同じコンパイル オプションを使用している。 この場合、すべてのインクルード ファイルを 1 つのプリコンパイル済みヘッダーにプリコンパイルできます。

プリコンパイル済みヘッダー (PCH) ファイルが作成される最初のコンパイルでは、後続のコンパイルより少し長く時間がかかります。 後続のコンパイルは、プリコンパイル済みコードを含めることで、より迅速に進めることができます。

C と C++ プログラムのどちらもプリコンパイルできます。 C++ プログラミングでは、クラス インターフェイス情報をヘッダー ファイルに分割するのが一般的です。 これらのヘッダー ファイルは、そのクラスを使用するプログラムに後で含めることができます。 これらのヘッダーをプリコンパイルすると、プログラムのコンパイルにかかる時間を短縮できます。

> [!NOTE]
> 各ソース ファイルで使用できるプリコンパイル済みヘッダー (.pch) ファイルは 1 つだけですが、プロジェクトでは複数の .pch ファイルを使用できます。

## <a name="two-choices-for-precompiling-code"></a>コードをプリコンパイルする 2 つの方法

C または C++ コードをプリコンパイルできますが、プリコンパイルするのはヘッダー ファイルだけに限定されません。

プリコンパイルを行うには計画を立てる必要がありますが、単純なヘッダー ファイル以外のソース コードをプリコンパイルすることで、コンパイルが大幅に高速化されます。

ソース ファイルで共通のヘッダー ファイル セットが使用されていても、同じ順序では含まれていないことがわかっている場合、またはソース コードをプリコンパイルに含める場合は、コードをプリコンパイルしてください。

プリコンパイル済みヘッダーのオプションは、[/Yc (プリコンパイル済みヘッダー ファイルの作成)](reference/yc-create-precompiled-header-file.md) と [/Yu (プリコンパイル済みヘッダー ファイルの使用)](reference/yu-use-precompiled-header-file.md) です。 **/Yc** は、プリコンパイル済みヘッダーを作成する場合に使用します。 オプションの [hdrstop](../preprocessor/hdrstop.md) プラグマとともに **/Yc** を使用すると、ヘッダー ファイルとソース コードの両方をプリコンパイルできます。 **/Yu** は、既存のコンパイルで既存のプリコンパイル済みヘッダーを使用する場合に選択します。 また、 **/Fp** を **/Yc** および **/Yu** オプションとともに使用して、プリコンパイル済みヘッダーに代替名を指定することもできます。

**/Yu** および **/Yc** のコンパイラ オプションのリファレンス トピックでは、開発環境でこの機能にアクセスする方法について説明します。

## <a name="precompiled-header-consistency-rules"></a>プリコンパイル済みヘッダーの一貫性規則

PCH ファイルには、コンピューター環境に関する情報とプログラムに関するメモリ アドレス情報が含まれているため、PCH ファイルは、それが作成されたコンピューター上でのみ使用してください。

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>PCH ファイルの使用時の一貫性規則

[/Yu](reference/yu-use-precompiled-header-file.md) コンパイラ オプションを使用すると、使用する PCH ファイルを指定できます。

PCH ファイルを使用する場合、コンパイラでは、特別に指定しない限り、PCH ファイルを作成したときに有効であった環境と同じ (使用されているコンパイラ オプション、プラグマなどが一貫している) コンパイル環境が想定されます。 コンパイラでは、不整合が検出されると警告が発行され、可能な場合はその不整合が特定されます。 このような警告は、必ずしも PCH ファイルに問題があることを示しているわけではありません。競合が発生する可能性があることを警告するだけです。 PCH ファイルの一貫性の要件については、この後のセクションで説明します。

### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性

PCH ファイルを使用する場合、次のコンパイラ オプションによって不整合の警告がトリガーされることがあります。

- プリプロセッサ (/D) オプションを使用して作成されたマクロは、PCH ファイルを作成したコンパイルと現在のコンパイルの間で同じでなければなりません。 定義された定数の状態はチェックされませんが、これらが変更されると、予測できない結果が生じる可能性があります。

- PCH ファイルは、/E および /EP オプションでは機能しません。

- ブラウザー情報の生成 (/FR) オプションまたはローカル変数の除外 (/Fr) オプションを使用して PCH ファイルを作成してからでないと、その PCH ファイルを使用する後続のコンパイルでこれらのオプションを使用できません。

### <a name="c-70-compatible-z7"></a>C 7.0 互換 (/Z7)

PCH ファイルの作成時にこのオプションが有効になっている場合、その PCH ファイルを使用する後続のコンパイルでデバッグ情報を使用できます。

PCH ファイルの作成時に C 7.0 互換 (/Z7) オプションが有効になっていない場合、PCH ファイルと /Z7 を使用する後続のコンパイルで警告がトリガーされます。 デバッグ情報は現在の .obj ファイルに配置され、PCH ファイルで定義されているローカル シンボルはデバッガーでは使用できません。

### <a name="include-path-consistency"></a>インクルード パスの一貫性

PCH ファイルには、その作成時に有効だったインクルード パスに関する情報は含まれません。 PCH ファイルを使用する場合、コンパイラでは常に現在のコンパイルで指定されたインクルード パスが使用されます。

### <a name="source-file-consistency"></a>ソース ファイルの一貫性

プリコンパイル済みヘッダー ファイルの使用 (/Yu) オプションを指定すると、コンパイラでは、プリコンパイルされるソース コードに現れるすべてのプリプロセッサ ディレクティブ (プラグマを含む) は無視されます。 このプリプロセッサ ディレクティブによって指定されるコンパイルは、プリコンパイル済みヘッダー ファイルの作成 (/Yc) オプションで使用されるコンパイルと同じでなければなりません。

### <a name="pragma-consistency"></a>プラグマの一貫性

PCH ファイルの作成中に処理されるプラグマは、通常、後でその PCH ファイルと一緒に使用されるファイルに作用します。 `comment` および `message` プラグマは、コンパイルの残りの部分には作用しません。

次のプラグマは、PCH ファイル内のコードにのみ作用し、後で PCH ファイルを使用するコードには作用しません。

:::row:::
   :::column span="":::
      `comment`\
      `linesize`
   :::column-end:::
   :::column span="":::
      `message`\
      `page`
   :::column-end:::
   :::column span="":::
      `pagesize`\
      `skip`
   :::column-end:::
   :::column span="":::
      `subtitle`\
      `title`
   :::column-end:::
:::row-end:::

次のプラグマは、プリコンパイル済みヘッダーの一部として保持され、プリコンパイル済みヘッダーを使用するコンパイルの残りの部分に作用します。

:::row:::
   :::column span="":::
      `alloc_text`\
      `auto_inline`\
      `check_stack`\
      `code_seg`\
      `data_seg`
   :::column-end:::
   :::column span="":::
      `function`\
      `include_alias`\
      `init_seg`\
      `inline_depth`
   :::column-end:::
   :::column span="":::
      `inline_recursion`\
      `intrinsic`\
      `optimize`\
      `pack`
   :::column-end:::
   :::column span="":::
      `pointers_to_members`\
      `setlocale`\
      `vtordisp`\
      `warning`
   :::column-end:::
:::row-end:::

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc および /Yu の一貫性規則

/Yc または/Yu を使用して作成されたプリコンパイル済みヘッダーを使用する場合、コンパイラでは、現在のコンパイル環境と PCH ファイルの作成時に存在していた環境が比較されます。 現在のコンパイルには必ず、(一貫性のあるコンパイラ オプション、プラグマなどを使用して) 前の環境と一致する環境を指定してください。 コンパイラでは、不整合が検出されると警告が発行され、可能な場合はその不整合が特定されます。 このような警告は、必ずしも PCH ファイルに問題があることを示しているわけではありません。競合が発生する可能性があることを警告するだけです。 この後のセクションでは、プリコンパイル済みヘッダーの一貫性の要件について説明します。

### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性

次の表に、プリコンパイル済みヘッダーを使用するときに不整合の警告がトリガーされる可能性のあるコンパイラ オプションを示します。

|オプション|名前|ルール|
|------------|----------|----------|
|/D|定数とマクロの定義|プリコンパイル済みヘッダーを作成したコンパイルと現在のコンパイルの間で同じでなければなりません。 定義された定数の状態はチェックされませんが、ファイルが変更された定数の値に依存している場合は予測できない結果が生じる可能性があります。|
|/E または /EP|標準出力へのプリプロセッサ出力のコピー|プリコンパイル済みヘッダーは、/E または /EP オプションでは機能しません。|
|/Fr または /FR|Microsoft ソース ブラウザー情報の生成|/Fr および /FR オプションを /Yu オプションで有効にするには、プリコンパイル済みヘッダーが作成されたときにもこれらが有効になっている必要があります。 プリコンパイル済みヘッダーを使用する後続のコンパイルでも、ソース ブラウザー情報が生成されます。 ブラウザー情報は 1 つの .sbr ファイルに配置され、CodeView 情報と同じ方法で他のファイルから参照されます。 ソース ブラウザー情報の配置をオーバーライドすることはできません。|
|/GA、/GD、/GE、/Gw、/GW|Windows プロトコル オプション|プリコンパイル済みヘッダーを作成したコンパイルと現在のコンパイルの間で同じでなければなりません。 これらのオプションが異なる場合、警告メッセージが発行されます。|
|/ZI|詳細なデバッグ情報の生成|プリコンパイル済みヘッダーの作成時にこのオプションが有効になっている場合、プリコンパイルを使用する後続のコンパイルでそのデバッグ情報を使用できます。 プリコンパイル済みヘッダーの作成時に /Zi が有効になっていない場合、プリコンパイルおよび /Zi オプションを使用する後続のコンパイルで警告がトリガーされます。 デバッグ情報は現在のオブジェクト ファイルに配置され、プリコンパイル済みヘッダーで定義されているローカル シンボルはデバッガーでは使用できません。|

> [!NOTE]
> プリコンパイル済みヘッダー機能は、C および C++ ソース ファイルでの使用のみを目的としています。

## <a name="using-precompiled-headers-in-a-project"></a>プロジェクトでのプリコンパイル済みヘッダーの使用

前のセクションでは、プリコンパイル済みヘッダーの概要 (/Yc と /Yu、/Fp オプション、[hdrstop](../preprocessor/hdrstop.md) プラグマ) を紹介しています。 このセクションでは、プロジェクトで手動プリコンパイル済みヘッダーのオプションを使用する方法について説明します。説明の最後に、サンプルのメイクファイルとそれによって管理されるコードを示します。

プロジェクトで手動プリコンパイル済みヘッダーのオプションを使用する別の方法として、Visual Studio の既定のセットアップ時に作成される MFC/SRC ディレクトリにあるいずれかのメイクファイルを調べます。 これらのメイクファイルでは、このセクションで紹介するものと同様の方法が使用されますが、Microsoft Program Maintenance Utility (NMAKE) マクロがより多く活用され、ビルド プロセスがより細かく制御されます。

## <a name="pch-files-in-the-build-process"></a>ビルド プロセスでの PCH ファイル

通常、ソフトウェア プロジェクトのコード ベースは、複数の C または C++ ソース ファイル、オブジェクト ファイル、ライブラリ、ヘッダー ファイルに含まれています。 一般に、メイクファイルは、これらの要素の組み合わせを調整して 1 つの実行可能ファイルにします。 次の図は、プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造を示しています。 この図の NMAKE マクロ名とファイル名は、「[PCH のサンプル メイクファイル](#sample-makefile-for-pch)」と「[PCH のサンプル コード](#example-code-for-pch)」にあるサンプル コードのものと一致しています。

この図は、3 つの図式デバイスを使用して、ビルド プロセスのフローを示しています。 名前付きの四角形は、各ファイルまたはマクロを表します。3 つのマクロは、1 つ以上のファイルを表します。 網掛け領域は、各コンパイルまたはリンク アクションを表します。 矢印は、コンパイルまたはリンク プロセス中に結合されるファイルとマクロを示します。

![プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造](media/vc30ow1.gif "プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造") <br/>
プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造

図を上から見ていくと、STABLEHDRS と BOUNDRY はいずれも NMAKE マクロであり、ここで、再コンパイルが必要でないと思われるファイルを一覧表示します。 これらのファイルが次のコマンド文字列によってコンパイルされるのは、

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

プリコンパイル済みヘッダー ファイル (STABLE.pch) が存在しない場合、または 2 つのマクロに一覧表示されているファイルに変更を加えた場合のみです。 どちらの場合も、プリコンパイル済みヘッダー ファイルには、STABLEHDRS マクロに一覧表示されているファイルのコードのみが含まれます。 BOUNDRY マクロには、プリコンパイルする最後のファイルを示します。

これらのマクロに一覧表示するファイルは、ヘッダー ファイルか C または C++ ソース ファイルのいずれかです。 (1 つの PCH ファイルを、C と C++ の両方のモジュールで使用することはできません。)**hdrstop** マクロを使用すると、BOUNDRY ファイル内の特定のポイントでプリコンパイルを停止することができます。 詳細については、[hdrstop](../preprocessor/hdrstop.md) に関する記事を参照してください。

さらに図を下に進みます。APPLIB.obj は、最終的なアプリケーションで使用されるサポート コードを表します。 これは、APPLIB.cpp、UNSTABLEHDRS マクロに一覧表示されているファイル、プリコンパイル済みヘッダーのプリコンパイル済みコードから作成されます。

MYAPP.obj は、最終的なアプリケーションを表します。 これは、MYAPP.cpp、UNSTABLEHDRS マクロに一覧表示されているファイル、プリコンパイル済みヘッダーのプリコンパイル済みコードから作成されます。

最後に、OBJ マクロ (APPLIB.obj と MYAPP.obj) に一覧表示されるファイル をリンクして実行可能ファイル (MYAPP.EXE) が作成されます。

## <a name="sample-makefile-for-pch"></a>PCH のサンプル メイクファイル

次のメイクファイルでは、マクロと !IF, !ELSE, !ENDIF 制御フロー コマンド構造を使用して、プロジェクトへの適応を単純化します。

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

「[ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)」の図「プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造」に示されている STABLEHDRS、BOUNDRY、UNSTABLEHDRS マクロとは別に、このメイクファイルには CLFLAGS マクロと LINKFLAGS マクロが用意されています。 これらのマクロを使用して、アプリケーションの実行可能ファイルのデバッグ バージョンと最終バージョンのどちらをビルドする場合でも適用される、コンパイラとリンカーのオプションを一覧表示する必要があります。 また、プロジェクトに必要なライブラリを一覧表示する LIBS マクロもあります。

さらに、このメイクファイルでは、!IF, !ELSE, !ENDIF を使用して、NMAKE コマンド ラインで DEBUG シンボルを定義するかどうかも検出されます。

```NMAKE
NMAKE DEBUG=[1|0]
```

この機能により、開発中とプログラムの最終バージョンで同じメイクファイルを使用できます。最終バージョンでは DEBUG = 0 を使用します。 次のコマンド ラインは同等のものです。

```NMAKE
NMAKE
NMAKE DEBUG=0
```

メイクファイルの詳細については、「[NMAKE リファレンス](reference/nmake-reference.md)」を参照してください。 また、[MSVC コンパイラ オプション](reference/compiler-options.md)に関する記事と [MSVC リンカー オプション](reference/linker-options.md)に関する記事も参照してください。

## <a name="example-code-for-pch"></a>PCH のサンプル コード

次のソース ファイルは、「[ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)」と「[PCH のサンプル メイクファイル](#sample-makefile-for-pch)」で説明されているメイクファイルで使用されます。 コメントには重要な情報が含まれているので注意してください。

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
