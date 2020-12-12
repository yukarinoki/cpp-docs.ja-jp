---
description: 詳細情報:/Gs (スタックチェック呼び出しの制御)
title: /Gs (スタック チェック呼び出しの制御)
ms.date: 10/25/2018
f1_keywords:
- /GS
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
ms.openlocfilehash: 128a5ad4dbcba15dfc5b76313b8576ce1448ec68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200164"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (スタック チェック呼び出しの制御)

スタックプローブのしきい値を制御します。

## <a name="syntax"></a>構文

> **/Gs**[*サイズ*]

## <a name="arguments"></a>引数

*size*<br/>
(オプション) スタック プローブが開始される前にローカル変数が占有することのできるバイト数。 **/Gs** と *size* の間にスペースを使用することはできません。

## <a name="remarks"></a>解説

*スタックプローブ* とは、コンパイラが関数呼び出しの開始時に挿入する一連のコードです。 スタック プローブを開始すると、関数のローカル変数を保存するのに必要なスペースの量に応じてメモリに作用します。 これにより、必要に応じて、関数の残りの部分が実行される前に、オペレーティングシステムが追加のスタックメモリに透過的にページされます。

既定で、関数に 1 ページを超えるスタック領域が必要な場合、コンパイラはスタック プローブを開始するコードを生成します。 これは、x86、x64、ARM、および ARM64 プラットフォームの **/Gs4096** のコンパイラオプションに相当します。 この値により、アプリケーションと Windows メモリ マネージャーは、実行時に動的にプログラム スタックにコミットされるメモリの量を増やすことができます。

> [!NOTE]
> **/Gs4096** の既定値を使用すると、Windows のアプリケーションのプログラムスタックを実行時に正しく拡張できます。 既定値は、変更理由が明確でない限り変えないことをお勧めします。

仮想デバイス ドライバーなど一部のプログラムでは、この既定のスタック増加メカニズムは必要ありません。 このような場合、スタックプローブは必要ありません。また、 *サイズ* をローカル変数ストレージに必要な任意の関数よりも大きい値に設定することにより、コンパイラが生成されないようにすることができます。

**/Gs0** は、ローカル変数のストレージを必要とするすべての関数呼び出しに対して、スタックプローブを開始します。 これはパフォーマンスに対して悪影響を及ぼす可能性があります。

X64 ターゲットの場合、*サイズ* 引数なしで **/gs** オプションを指定すると、 **/Gs0** と同じになります。 *Size* 引数が 1 ~ 9 の場合、警告 D9014 が出力され、効果は **/Gs0** を指定した場合と同じになります。

X86、ARM、ARM64 ターゲットの場合、*サイズ* 引数のない **/Gs** オプションは **/Gs4096** と同じになります。 *Size* 引数が 1 ~ 9 の場合、警告 D9014 が出力され、効果は **/Gs4096** を指定した場合と同じになります。

すべてのターゲットについて、10 ~ 2147485647 の *サイズ* 引数は、しきい値を指定された値に設定します。 *サイズ* が2147485648以上の場合は、致命的なエラー C1049 が発生します。

[Check_stack](../../preprocessor/check-stack.md)ディレクティブを使用して、スタックプローブのオンとオフを切り替えることができます。 **/Gs** および `check_stack` プラグマは、標準 C ライブラリルーチンには影響しません。コンパイルする関数のみに影響します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Gs** コンパイラオプションと **追加オプション** のサイズ (オプション) を入力します。 **[OK]** または [**適用**] を選択して、変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
