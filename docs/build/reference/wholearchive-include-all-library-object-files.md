---
description: 詳細情報:/WHOLEARCHIVE (すべてのライブラリオブジェクトファイルを含む)
title: /WHOLEARCHIVE (すべてのライブラリオブジェクトファイルを含む)
ms.date: 02/12/2020
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: 1cbc2ad29bab124af90551d2f4a96ee9f08c578c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259176"
---
# <a name="wholearchive-include-all-library-object-files"></a>/WHOLEARCHIVE (すべてのライブラリオブジェクトファイルを含む)

リンクされた実行可能ファイルのスタティックライブラリにすべてのオブジェクトファイルを含めるようにリンカーを強制します。

## <a name="syntax"></a>構文

> **/WHOLEARCHIVE**\
> **/WHOLEARCHIVE:**_ライブラリ_

### <a name="arguments"></a>引数

*ライブラリ*\
スタティックライブラリのパス名 (省略可能)。 リンカーには、このライブラリのすべてのオブジェクトファイルが含まれています。

## <a name="remarks"></a>解説

/WHOLEARCHIVE オプションは、指定されたスタティックライブラリのすべてのオブジェクトファイルをリンカーに強制的に含めます。または、ライブラリが指定されていない場合は、指定したすべてのスタティックライブラリからリンクコマンドに指定します。 複数のライブラリに対して/WHOLEARCHIVE オプションを指定するには、リンカーコマンドラインで複数の/WHOLEARCHIVE スイッチを使用できます。 既定では、リンカーは、実行可能ファイル内の他のオブジェクトファイルによって参照されるシンボルをエクスポートする場合にのみ、リンクされた出力にオブジェクトファイルを含めます。 /WHOLEARCHIVE オプションを使用すると、リンカーコマンドラインで個別に指定されているかのように、すべてのオブジェクトファイルがスタティックライブラリに保存されます。

/WHOLEARCHIVE オプションを使用すると、スタティックライブラリからすべてのシンボルを再エクスポートできます。 これにより、複数のスタティックライブラリからコンポーネントを作成するときに、すべてのライブラリコード、リソース、およびメタデータが含まれるようにすることができます。 エクスポート用の Windows ランタイムコンポーネントを含むスタティックライブラリを作成するときに警告 LNK4264 が表示される場合は、そのライブラリを別のコンポーネントまたはアプリにリンクするときに/WHOLEARCHIVE オプションを使用します。

/WHOLEARCHIVE オプションは、Visual Studio 2015 Update 2 で導入されました。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] の [**リンカー**] で、[**コマンドライン**] プロパティページを選択します。

1. [ **追加のオプション** ] テキストボックスに/WHOLEARCHIVE オプションを追加します。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
