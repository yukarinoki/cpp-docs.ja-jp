---
title: -EXPORT (関数のエクスポート) |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16ec6be15635ebfc085615015b1221231645970d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894795"
---
# <a name="export-exports-a-function"></a>/EXPORT (関数のエクスポート)

プログラムから名前または序数、または、データでの関数をエクスポートします。

## <a name="syntax"></a>構文

> **/EXPORT:**<em>entryname</em>[**、\@**<em>序数</em>**[、NONAME]** **[、データ]**

## <a name="remarks"></a>Remarks

他のプログラムは、関数を呼び出すことができますができるように、/EXPORT オプションと、関数、プログラムからにエクスポートできます。 データをエクスポートすることもできます。 エクスポートは、通常は DLL で定義されます。

*Entryname*関数またはデータ項目の名前は、呼び出し元プログラムで使用されます。 `ordinal` 範囲 1 ~ 65,535 です。 エクスポート テーブルにインデックスを指定します。指定しない場合`ordinal`、いずれかのリンクが割り当てられます。 **NONAME**キーワード関数をエクスポート序数としてのみせず、 *entryname*します。

**データ**キーワードは、エクスポートされた項目がデータ項目を指定します。 使用して、クライアント プログラム内のデータ項目を宣言する必要があります**extern _declspec**します。

使用の推奨される順序で、定義をエクスポートするための 3 つの方法はあります。

1. [方式](../../cpp/dllexport-dllimport.md)でソース コード

2. [エクスポート](../../build/reference/exports.md).def ファイル内のステートメント

3. LINK コマンドで、/EXPORT 仕様

3 つのメソッドは、同じプログラム内で使用できます。 リンクは、エクスポートを含むプログラムをビルドも作成、インポート ライブラリのビルドで .exp ファイルを使用しない場合。

リンクは、装飾された識別子の形式。 コンパイラは、.obj ファイルの作成時に識別子を修飾します。 場合*entryname*その非装飾にはリンカーに指定された形式 (ソース コードに表示されます)、リンクは、名前を照合しようとしています。 一意の一致が見つからない場合、リンクは、エラー メッセージを発行します。 使用して、 [DUMPBIN](../../build/reference/dumpbin-reference.md)を取得するためのツール、[装飾名](../../build/reference/decorated-names.md)リンカーに指定する必要がある場合は、識別子の形式。

> [!NOTE]
> 宣言されている C 識別子の装飾形式を指定しない`__cdecl`または`__stdcall`します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

2. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

3. オプションを入力して、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
[リンカー オプション](../../build/reference/linker-options.md)