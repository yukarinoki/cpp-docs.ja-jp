---
title: -D (プリプロセッサの定義) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
dev_langs:
- C++
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc4da4235b57e9abd8e5f32b8f3e696bd1ce2de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397183"
---
# <a name="d-preprocessor-definitions"></a>/D (プリプロセッサの定義)

ソース ファイルのプリプロセッサ シンボルを定義します。

## <a name="syntax"></a>構文

```
/Dname[= | # [{string | number}] ]
```

## <a name="remarks"></a>Remarks

このシンボルを `#if` または `#ifdef` と一緒に使用すると、ソース コードを条件付きでコンパイルできます。 シンボル定義は、コードで再定義されるまで、または `#undef` ディレクティブによってコードで未定義になるまで有効です。

**/D**と同じ効果があります、`#define`点を除いて、ソース コード ファイルの先頭にディレクティブ **/D**コマンドラインの引用符を削除し、`#define`それらを保持します。

既定では、シンボルに関連付けられる値は 1 です。 たとえば、 **/D** `name`と等価 **/D**`name`**= 1**します。 この記事では、定義の最後の例では**テスト**を印刷するには、`1`します。

使用してコンパイル **/D** `name` **=** と関連付けられている値がないシンボル。 シンボルは引き続きコードの条件コンパイルに使用できますが、何も指定されていないものとして評価されます。 使用してコンパイルする場合の例で **/DTEST =** エラーが発生します。 この動作は、値を指定して、または値を指定せずに `#define` を使用する場合と似ています。

次のコマンドを実行すると、TEST.c で DEBUG シンボルが定義されます。

**CL/DDEBUG をテストします。C**

次のコマンドを実行すると、TEST.c からすべての `__far` キーワードが削除されます。

**CL/D__far テストを = です。C**

**CL**環境変数は、等号 (=) を含む文字列に設定することはできません。 使用する **/D**と共に、 **CL**環境変数を指定してください、等号 (=) ではなくシャープ記号。

```
SET CL=/DTEST#0
```

コマンド プロンプトでプリプロセッサ シンボルを定義する場合は、コンパイラ解析規則とシェル解析規則の両方を考慮してください。 たとえば、プログラムでパーセント記号のプリプロセッサ シンボル (%) を定義するには、コマンド プロンプトでパーセント記号 2 文字 (%%) を指定します。パーセント記号を 1 文字だけ指定すると、解析エラーが発生します。

```
CL /DTEST=%% TEST.C
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 左側のウィンドウで次のように選択します。**構成プロパティ**、 **c/c++**、**プリプロセッサ**します。

1. 右側の列の右側のウィンドウで、**プリプロセッサの定義**プロパティ、ドロップダウン メニューを開き、選択**編集**します。

1. **プリプロセッサの定義**ダイアログ ボックスで、(1 行につき 1 つ) を追加、変更、または 1 つまたは複数の定義を削除します。 **OK** を選択して変更を保存してください。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>

## <a name="example"></a>例

```
// cpp_D_compiler_option.cpp
// compile with: /DTEST
#include <stdio.h>

int main( )
{
    #ifdef TEST
        printf_s("TEST defined %d\n", TEST);
    #else
        printf_s("TEST not defined\n");
    #endif
}
```

```Output
TEST defined 1
```

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/U、/u (定義済みマクロ シンボルの未定義化)](../../build/reference/u-u-undefine-symbols.md)<br/>
[#undef ディレクティブ (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br/>
[#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)