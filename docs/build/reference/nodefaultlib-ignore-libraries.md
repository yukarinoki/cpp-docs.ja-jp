---
description: 詳細について:/NODEFAULTLIB (ライブラリを無視する)
title: /NODEFAULTLIB (ライブラリを無視する)
ms.date: 03/26/2019
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
ms.openlocfilehash: 1443d7ac1e17d464baa829d8297234ae80f3b998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196712"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (ライブラリを無視する)

> **/NODEFAULTLIB**[__:__*library*]

## <a name="arguments"></a>引数

*ライブラリ*<br/>
外部参照を解決するときに、リンカーが無視するライブラリ。

## <a name="remarks"></a>解説

/NODEFAULTLIB オプションは、外部参照を解決するときに検索するライブラリの一覧から1つ以上の既定のライブラリを削除するようにリンカーに指示します。

既定のライブラリへの参照を含まない .obj ファイルを作成するには、 [/zl (既定のライブラリ名の省略)](zl-omit-default-library-name.md)を使用します。

既定では、/NODEFAULTLIB は外部参照を解決するときに検索するライブラリの一覧からすべての既定のライブラリを削除します。 オプション *ライブラリ* パラメーターを使用すると、外部参照を解決するときに検索するライブラリの一覧から、指定したライブラリを削除できます。 除外するライブラリごとに1つの/NODEFAULTLIB オプションを指定します。

リンカーは、明示的に指定したライブラリ内で最初に検索し、次に [/DEFAULTLIB:](defaultlib-specify-default-library.md) オプションで指定された既定のライブラリ内で検索して、.obj ファイル内の既定のライブラリで検索することで、外部定義への参照を解決します。

/NODEFAULTLIB:*library は*、両方で同じ *ライブラリ* 名が指定されている場合、/DEFAULTLIB:*library* をオーバーライドします。

/NODEFAULTLIB を使用して C ランタイムライブラリなしでプログラムをビルドする場合は、 [/entry](entry-entry-point-symbol.md) を使用してプログラムのエントリポイント関数を指定することも必要になる場合があります。 詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **入力**] プロパティページを選択します。

1. [ **すべての既定のライブラリを無視** する] プロパティを選択します。 または、無視するライブラリのセミコロン区切りのリストを、[ **特定の既定のライブラリを無視** する] プロパティで指定します。 [ **コマンドライン** ] プロパティページには、これらのプロパティに加えた変更の影響が表示されます。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> と <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A> を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
