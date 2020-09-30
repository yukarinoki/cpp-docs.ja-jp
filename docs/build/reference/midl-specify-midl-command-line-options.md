---
title: /MIDL (MIDL コマンド ライン オプションの指定)
ms.date: 09/05/2018
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
ms.openlocfilehash: 3f1b6526f51e5aaa48008792361d3e63249d9f16
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502855"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL コマンド ライン オプションの指定)

MIDL コマンドラインオプションの応答ファイルを指定します。

## <a name="syntax"></a>構文

> **/MIDL: \@ **<em>ファイル</em>

## <a name="arguments"></a>引数

*file*<br/>
[MIDL コマンドラインオプション](/windows/win32/Midl/general-midl-command-line-syntax)を含むファイルの名前。

## <a name="remarks"></a>注釈

IDL ファイルから TLB ファイルへの変換に関するすべてのオプションは、 *ファイル*で指定する必要があります。MIDL コマンドラインオプションは、リンカーのコマンドラインでは指定できません。 /Midl が指定されていない場合は、IDL ファイル名のみを使用して MIDL コンパイラが呼び出され、その他のオプションは呼び出されません。

ファイルには、1行につき1つの MIDL コマンドラインオプションが含まれている必要があります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **埋め込み IDL**プロパティ] ページを選択します。

1. **MIDL コマンド**のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[/IDLOUT (MIDL 出力ファイルの名前の指定)](idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL (属性を MIDL に処理しない)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT (名前。TLB ファイル)](tlbout-name-dot-tlb-file.md)<br/>
[属性付きプログラムの作成](../../windows/attributes/cpp-attributes-com-net.md)
