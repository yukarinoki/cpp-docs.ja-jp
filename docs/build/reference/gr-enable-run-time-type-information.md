---
description: 詳細:/GR (Run-Time 型情報の有効化)
title: /GR (ランタイム型情報の有効化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: 61b1a595999e5e00bf6b28c75be2de03467cc4ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200165"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (ランタイム型情報の有効化)

実行時にオブジェクトの種類を確認するコードを追加します。

## <a name="syntax"></a>構文

```
/GR[-]
```

## <a name="remarks"></a>解説

**/Gr** が on の場合、コンパイラは `_CPPRTTI` プリプロセッサマクロを定義します。 既定では、 **/gr** は on です。 **/Gr-** ランタイム型情報を無効にします。

コンパイラがコード内のオブジェクトの型を静的に解決できない場合は、 **/gr** を使用します。 通常、コードで [Dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)または [typeid](../../cpp/typeid-operator.md)を使用する場合は、 **/gr** オプションが必要です。 ただし、 **/gr** を使用すると、イメージの .rdata セクションのサイズが大きくなります。 コードでまたはを使用していない場合は **`dynamic_cast`** **`typeid`** 、小さいイメージ **が** 生成されることがあります。

実行時の型チェックの詳細については、「 *C++ 言語リファレンス*」の「[ランタイム型情報](../../cpp/run-time-type-information.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **言語** ] プロパティページをクリックします。

1. [ **Run-Time の種類の情報を有効にする** ] プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
