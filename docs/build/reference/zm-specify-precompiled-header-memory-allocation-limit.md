---
description: 詳細情報:/Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)
title: /Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)
ms.date: 03/08/2019
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: 624d8926961d9ca3d32ef204b70683c14dc3197f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224388"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)

コンパイラがプリコンパイル済みヘッダーを構築するために割り当てるメモリの量を決定します。

## <a name="syntax"></a>構文

```
/Zmfactor
```

## <a name="arguments"></a>引数

*段階*<br/>
コンパイラがプリコンパイル済みヘッダーを構築するために使用するメモリの量を決定するスケール ファクター。

*Factor* 引数は、コンパイラで定義された作業バッファーの既定のサイズに対する割合です。 既定値は 100 (パーセント *) ですが* 、より大きいまたは小さい値を指定することもできます。

## <a name="remarks"></a>解説

Visual Studio 2015 より前のバージョンでは、C++ コンパイラは複数の独立したヒープを使用しており、それぞれに有限の制限がありました。 現時点では、コンパイラはヒープサイズの上限まで必要に応じてヒープを動的に拡張し、プリコンパイル済みヘッダーが複数のアドレス範囲を構成できるようにします。 そのため、 **/zm** コンパイラオプションはほとんど必要ありません。

コンパイラがヒープスペースを使い果たし、 **/zm** コンパイラオプションを使用すると [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)エラーメッセージが出力される場合、予約されているメモリが多すぎる可能性があります。 **/Zm** オプションを削除することを検討してください。

コンパイラによって [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)エラーメッセージが出力された場合、付随する [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)メッセージは、 **/zm** コンパイラオプションを使用して再コンパイルするときに使用する *factor* 引数を指定します。 このメッセージは、プリコンパイル済みヘッダーでが使用されている場合にのみ重要です `#pragma hdrstop` 。 それ以外の場合は、Windows 仮想メモリの負荷の問題によって発生する誤ったエラーであるため、 **/zm** オプションを使用することをお勧めします。 代わりに、 **/maxcpucount** オプションを使用して、CL.EXE する **/mp** オプションと組み合わせて MSBUILD.EXE する場合は、並列処理の数を減らすことを検討してください。 詳細については、「 [プリコンパイル済みヘッダー (PCH) の問題と推奨事項](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/)」を参照してください。

次の表は、既定のプリコンパイル済みヘッダーバッファーのサイズが 75 MB であると仮定した場合に、 *factor* 引数がメモリ割り当て制限に与える影響を示しています。

|*係数* の値|メモリ割り当て制限|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>メモリ割り当て制限を設定する別の方法

### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で /Zm コンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. ナビゲーションウィンドウで、[**構成プロパティ**] [  >  **C/c + +**  >  **] [コマンドライン**] の順に選択します。

1. [**追加オプション**] ボックスに **/zm** コンパイラオプションを入力します。

### <a name="to-set-the-zm-compiler-option-programmatically"></a>/Zm コンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
