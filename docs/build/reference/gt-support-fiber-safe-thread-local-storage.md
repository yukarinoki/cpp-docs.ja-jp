---
title: /GT (スレッド ローカル ストレージを使用したファイバー保護のサポート)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 22f9df6248b0ee1af2ef999bbf0dba2e716c9189
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557912"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (スレッド ローカル ストレージを使用したファイバー保護のサポート)

静的スレッド ローカル ストレージを使用して割り当てられたデータを使用して割り当てられたデータに対して、ファイバー保護をサポートしている`__declspec(thread)`します。

## <a name="syntax"></a>構文

```
/GT
```

## <a name="remarks"></a>Remarks

宣言されたデータ`__declspec(thread)`スレッド ローカル ストレージ (TLS) の配列を使用して参照されます。 TLS の配列は、各スレッドに対して、システムが保持しているアドレスの配列です。 この配列内の各アドレスは、スレッド ローカル ストレージのデータの場所を示します。

ファイバーは、軽量オブジェクトをスタックとレジスタのコンテキストで構成され、さまざまなスレッドでスケジュールできます。 ファイバーは、任意のスレッドで実行できます。 ファイバーはスワップ アウトが後に別のスレッドで再起動ため、TLS の配列のアドレスする必要がありますいないキャッシュまたは最適化される共通部分式として関数呼び出しの間で (を参照してください、 [/Og (グローバルの最適化)](../../build/reference/og-global-optimizations.md)オプション詳細情報)。 **/GT**このような最適化を防止します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**最適化**プロパティ ページ。

1. 変更、**ファイバー保護の最適化を有効にする**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)