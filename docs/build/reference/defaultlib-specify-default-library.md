---
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
ms.openlocfilehash: 408507bf0683ea3434ab138fd5ca3a815a1c6a33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494238"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (既定のライブラリの指定)

外部参照を解決するために検索する既定のライブラリを指定します。

## <a name="syntax"></a>構文

> **/DEFAULTLIB**:_ライブラリ_

### <a name="arguments"></a>引数

|引数|説明|
|-|-|
*ライブラリ*|外部参照を解決するときに検索するライブラリの名前。

## <a name="remarks"></a>Remarks

**/DEFAULTLIB**オプションでは、1 つ追加*ライブラリ*リンクが参照を解決するときに検索するライブラリの一覧にします。 指定されているライブラリ **/DEFAULTLIB**後コマンドラインで、既定のライブラリが .obj ファイル内の前に明示的に指定したライブラリが検索されます。

引数を指定せずに使用すると、 [/NODEFAULTLIB (すべて既定のライブラリの無視)](../../build/reference/nodefaultlib-ignore-libraries.md)オプションをすべてオーバーライドされます **/DEFAULTLIB**:*ライブラリ*オプション。 **/NODEFAULTLIB**:*ライブラリ*上書きオプション **/DEFAULTLIB**:*ライブラリ*ときに、同じ*ライブラリ*両方で名前を指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. **追加オプション**、入力、 **/DEFAULTLIB**:*ライブラリ*を検索するには、各ライブラリのオプション。 **OK** を選択して変更を保存してください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
