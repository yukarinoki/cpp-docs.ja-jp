---
title: プリコンパイル済みヘッダー ファイルの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- pch
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31d9708f203c3d79d4cf369583c75d348278d06a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379212"
---
# <a name="creating-precompiled-header-files"></a>プリコンパイル済みヘッダー ファイルの作成
  
Microsoft C および C++ コンパイラは、インライン コードを含む、C または C++ コードをプリコンパイルするためのオプションを提供します。 このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。 安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。  
  
このトピックでは、次のプリコンパイル済みヘッダーの内容について説明します。  
  
-   [ソース コードをプリコンパイルする時期](#when-to-precompile-source-code)  
  
-   [コードをプリコンパイルする 2 つの方法](#two-choices-for-precompiling-code)  
  
-   [プリコンパイル済みヘッダーの一貫性規則](#precompiled-header-consistency-rules)  
  
-   [PCH ファイルの使用時の一貫性規則](#consistency-rules-for-per-file-use-of-precompiled-headers)  
  
-   [/Yc および/Yu の一貫性規則](#consistency-rules-for-yc-and-yu)  
  
-   [プロジェクトでのプリコンパイル済みヘッダーの使用](#using-precompiled-headers-in-a-project)  
  
-   [ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)  
  
-   [PCH のサンプル メイクファイル](#sample-makefile-for-pch)  
  
-   [PCH のサンプル コード](#example-code-for-pch)  
  
プリコンパイル済みヘッダーに関連するコンパイラ オプションの参照については、次を参照してください。 [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)です。  
  
<a name="when-to-precompile-source-code"></a>  
  
## <a name="when-to-precompile-source-code"></a>ソース コードをプリコンパイルする時期  
  
プリコンパイルされたコードは特に場合、コンパイル時間を短縮する開発サイクル中に便利です。  
  
-   変更頻度の低いコードの本文を常に使用します。  
  
-   プログラムには、複数のモジュールが使用する標準的な一連のインクルード ファイルと同じコンパイル オプションが構成されています。 この場合、すべてのインクルード ファイル 1 つのプリコンパイル済みヘッダーをプリコンパイルすることができます。  
  
最初のコンパイル: プリコンパイル済みヘッダー (PCH) ファイルを作成する 1 つ、後続のコンパイルより少し時間がかかります。 後続のコンパイルは、プリコンパイルされたコードを含めることでより迅速に行えます。  
  
C と C++ の両方のプログラムをプリコンパイルすることができます。 C++ プログラミングでは、ヘッダー ファイルにクラス インターフェイスの情報を区切るための一般的な方法を勧めします。 これらのヘッダー ファイルは、クラスを使用するプログラムに後で含めることができます。 これらのヘッダーをプリコンパイルするには、によっては、プログラムがコンパイルに要する時間を短縮できます。  
  
> [!NOTE]
>  ソース ファイルごとの 1 つだけのプリコンパイル済みヘッダー (.pch) ファイルを使用できますが、プロジェクト内の複数の .pch ファイルを使用することができます。  
  
<a name="two-choices-for-precompiling-code"></a>  
  
# <a name="two-choices-for-precompiling-code"></a>コードをプリコンパイルする 2 つの方法  
  
Visual C には、C または C++ コードをプリコンパイルすることができます。プリコンパイル ヘッダー ファイルのみに限定されません。  
  
プリコンパイルを計画する必要がありますが、単純なヘッダー ファイル以外のソース コードをプリコンパイルする場合は、はるかに高速コンパイルします。  
  
ソース ファイルに複数の一般的なヘッダー ファイルが同じ順序でインクルードされている場合、またはプリコンパイルにソース コードを追加するときは、コードをプリコンパイルします。  
  
プリコンパイル済みヘッダー オプションは[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)と[/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)です。 使用して **/Yc**プリコンパイル済みヘッダーを作成します。 省略可能なを使用すると[hdrstop](../../preprocessor/hdrstop.md)プラグマ、 **/Yc**とソース コードの両方のヘッダー ファイルをプリコンパイルすることができます。 選択 **/Yu**に既存のコンパイル時に、既存のプリコンパイル済みヘッダーを使用します。 使用することも **/Fp**で、 **/Yc**と **/Yu**プリコンパイル済みヘッダーの代替名を提供するオプションです。  
  
コンパイラ オプションの参照トピック **/Yu**と **/Yc**開発環境でこの機能にアクセスする方法について説明します。  
  
<a name="precompiled-header-consistency-rules"></a>  
  
## <a name="precompiled-header-consistency-rules"></a>プリコンパイル済みヘッダーの一貫性規則  
  
PCH ファイルには、コンピューター環境についての情報だけでなく、プログラムのメモリ アドレス情報が含まれている、ためにのみが作成されたコンピューター上の PCH ファイルを使用する必要があります。  
  
<a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>  
  
## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>PCH ファイルの使用時の一貫性規則

[/Yu](../../build/reference/yu-use-precompiled-header-file.md)コンパイラ オプションを使用して、使用するには、どの PCH ファイルを指定できます。  
  
PCH ファイルを使用する場合、コンパイラが同じコンパイル環境を前提としています-コンパイラ オプションや、プラグマを使用する — を有効であった PCH ファイルを作成したときにそれ以外の場合に指定する場合を除き、します。 コンパイラが矛盾を検出した場合は警告を発行し、可能な限りの不整合を識別します。 このような警告必ずしも PCH ファイルの問題競合を警告に単に使用します。 PCH ファイルに対する一貫性の要件は次のセクションで説明します。  
  
### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性  
  
PCH ファイルを使用する場合、次のコンパイラ オプションは不整合が警告をトリガーできます。  
  
-   マクロがプリプロセッサを使用して作成された (/D) オプションは、PCH ファイルを作成したコンパイルと、現在のコンパイルの間で同じである必要があります。 定義済み定数の状態はチェックされませんが、これらを変更する場合に、予期しない結果が発生することができます。  
  
-   PCH ファイルは、/E や/EP オプションでは機能しません。  
  
-   PCH ファイルは、いずれかの参照情報の生成を使用して作成する必要があります (/FR) オプションまたはローカル変数の除外 (/Fr) PCH ファイルを使用する後続のコンパイルがこれらのオプションを使用する前にオプションです。  
  
### <a name="c-70-compatible-z7"></a>C 7.0 互換 (/Z7)  
  
PCH ファイルの作成時に、このオプションは有効では、PCH ファイルを使用する後続のコンパイルは、デバッグ情報を使用できます。  
  
場合、C 7.0 互換 (/Z7) オプションは適用されません PCH ファイルの作成時に、後続のコンパイル PCH ファイルおよび/Z7 を使用すると警告がトリガーされます。 デバッグ情報は、現在の .obj ファイルに配置され、PCH ファイルで定義されているローカル シンボルは、デバッガーを使用できません。  
  
### <a name="include-path-consistency"></a>インクルード パスの一貫性  
  
PCH ファイルには作成時に有効であったインクルード パスに関する情報が含まれていません。 PCH ファイルを使用すると、コンパイラは常に、現在のコンパイルで指定されたインクルード パスを使用します。  
  
### <a name="source-file-consistency"></a>ソース ファイルの整合性  
  
プリコンパイル済みヘッダー ファイルの使用 (/Yu) オプションを指定すると、コンパイラは、すべてのプリプロセッサ ディレクティブ (プラグマを含む) は、事前にコンパイルするソース コードに表示されるを無視します。 このようなプリプロセッサ ディレクティブで指定された、コンパイルは、プリコンパイル済みヘッダー ファイルを作成する (/Yc) オプションとして使用される、コンパイル時と同じである必要があります。  
  
### <a name="pragma-consistency"></a>プラグマの一貫性    
  
通常の PCH ファイルの作成中に処理されたプラグマには、これで PCH ファイルを使用して、その後、ファイルが反映されます。 `comment`と`message`プラグマ、コンパイル時の残りの部分には影響しません。  
  
これらのプラグマ PCH ファイル内のコードのみに影響を与えるPCH ファイルをそのまま使用するコードには影響しません。  
  
||||  
|-|-|-|  
|`comment`|`page`|`subtitle`|  
|`linesize`|`pagesize`|`title`|  
|`message`|`skip`||  
  
これらのプラグマは、プリコンパイル済みヘッダーの一部として保持して、プリコンパイル済みヘッダーを使用するコンパイルの残りの部分に影響を与えます。  
  
||||  
|-|-|-|  
|`alloc_text`|`include_alias`|`pack`|  
|`auto_inline`|`init_seg`|`pointers_to_members`|  
|`check_stack`|`inline_depth`|`setlocale`|  
|`code_seg`|`inline_recursion`|`vtordisp`|  
|`data_seg`|`intrinsic`|`warning`|  
|`function`|`optimize`||  
  
<a name="consistency-rules-for-yc-and-yu"></a>  
  
## <a name="consistency-rules-for-yc-and-yu"></a>/Yc および /Yu の一貫性規則  
  
/Yc、/Yu またはを使用して作成されたプリコンパイル済みヘッダーを使用する場合、コンパイラは、PCH ファイルの作成時に存在している現在のコンパイル環境を比較します。 必ず以上の 2 つ (コンパイラ オプションや、プラグマを使用)、現在のコンパイルの一貫した環境を指定してください。 コンパイラが矛盾を検出した場合は警告を発行し、可能な限りの不整合を識別します。 このような警告しない PCH ファイルに問題があるとは限りません競合を警告に単に使用します。 次のセクションでは、プリコンパイル済みヘッダーの一貫性の要件を説明します。  
  
### <a name="compiler-option-consistency"></a>コンパイラ オプションの一貫性  
  
次の表は、コンパイラ オプションがプリコンパイル済みヘッダーを使用するときに不整合が警告をトリガーする可能性があります。  
  
|オプション|名前|ルール|  
|------------|----------|----------|  
|/D|定数とマクロを定義します。|プリコンパイル済みヘッダーを作成するコンパイルと、現在のコンパイルの間で同じにする必要があります。 定義済み定数の状態はチェックされませんが、ファイルが変更された定数の値に依存している場合、予期しない結果が発生することができます。|  
|/E または/EP|プリプロセッサ出力を標準出力にコピーします。|プリコンパイル済みヘッダーは、/E または/EP オプションでは機能しません。|  
|/Fr や/FR|Microsoft ソース ブラウザー情報を生成します。|オプションについては、/Fr、/FR/Yu オプションで有効にする、それらもされている必要が有効で、プリコンパイル済みヘッダーの作成時にします。 プリコンパイル済みヘッダーを使用して後続のコンパイルでは、ソース ブラウザー情報も生成します。 ブラウザー情報は単一の .sbr ファイルに配置され、CodeView 情報と同じ方法で他のファイルで参照されます。 ソース ブラウザー情報の配置を上書きすることはできません。|  
|/GA、/GD、/GE、/Gw、または/GW|Windows プロトコル オプション|プリコンパイル済みヘッダーを作成するコンパイルと、現在のコンパイルの間で同じにする必要があります。 これらのオプションが異なる場合、警告メッセージが出力されます。|  
|/ZI|詳細なデバッグ情報を生成します。|このオプションは、プリコンパイル済みヘッダーの作成時に有効では、プリコンパイルを使用する後続のコンパイルはデバッグ情報を使用できます。 /Zi は適用されません、プリコンパイル済みヘッダーの作成時に、プリコンパイルおよび/Zi オプションを使用する後続のコンパイルは、警告をトリガーします。 デバッグ情報は、現在のオブジェクト ファイルに配置され、プリコンパイル済みヘッダーで定義されているローカル シンボルは、デバッガーを使用できません。|  
  
> [!NOTE]
>  プリコンパイル済みヘッダーの機能は C および C++ ソース ファイルでのみ使用するものです。  
  
<a name="using-precompiled-headers-in-a-project"></a>  
  
## <a name="using-precompiled-headers-in-a-project"></a>プロジェクトでのプリコンパイル済みヘッダーの使用  
  
前のセクションでは、プリコンパイル済みヘッダーの概要を示す:/Yc および/Yu、/Fp オプションおよび[hdrstop](../../preprocessor/hdrstop.md)プラグマ。 このセクションで、プロジェクトに手動プリコンパイル済みヘッダー オプションを使用する方法を説明します。サンプル メイクファイルと、管理しているコードで終了します。  
  
プロジェクトで、手動プリコンパイル済みヘッダー オプションの使用に別の方法については、Visual C の既定のセットアップ中に作成された mfc \src ディレクトリにあるメイクファイルのいずれかを検討します。 これらメイクファイル、同様のアプローチをここで説明したものが Microsoft プログラムのメンテナンス ユーティリティ (NMAKE) マクロを使用を取り出して、ビルド プロセスをより厳密に制御を提供します。  
  
<a name="pch-files-in-the-build-process"></a>  
  
## <a name="pch-files-in-the-build-process"></a>ビルド プロセスでの PCH ファイル  
  
複数 C または C++ ソース ファイル、オブジェクト ファイル、ライブラリ、およびヘッダー ファイルでは、通常、ソフトウェア プロジェクトのコード ベースが含まれて。 通常、メイクファイルは、実行可能ファイルにこれらの要素の組み合わせを調整します。 次の図は、プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造を示しています。 NMAKE マクロの名前とこのダイアグラム内のファイル名は、例のコードと整合[PCH のサンプル メイクファイル](#sample-makefile-for-pch)と[PCH のサンプル コード](#example-code-for-pch)です。  
  
図では、3 つの図形式デバイスを使用して、ビルド プロセスのフローを表示します。 四角形を表すをという名前の各ファイルまたはマクロです。3 つのマクロは、1 つまたは複数のファイルを表します。 影の部分では、各のコンパイルまたはリンク アクションを表します。 矢印は、どのファイルとマクロがコンパイルまたはリンクの処理中に結合を示しています。  
  
![プリコンパイル済みヘッダー ファイルを使用するメイクファイル](../../build/reference/media/vc30ow1.gif "プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造")  
##### <a name="structure-of-a-makefile-that-uses-a-precompiled-header-file"></a>プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造  
  
以降では、図の上部にある、STABLEHDRS と境界の両方は、NMAKE マクロを再コンパイルが必要ない可能性の高いファイルを一覧表示。 これらのファイルは、コマンド文字列でコンパイルします。  
  
`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`  
  
プリコンパイル済みヘッダー ファイル (STABLE.pch) が存在しない場合にのみ、または 2 つのマクロで示されているファイルを変更する場合は。 どちらの場合、プリコンパイル済みヘッダー ファイルに STABLEHDRS マクロで示されているファイルからのみコードが含まれています。 境界のマクロでは、プリコンパイルする最後のファイルを一覧表示します。  
  
これらのマクロで指定したファイルには、ヘッダー ファイルまたは C または C++ のソース ファイルのいずれかを指定できます。 (1 つの PCH ファイルは C および C++ の両方のモジュールで使用できません)。使用できるに注意してください、 **hdrstop**境界ファイル内のいくつかの時点でのプリコンパイルを停止するマクロです。 参照してください[hdrstop](../../preprocessor/hdrstop.md)詳細についてはします。  
  
下の図は、続行、APPLIB.obj は最終的にアプリケーションで使用するサポート コードを表します。 APPLIB.cpp から作成されます、ファイルが UNSTABLEHDRS マクロで一覧表示され、プリコンパイル済みヘッダーからコードをプリコンパイル済みです。  
  
MYAPP.obj では、最終的にアプリケーションを表します。 MYAPP.cpp から作成されます、ファイルが UNSTABLEHDRS マクロで一覧表示され、プリコンパイル済みヘッダーからコードをプリコンパイル済みです。  
  
実行可能ファイル (MYAPP 最後に。OBJS マクロ (APPLIB.obj および MYAPP.obj) で示されているファイルをリンクするには、EXE) が作成されます。  
  
<a name="sample-makefile-for-pch"></a>  
  
## <a name="sample-makefile-for-pch"></a>PCH のサンプル メイクファイル  
  
次のメイクファイルのマクロを使用して、!もし！その他、!ENDIF フロー制御コマンドは、プロジェクトに簡単に応用する構造体。  
  
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
  
別に"構造のメイクファイルを使用して、プリコンパイル済みヘッダー ファイル"の図に示す STABLEHDRS、境界、および UNSTABLEHDRS マクロ[ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)、このメイクファイル CLFLAGS マクロであり、LINKFLAGS の提供マクロです。 これらのマクロを使用して、コンパイラと、デバッグ ログとアプリケーションの実行可能ファイルの最終バージョンをビルドするかどうかを適用するリンカー オプションを一覧表示する必要があります。 また LIBS マクロがライブラリを列記したプロジェクトが必要です。  
  
メイクファイルを使用しても!もし！その他、!NMAKE のコマンド ラインでは、デバッグ シンボルを定義するかどうかを検出するために ENDIF:  
  
```NMAKE  
NMAKE DEBUG=[1|0]  
```  
  
この機能により、開発時に同じメイクファイルを使用して、プログラムの最終バージョンのデバッグを使用して最終バージョンの場合は 0 を = です。 次のコマンドラインは等価です。  
  
```NMAKE  
NMAKE   
NMAKE DEBUG=0  
```  
  
メイクファイルの詳細については、次を参照してください。 [NMAKE リファレンス](../../build/nmake-reference.md)です。 参照してください[コンパイラ オプション](../../build/reference/compiler-options.md)と[リンカー オプション](../../build/reference/linker-options.md)です。  
  
<a name="example-code-for-pch"></a>  
  
## <a name="example-code-for-pch"></a>PCH のサンプル コード  
  
説明されているメイクファイルで次のソース ファイルが使用[ビルド プロセスでの PCH ファイル](#pch-files-in-the-build-process)と[PCH のサンプル メイクファイル](#sample-makefile-for-pch)です。 コメントが重要な情報を含めることに注意してください。  
  
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
[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)   
[コンパイラ オプション](../../build/reference/compiler-options.md)