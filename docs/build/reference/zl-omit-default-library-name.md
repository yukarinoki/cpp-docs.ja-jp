---
description: 詳細情報:/Zl (既定のライブラリ名を省略)
title: /Zl (既定のライブラリ名の省略)
ms.date: 11/04/2016
f1_keywords:
- /zl
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
ms.openlocfilehash: eaf39b7bfe1a2b7f2d2c7754cccf8061543e4c7c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224427"
---
# <a name="zl-omit-default-library-name"></a>/Zl (既定のライブラリ名の省略)

.Obj ファイルから既定の C ランタイムライブラリ名を省略します。 既定では、コンパイラでライブラリ名が .obj ファイルにプッシュされ、リンカーに適切なライブラリが示されます。

## <a name="syntax"></a>構文

```
/Zl
```

## <a name="remarks"></a>解説

既定のライブラリの詳細については、「 [Run-Time ライブラリの使用](md-mt-ld-use-run-time-library.md)」を参照してください。

**/Zl** を使用して、ライブラリに格納する .obj ファイルをコンパイルできます。 ライブラリ名を省略しても、1つの .obj ファイルに対して保存される領域の量はわずかですが、多くのオブジェクトモジュールを含むライブラリでは、保存される領域の合計が大きくなります。

このオプションは詳細設定オプションです。 このオプションを設定すると、アプリケーションで必要になる可能性がある特定の C ランタイムライブラリのサポートが削除され、アプリケーションがこのサポートに依存している場合はリンク時エラーが発生します。 このオプションを使用する場合は、他の方法で必要なコンポーネントを提供する必要があります。

/NODEFAULTLIB を使用します [(ライブラリを無視](nodefaultlib-ignore-libraries.md)します)。 すべての .obj ファイル内のライブラリ参照を無視するようにリンカーを設定します。

詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。

**/Zl** を指定してコンパイルすると、 `_VC_NODEFAULTLIB` が定義されます。  次に例を示します。

```cpp
// vc_nodefaultlib.cpp
// compile with: /Zl
void Test() {
   #ifdef _VC_NODEFAULTLIB
      int i;
   #endif

   int i;   // C2086
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. " **既定のライブラリ名を省略** する" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
