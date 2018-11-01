---
title: /homeparams (レジスタ パラメーターのスタックへのコピー)
ms.date: 11/04/2016
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: 952a38d2ab1268ee3dc1fda0899a3ba047281b44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518457"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (レジスタ パラメーターのスタックへのコピー)

関数の実行に入ったときに、レジスタで渡されたパラメーターを、強制的にスタック内のその場所に書き込みます。

## <a name="syntax"></a>構文

```
/homeparams
```

## <a name="remarks"></a>Remarks

このコンパイラ オプションは、x64 のみコンパイラ (ネイティブ コンパイルおよびクロス コンパイル)。

X64 でのパラメーターが渡されると、コンパイルの呼び出し規約によりパラメーターが必要、レジスタに渡されるパラメーターの場合でも。 詳細については、次を参照してください。[パラメーターの引き渡し](../../build/parameter-passing.md)します。 ただし、リリース ビルドでは既定では、登録パラメーターは書き込めません、スタックにパラメーターを既に提供されている領域に。 これにより、プログラムの最適化 (リリース) ビルドをデバッグは困難です。

リリース ビルドでは、使用 **/homeparams**させるアプリケーションをデバッグすることができます。 **/homeparams**スタック レジスタ パラメーターを読み込む必要があるために、パフォーマンスがわけです。

デバッグ ビルドでは、レジスタに渡されるパラメーターを常に、スタックが設定されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)