---
title: プリコンパイル済みヘッダー ファイルの作成
ms.date: 11/19/2018
f1_keywords:
- pch
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: 75ebc466b55cdc2221783531024eefece2e976bb
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413772"
---
# <a name="creating-precompiled-header-files"></a>プリコンパイル済みヘッダー ファイルの作成

Microsoft C および C++ コンパイラは、インライン コードを含む、C または C++ コードをプリコンパイルするためのオプションを提供します。 このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。 安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。

このトピックでは、次のプリコンパイル済みヘッダーの項目について説明します。

- [ソース コードをプリコンパイルする時期](#when-to-precompile-source-code)

- [コードをプリコンパイルする 2 つの方法](#two-choices-for-precompiling-code)

- [プリコンパイル済みヘッダーの一貫性規則](#precompiled-header-consistency-rules)

- [PCH ファイルの使用時の一貫性規則](#consistency-rules-for-per-file-use-of-precompiled-headers)

- [/Yc および/Yu の一貫性規則](#consistency-rules-for-yc-and-yu)

- [プロジェクトでのプリコンパイル済みヘッダーの使用](#using-precompiled-headers-in-a-project)

- [ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)

- [PCH のサンプル メイクファイル](#sample-makefile-for-pch)

- [PCH のサンプル コード](#example-code-for-pch)

プリコンパイル済みヘッダーに関連するコンパイラ オプションの参照については、次を参照してください。 [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)します。

## <a name="when-to-precompile-source-code"></a>ソース コードをプリコンパイルする時期

プリコンパイル済みのコードは、特に場合、コンパイルの時間を短縮する開発サイクル中に便利です。

- 常に、大規模な変更が頻繁にコードの本体を使用します。

- プログラムには、標準的な一連のインクルード ファイルと同じコンパイル オプションを使用して、これらはすべて、複数のモジュールが構成されています。 この場合、すべてのインクルード ファイルを 1 つのプリコンパイル済みヘッダーにプリコンパイルすることができます。

最初のコンパイル-プリコンパイル済みヘッダー (PCH) ファイルを作成する 1 つ、後続のコンパイルよりも少し長きます。 後続のコンパイルは、プリコンパイルされたコードを含めることでより迅速に進むことができます。

C および C++ の両方のアプリケーションをプリコンパイルすることができます。 C++ プログラミングでは、ヘッダー ファイルにクラス インターフェイスの情報を分割する一般的なプラクティスを勧めします。 これらのヘッダー ファイルが後でクラスを使用するプログラムに含まれることができます。 これらのヘッダーをプリコンパイルするには、によってプログラムがコンパイルにかかる時間を削減できます。

> [!NOTE]
> ソース ファイルごと、1 つだけのプリコンパイル済みヘッダー (.pch) ファイルを使用できますが、プロジェクト内の複数の .pch ファイルを使用することができます。

## <a name="two-choices-for-precompiling-code"></a>コードをプリコンパイルする 2 つの方法

Visual c には、C または C++ コードをプリコンパイルすることができます。プリコンパイル ヘッダー ファイルのみに限定されません。

プリコンパイルする場合は、計画、する必要がありますが、単純なヘッダー ファイル以外のソース コードをプリコンパイルする場合は、はるかに高速コンパイルします。

ソース ファイルに複数の一般的なヘッダー ファイルが同じ順序でインクルードされている場合、またはプリコンパイルにソース コードを追加するときに、コードをプリコンパイルします。

プリコンパイル済みヘッダー オプション[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)と[/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)します。 使用 **/Yc**プリコンパイル済みヘッダーを作成します。 オプションを使用すると[hdrstop](../../preprocessor/hdrstop.md)プラグマ、 **/Yc**とソース コードの両方のヘッダー ファイルをプリコンパイルすることができます。 選択 **/Yu**に既存のコンパイル時に、既存のプリコンパイル済みヘッダーを使用します。 使用することも **/Fp**で、 **/Yc**と **/Yu**プリコンパイル済みヘッダーの代替名を提供するオプション。

コンパイラ オプションの参照トピック **/Yu**と **/Yc**開発環境では、この機能にアクセスする方法について説明します。

## <a name="precompiled-header-consistency-rules"></a>プリコンパイル済みヘッダーの一貫性規則

PCH ファイルには、マシンの環境に関する情報のほか、プログラムのメモリ アドレス情報が含まれている、ためにのみが作成されたコンピューターの PCH ファイルを使用する必要があります。

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>PCH ファイルの使用時の一貫性規則

[/Yu](../../build/reference/yu-use-precompiled-header-file.md)コンパイラ オプションを使用して、使用するには、どの PCH ファイルを指定できます。

PCH ファイルを使用する場合、コンパイラが、同じコンパイル環境を前提としています-一貫性のあるコンパイラ オプションや、プラグマを使用する — が有効であった、PCH ファイルを作成したときにそれ以外の場合を指定しない限りです。 コンパイラは、矛盾を検出した場合、警告を発行し、可能であれば、不整合を識別します。 このような警告は、PCH ファイルを使用して問題を必ずしも示していません競合の警告に単に使用します。 PCH ファイルの整合性の要件については、次のセクションで説明します。

### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性

PCH ファイルを使用するときに、次のコンパイラ オプションは矛盾をトリガーできます。

- プリプロセッサ マクロ (/D) オプションには、PCH ファイルを作成したコンパイルと、現在のコンパイル間で同じである必要があります。 定義済みの定数の状態はチェックされませんが、これらを変更する場合に、予期しない結果が発生することができます。

- PCH ファイルは、/E や/EP オプションでは機能しません。

- PCH ファイルは、いずれかの参照情報の生成を使用して作成する必要があります (/FR) オプションまたはローカル変数の除外 (/Fr) オプションの前に、PCH ファイルを使用する後続のコンパイルは、これらのオプションを使用できます。

### <a name="c-70-compatible-z7"></a>C# 7.0 と互換性のある (/Z7)

PCH ファイルの作成時に、このオプションは有効では、PCH ファイルを使用する後続のコンパイルはデバッグ情報を使用できます。

場合、C 7.0 互換 (/Z7) オプションは適用されません PCH ファイルの作成時に、/Z7、PCH ファイルを使用して、後続のコンパイルが警告をトリガーします。 デバッグ情報は、現在の .obj ファイルに配置され、PCH ファイルで定義されているローカル シンボルは、デバッガーを使用できません。

### <a name="include-path-consistency"></a>インクルード パスの一貫性

PCH ファイルには作成時に有効であったインクルード パスに関する情報が含まれていません。 PCH ファイルを使用する場合、コンパイラは常に、現在のコンパイルで指定されたインクルード パスを使用します。

### <a name="source-file-consistency"></a>ソース ファイルの整合性

使用してプリコンパイル済みヘッダー ファイル (/Yu) オプションを指定すると、コンパイラは、すべてのプリプロセッサ ディレクティブ (プラグマを含む) は、事前にコンパイルするソース コードに表示されるを無視します。 このようなプリプロセッサ ディレクティブで指定されたコンパイルは、プリコンパイル済みヘッダー ファイルを作成する (/Yc) オプションとして使用される、コンパイル時と同じである必要があります。

### <a name="pragma-consistency"></a>プラグマの一貫性

プラグマの PCH ファイルの作成時に、通常の処理では、PCH ファイルは、その後使用されるをファイルに影響します。 `comment`と`message`プラグマのコンパイルの残りの部分には影響しません。

これらのプラグマは、PCH ファイル内のコードのみに影響を与えるその後、PCH ファイルを使用するコードには影響しません。

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

これらのプラグマは、プリコンパイル済みヘッダーの一部として保持される、プリコンパイル済みヘッダーを使用するコンパイルの残りの部分に影響を与えます。

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc および /Yu の一貫性規則

/Yc、/Yu またはを使用して作成されたプリコンパイル済みヘッダーを使用すると、コンパイラは、PCH ファイルの作成時に存在している現在のコンパイル環境を比較します。 必ず、現在のコンパイルの前の 1 (一貫性のあるコンパイラ オプションや、プラグマを使用) と一貫性のある環境を指定してください。 コンパイラは、矛盾を検出した場合、警告を発行し、可能であれば、不整合を識別します。 このような警告ではありませんは、PCH ファイルの問題があるとは限りません競合の警告に単に使用します。 次のセクションでは、プリコンパイル済みヘッダーの整合性の要件について説明します。

### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性

次の表は、コンパイラ オプションがプリコンパイル済みヘッダーを使用する場合、不整合の警告をトリガーする可能性があります。

|オプション|名前|ルール|
|------------|----------|----------|
|/D|定数とマクロを定義します。|プリコンパイル済みヘッダーを作成したコンパイルと、現在のコンパイル間で同じである必要があります。 定義済みの定数の状態はチェックされませんが、ファイルが変更された定数の値に依存している場合、予期しない結果が発生することができます。|
|/E または/EP|プリプロセッサ出力を標準出力にコピーします。|プリコンパイル済みヘッダーは、/E または/EP オプションでは動作しません。|
|/Fr や/FR|Microsoft ソース ブラウザー情報を生成します。|/Yu オプションで有効にする/Fr および/FR オプションで、それらもされている必要が有効なプリコンパイル済みヘッダーの作成時にします。 プリコンパイル済みヘッダーを使用して、後続のコンパイルでは、ソース ブラウザー情報も生成します。 ブラウザー情報は 1 つの .sbr ファイル内にし、CodeView 情報と同じ方法で他のファイルで参照されます。 ソース ブラウザー情報の配置をオーバーライドすることはできません。|
|/GA、/GD、/GE、/Gw、または/GW|Windows プロトコルのオプション|プリコンパイル済みヘッダーを作成したコンパイルと、現在のコンパイル間で同じである必要があります。 これらのオプションが異なる場合、警告メッセージが発生します。|
|/ZI|詳細なデバッグ情報を生成します。|プリコンパイル済みヘッダーが作成されたときに、このオプションは有効では、プリコンパイルを使用する後続のコンパイルはデバッグ情報を使用できます。 /Zi でない場合に有効なプリコンパイル済みヘッダーの作成時にプリコンパイルおよび/Zi オプションを使用する後続のコンパイルは、警告をトリガーします。 デバッグ情報は、現在のオブジェクト ファイルに配置され、プリコンパイル済みヘッダーで定義されているローカル シンボルは、デバッガーを使用できません。|

> [!NOTE]
>  プリコンパイル済みヘッダーの機能は、C および C++ ソース ファイルでのみ使用を対象としています。

## <a name="using-precompiled-headers-in-a-project"></a>プロジェクトでのプリコンパイル済みヘッダーの使用

前のセクションでは、プリコンパイル済みヘッダーの概要を紹介:/Yc および/Yu、/Fp オプション、および[hdrstop](../../preprocessor/hdrstop.md)プラグマ。 このセクションは、プロジェクトで手動のプリコンパイル済みヘッダー オプションを使用する方法を説明します。サンプル メイクファイルと、管理しているコードで終了します。

プロジェクトで手動のプリコンパイル済みヘッダー オプションを使用する別の方法については、Visual C の既定のセットアップ中に作成された mfc \src のディレクトリにメイクファイルのいずれかを調べます。 これらメイクファイルは、同じアプローチをここで説明したもの、Microsoft プログラムのメンテナンス ユーティリティ (NMAKE) マクロを使用していて、ビルド プロセスの制御を提供します。

## <a name="pch-files-in-the-build-process"></a>ビルド プロセスでの PCH ファイル

ソフトウェア プロジェクトのコード ベースは通常複数 C または C++ ソース ファイル、オブジェクト ファイル、ライブラリ、およびヘッダー ファイルに含まれています。 通常、メイクファイルでは、実行可能ファイルにこれらの要素の組み合わせを調整します。 次の図は、プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造を示します。 NMAKE マクロの名前とこの図では、ファイル名は例のコードと一貫性のある[PCH のサンプル メイクファイル](#sample-makefile-for-pch)と[PCH のサンプル コード](#example-code-for-pch)します。

図では、図表の 3 つのデバイスを使用して、ビルド プロセスのフローを示します。 という名前の四角形を表す各ファイルまたはマクロです。次の 3 つのマクロは、1 つまたは複数のファイルを表します。 影の部分では、各コンパイルまたはリンク アクションを表します。 矢印は、どのファイルとマクロがコンパイルまたはリンクの処理中に結合を示しています。

![プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造](../../build/reference/media/vc30ow1.gif "プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造") <br/>
プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造

以降、図の上部にある STABLEHDRS と境界は、NMAKE マクロの再コンパイルを必要があります。 そうにないファイルを一覧表示します。 コマンド文字列によってこれらのファイルがコンパイルされます。

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

プリコンパイル済みヘッダー ファイル (STABLE.pch) が存在しない場合にのみ、または 2 つのマクロで示されているファイルに変更を加える場合は。 いずれの場合も、プリコンパイル済みヘッダー ファイルには STABLEHDRS マクロで示されているファイルからのみコードが含まれます。 境界のマクロでは、プリコンパイルする最後のファイルを一覧表示します。

ファイルがこれらのマクロで一覧表示するには、ヘッダー ファイルまたは C または C++ のソース ファイルのいずれかになります。 (1 つの PCH ファイルは C および C++ の両方のモジュールで使用できません)。使用することに注意してください、 **hdrstop**境界ファイル内では、ある時点でのプリコンパイルを停止するマクロ。 参照してください[hdrstop](../../preprocessor/hdrstop.md)詳細についてはします。

下の図は、続行すると、APPLIB.obj は最終的なアプリケーションで使用するサポート コードを表します。 APPLIB.cpp から作成されます、ファイルが、UNSTABLEHDRS マクロに一覧表示され、プリコンパイル済みヘッダーからのコードをプリコンパイルします。

MYAPP.obj では、最終的なアプリケーションを表します。 MYAPP.cpp から作成されます、ファイルが、UNSTABLEHDRS マクロに一覧表示され、プリコンパイル済みヘッダーからのコードをプリコンパイルします。

実行可能ファイル (MYAPP 最後に。OBJ マクロ (APPLIB.obj および MYAPP.obj) で示されているファイルをリンクすることで、EXE) が作成されます。

## <a name="sample-makefile-for-pch"></a>PCH のサンプル メイクファイル

次のメイクファイルのマクロを使用して、!もし！ELSE、!ENDIF フロー制御コマンドは、プロジェクトに簡単に応用する構造体。

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
LINKFLAGS = /NOD /ONERROR:NOEXE
!IF "$(DEBUG)" == "1"
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f
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

"構造体のメイクファイルを使用して、プリコンパイル済みヘッダー ファイル"の図に示した STABLEHDRS、境界、および UNSTABLEHDRS マクロとは別に[ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)、CLFLAGS マクロであり、LINKFLAGS このメイクファイルを提供しますマクロ。 これらのマクロを使用して、コンパイラと、デバッグ ログとアプリケーションの実行可能ファイルの最終バージョンをビルドするかどうかを適用するリンカー オプションを一覧表示する必要があります。 また LIBS マクロが、ライブラリを一覧表示、プロジェクトが必要です。

また、メイクファイルを使用します。もし！ELSE、!ENDIF (nmake の) コマンドラインでデバッグ シンボルを定義するかどうかを検出する:

```NMAKE
NMAKE DEBUG=[1|0]
```

この機能により、開発中に同じのメイクファイルを使用して、プログラムの最終バージョンをデバッグを使用して、最終バージョンの場合は 0 を =。 次のコマンドラインは同等です。

```NMAKE
NMAKE
NMAKE DEBUG=0
```

メイクファイルの詳細については、次を参照してください。 [NMAKE リファレンス](../../build/nmake-reference.md)します。 参照してください[コンパイラ オプション](../../build/reference/compiler-options.md)と[リンカー オプション](../../build/reference/linker-options.md)します。

## <a name="example-code-for-pch"></a>PCH のサンプル コード

説明されているメイクファイルで次のソース ファイルが使用[ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)と[PCH のサンプル メイクファイル](#sample-makefile-for-pch)します。 コメントが重要な情報を含むことに注意してください。

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
#include<iostream.h>
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

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)
