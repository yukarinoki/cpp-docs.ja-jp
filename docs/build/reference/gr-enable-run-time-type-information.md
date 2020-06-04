---
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
ms.openlocfilehash: ee1398b2f9ee78c62fb84aa591e77708cd0d9d83
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439589"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (ランタイム型情報の有効化)

実行時にオブジェクトの種類を確認するコードを追加します。

## <a name="syntax"></a>構文

```
/GR[-]
```

## <a name="remarks"></a>コメント

**/Gr**が on の場合、コンパイラは `_CPPRTTI` プリプロセッサマクロを定義します。 既定では、 **/gr**は on です。 **/Gr-** ランタイム型情報を無効にします。

コンパイラがコード内のオブジェクトの型を静的に解決できない場合は、 **/gr**を使用します。 通常、コードで[Dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)または[typeid](../../cpp/typeid-operator.md)を使用する場合は、 **/gr**オプションが必要です。 ただし、 **/gr**を使用すると、イメージの .rdata セクションのサイズが大きくなります。 コードで**dynamic_cast**または**typeid**が使用されていない場合、より小さな**イメージが生成されること**があります。

実行時の型チェックの詳細については、「  *C++言語リファレンス*」の「[ランタイム型情報](../../cpp/run-time-type-information.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[言語]** プロパティページをクリックします。

1. "**実行時の型情報を有効にする**" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
