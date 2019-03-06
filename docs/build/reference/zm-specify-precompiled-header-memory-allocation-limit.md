---
title: /Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)
ms.date: 11/04/2016
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
ms.openlocfilehash: d0f79ed1b38401abbc65898193f2305bd432bb28
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419921"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)

コンパイラがプリコンパイル済みヘッダーを構築するために割り当てるメモリの量を決定します。

## <a name="syntax"></a>構文

```
/Zmfactor
```

## <a name="arguments"></a>引数

*factor*<br/>
コンパイラがプリコンパイル済みヘッダーを構築するために使用するメモリの量を決定するスケール ファクター。

*係数*引数がコンパイラによって定義された作業バッファーの既定のサイズの割合。 既定値*係数*100 (パーセント) は拡大または縮小の量を指定することができます。

## <a name="remarks"></a>Remarks

以前のバージョンの Visual C++ では、コンパイラはいくつかの独立したヒープを使用し、ヒープにはそれぞれ大きさの限界がありました。 現在では、コンパイラは必要に応じてヒープを合計ヒープ サイズ制限まで動的に拡張します。固定サイズのバッファーはプリコンパイル済みヘッダーを構築するためだけに必要です。 その結果、 **/Zm**コンパイラ オプションが必要なことはほとんどありません。

かどうか、コンパイラはヒープ領域が不足し、出力、 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)を使用すると、エラー メッセージ、 **/Zm**コンパイラ オプション、過度のメモリを予約した可能性があります。 削除を検討して、 **/Zm**オプション。 コンパイラが出力する場合、 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 、付随するエラー メッセージは、 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)メッセージを指定します、*係数*を使用して再コンパイルするときに使用する引数 **/Zm**コンパイラ オプション。

次の表は、*要素*引数は、既定のプリコンパイル済みヘッダーのバッファーのサイズが 75 MB と仮定した場合にメモリ割り当て制限に影響します。

|値*要素*|メモリ割り当て制限|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>メモリ割り当て制限を設定する別の方法

#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で /Zm コンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. ナビゲーション ウィンドウで選択**構成プロパティ**、 **C/C++**、**コマンドライン**します。

1. 入力、 **/Zm**コンパイラ オプションで、**追加オプション**ボックス。

#### <a name="to-set-the-zm-compiler-option-programmatically"></a>/Zm コンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
