---
title: /Zl (既定のライブラリ名の省略)
ms.date: 11/04/2016
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
ms.openlocfilehash: ba30efd76e94749dd261f3528535d674b5e155e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621911"
---
# <a name="zl-omit-default-library-name"></a>/Zl (既定のライブラリ名の省略)

.Obj ファイルから既定の C ランタイム ライブラリ名を省略します。 既定では、コンパイラでライブラリ名が .obj ファイルにプッシュされ、リンカーに適切なライブラリが示されます。

## <a name="syntax"></a>構文

```
/Zl
```

## <a name="remarks"></a>Remarks

既定のライブラリの詳細については、次を参照してください。[ランタイム ライブラリの使用](../../build/reference/md-mt-ld-use-run-time-library.md)します。

使用することができます **/Zl**ライブラリに格納する .obj ファイルをコンパイルします。 少量の単一の .obj ファイルの領域のみを保存するライブラリ名を省略すると、保存領域の合計が大きなオブジェクトの多くのモジュールを含むライブラリ。

このオプションは、高度なオプションです。 このオプションを設定すると、リンク時のエラーをアプリケーションがこのサポートに依存する場合にその結果、アプリケーションで必要とされる特定の C ランタイム ライブラリのサポートが削除されます。 このオプションを使用する場合は、その他の何らかの方法で必要なコンポーネントを提供する必要があります。

使用[/NODEFAULTLIB (ライブラリの無視)](../../build/reference/nodefaultlib-ignore-libraries.md)します。 ライブラリの無視するようにリンカーに指示するには、すべての .obj ファイルで参照します。

詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。

コンパイルするときに **/Zl**、`_VC_NODEFAULTLIB`が定義されています。  例えば:

```
// vc_nodefaultlib.cpp
// compile with: /Zl
void Test() {
   #ifdef _VC_NODEFAULTLIB
      int i;
   #endif

   int i;   // C2086
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**詳細**プロパティ ページ。

1. 変更、**既定ライブラリ名の省略**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)