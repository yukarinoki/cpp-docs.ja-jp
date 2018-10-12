---
title: -WINMD (Windows メタデータの生成) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 492be2c5510155ab0336070adc4b5ae96a9775c0
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162959"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows メタデータの生成)

Windows ランタイム メタデータ (.winmd) ファイルの生成を有効にします。

> **/WINMD**\[**:**{**いいえ**\|**のみ**}]

## <a name="arguments"></a>引数

**/WINMD**<br/>
ユニバーサル Windows プラットフォーム アプリの既定の設定。 リンカーは、バイナリ実行可能ファイルと .winmd のメタデータ ファイルの両方を生成します。

**/WINMD:NO**<br/>
のみ、バイナリ実行可能ファイルですが .winmd ファイルではなく、リンカーが生成されます。

**/WINMD: のみ**<br/>
.Winmd ファイルのみが、バイナリ実行可能ファイルではなく、リンカーが生成されます。

## <a name="remarks"></a>Remarks

**/WINMD**リンカー オプションは Windows ランタイム メタデータ (.winmd) ファイルの作成を制御する UWP アプリと Windows ランタイム コンポーネントを使用します。 .Winmd ファイルは、Windows ランタイム型と、ランタイム コンポーネントでは、これらの型の実装の場合、メタデータを含んでいる DLL の一種です。 メタデータに依存して、 [ECMA 335](http://www.ecma-international.org/publications/standards/Ecma-335.htm)標準。

既定では、出力ファイル名には、フォーム*binaryname*.winmd します。 別のファイル名を指定するには、使用、 [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)オプション。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **Windows メタデータ**プロパティ ページ。

1. **Windows メタデータの生成**ドロップダウン リスト ボックスで、目的のオプションを選択します。

## <a name="see-also"></a>関連項目

[チュートリアル: 単純な Windows ランタイム コンポーネントの作成および JavaScript による呼び出し](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Microsoft インターフェイス定義言語 3.0 の概要](/uwp/midl-3/intro)<br/>
[/WINMDFILE (winmd ファイルの指定)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (キー ファイルの指定)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (キー コンテナーの指定)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (winmd の部分署名)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
