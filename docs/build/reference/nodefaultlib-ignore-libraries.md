---
title: /NODEFAULTLIB (ライブラリを無視する)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
ms.openlocfilehash: cacc1ef312065da5d6e62ddba1040e87fae9d709
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807456"
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

既定のライブラリへの参照を含まない .obj ファイルを作成するには、使用[/Zl (既定ライブラリ名の省略)](zl-omit-default-library-name.md)します。

既定では、/NODEFAULTLIB は外部参照を解決するときに検索するライブラリの一覧から既定ライブラリをすべて削除します。 省略可能な*ライブラリ*パラメーターでは、外部参照を解決するときに検索するライブラリの一覧から指定したライブラリまたはライブラリを削除することができます。 /NODEFAULTLIB オプションを除外する各ライブラリの 1 つを指定します。

リンカーを明示的に指定し、ライブラリが/DEFAULTLIB オプションで指定された既定のライブラリで、既定のライブラリが .obj ファイル内でしを最初に検索して、外部定義への参照を解決します。

/NODEFAULTLIB:*ライブラリ*よりも優先されます[/DEFAULTLIB:](defaultlib-specify-default-library.md)*ライブラリ*ときに、同じ*ライブラリ*両方で名前を指定します。

/NODEFAULTLIB を使用する場合など、C ランタイム ライブラリなしプログラムをビルドする必要に応じても使用する[/ENTRY](entry-entry-point-symbol.md)をプログラムでエントリ ポイント (関数) を指定します。 詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**入力**プロパティ ページ。

1. 選択、**すべて既定のライブラリの無視**プロパティで無視するライブラリの一覧を指定または、**特定のライブラリの無視**プロパティ。 **コマンドライン**プロパティ ページには、これらのプロパティに加えた変更の効果が表示されます。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> 」および「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
