---
title: -homeparams (レジスタ パラメーターへのコピー スタック) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6c51c5e6062f4d7b793e3adb6e9f22e03a65c11
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699843"
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

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)