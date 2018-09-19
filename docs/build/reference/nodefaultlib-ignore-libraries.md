---
title: -NODEFAULTLIB (ライブラリの無視) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs:
- C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae291677743cc05b0eeb85b41ebfa84e5a6e022e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726311"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (ライブラリを無視する)

```
/NODEFAULTLIB[:library]
```

## <a name="arguments"></a>引数

*ライブラリ*<br/>
外部参照を解決するときに無視するライブラリ。

## <a name="remarks"></a>Remarks

/NODEFAULTLIB オプションは、外部参照を解決するときに検索するライブラリの一覧から 1 つまたは複数の既定のライブラリを削除するリンカーに指示します。

既定のライブラリへの参照を含まない .obj ファイルを作成するには、使用[/Zl (既定ライブラリ名の省略)](../../build/reference/zl-omit-default-library-name.md)します。

既定では、/NODEFAULTLIB は外部参照を解決するときに検索するライブラリの一覧から既定ライブラリをすべて削除します。 省略可能な*ライブラリ*パラメーターでは、外部参照を解決するときに検索するライブラリの一覧から指定したライブラリまたはライブラリを削除することができます。 /NODEFAULTLIB オプションを除外する各ライブラリの 1 つを指定します。

リンカーを明示的に指定し、ライブラリが/DEFAULTLIB オプションで指定された既定のライブラリで、既定のライブラリが .obj ファイル内でしを最初に検索して、外部定義への参照を解決します。

/NODEFAULTLIB:*ライブラリ*よりも優先されます[/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*ライブラリ*ときに、同じ*ライブラリ*両方で名前を指定します。

/NODEFAULTLIB を使用する場合など、C ランタイム ライブラリなしプログラムをビルドする必要に応じても使用する[/ENTRY](../../build/reference/entry-entry-point-symbol.md)をプログラムでエントリ ポイント (関数) を指定します。 詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**入力**プロパティ ページ。

1. 選択、**すべて既定のライブラリの無視**プロパティで無視するライブラリの一覧を指定または、**特定のライブラリの無視**プロパティ。 **コマンドライン**プロパティ ページには、これらのプロパティに加えた変更の効果が表示されます。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)