---
description: 詳細情報:/GA (Windows アプリケーションの最適化)
title: /GA (Windows アプリケーションの最適化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: f9d65dce26e80b585abc4d67e2eef55f10cb365b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191980"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Windows アプリケーションの最適化)

によって、スレッドローカルストレージ (TLS) 変数にアクセスするための .exe ファイルのコードがより効率的になります。

## <a name="syntax"></a>構文

```
/GA
```

## <a name="remarks"></a>解説

**/GA** は、Windows ベースのプログラムで [__declspec (thread)](../../cpp/declspec.md) を使用して宣言されたデータへのアクセスを高速化します。 このオプションを設定した場合、 [__tls_index](/windows/win32/ProcThread/thread-local-storage) マクロは0と見なされます。

DLL に **/GA** を使用すると、コードの生成に問題が生じる可能性があります。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
