---
description: 詳細情報:/DEFAULTLIB (既定のライブラリの指定)
title: /DEFAULTLIB (既定のライブラリの指定)
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 9abaf158ed01b3e0a04d29c55d213c8749462c43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201691"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (既定のライブラリの指定)

外部参照を解決するために検索する既定のライブラリを指定します。

## <a name="syntax"></a>構文

> **/DEFAULTLIB**:_ライブラリ_

### <a name="arguments"></a>引数

*ライブラリ*<br/>
外部参照を解決するときに検索するライブラリの名前。

## <a name="remarks"></a>解説

**/DEFAULTLIB** オプションを指定すると、参照を解決するときにリンクが検索するライブラリの一覧に *ライブラリ* が1つ追加されます。 **/DEFAULTLIB** で指定されたライブラリは、コマンドラインで明示的に指定されたライブラリの後、および .obj ファイル内の既定のライブラリの前に検索されます。

引数を指定せずに使用する場合、 [/NODEFAULTLIB (すべての既定のライブラリを無視)](nodefaultlib-ignore-libraries.md) オプションは、すべての **/DEFAULTLIB**:*library* オプションをオーバーライドします。 両方で同じ *ライブラリ* 名が指定されている場合、 **/NODEFAULTLIB**:*library* オプションは **/DEFAULTLIB**:*library* をオーバーライドします。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [ **追加オプション**] で、検索する各ライブラリの **/DEFAULTLIB**:*library* オプションを入力します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
