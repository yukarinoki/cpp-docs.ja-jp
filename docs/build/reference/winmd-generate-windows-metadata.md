---
description: 詳細情報:/WINMD (Windows メタデータの生成)
title: /WINMD (Windows メタデータの生成)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
ms.openlocfilehash: 7cf52a49716e6ec30a29c7e6a96fe7a078b4830c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259085"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows メタデータの生成)

Windows ランタイムメタデータ (winmd) ファイルの生成を有効にします。

> **/WINMD** \[**:**{**なし** \| }]

## <a name="arguments"></a>引数

**/WINMD**<br/>
ユニバーサル Windows プラットフォームアプリの既定の設定。 リンカーは、バイナリ実行可能ファイルと winmd メタデータファイルの両方を生成します。

**/WINMD: いいえ**<br/>
リンカーは、バイナリ実行可能ファイルのみを生成しますが、winmd ファイルは生成しません。

**/WINMD: のみ**<br/>
リンカーは、winmd ファイルのみを生成しますが、バイナリ実行可能ファイルは生成しません。

## <a name="remarks"></a>解説

**/Winmd** リンカーオプションは、UWP アプリと Windows ランタイムコンポーネントに対して、Windows ランタイムメタデータ (WINMD) ファイルの作成を制御するために使用されます。 Winmd ファイルは、Windows ランタイム型のメタデータを含む DLL の一種であり、ランタイムコンポーネントの場合は、これらの型の実装です。 メタデータは [ECMA-335](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 標準に従います。

既定では、出力ファイル名の形式は *binaryname*. winmd です。 別のファイル名を指定するには、 [/WINMDFILE](winmdfile-specify-winmd-file.md) オプションを使用します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [リンカー] [  >    >  **Windows メタデータ**] プロパティページを選択します。

1. [ **Windows メタデータの生成** ] ボックスの一覧で、必要なオプションを選択します。

## <a name="see-also"></a>関連項目

[チュートリアル: 単純な Windows ランタイム コンポーネントの作成と JavaScript からの呼び出し](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Microsoft インターフェイス定義言語3.0 の概要](/uwp/midl-3/intro)<br/>
[/WINMDFILE (winmd ファイルの指定)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (winmd キーファイルの指定)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (キーコンテナーの指定)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (winmd の部分署名)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
