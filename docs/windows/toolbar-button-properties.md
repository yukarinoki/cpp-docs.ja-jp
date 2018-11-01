---
title: ツール バー ボタンのプロパティ (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
ms.openlocfilehash: f20556ac088180ceb1ed979c3e02ffc465b41c7b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665371"
---
# <a name="toolbar-button-properties-c"></a>ツール バー ボタンのプロパティ (C++)

ツール バー ボタンのプロパティは次のとおりです。

|プロパティ|説明|
|--------------|-----------------|
|**ID**|ボタンの ID を定義します。 ドロップダウンの一覧は、一般的な**ID**名。|
|**Width**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|
|**Height**|ボタンの高さを設定します。 1 つのボタンの高さがすべてのツールバーのボタンの高さを変更することに注意してください。 15 ピクセルをお勧めします。|
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 \N と名を追加すると、そのツール バー ボタンにツールヒントが追加されます。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)します。|

**幅**と**高さ**のすべてのボタンに適用されます。 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 したがって、ボタンの幅を 512 に設定した場合は 4 つのボタンのみができ、513 幅を設定する場合は 3 つのボタンのみができます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[ツール バー ボタンのプロパティを変更するには](../windows/changing-the-properties-of-a-toolbar-button.md)<br/>
[ツール バー エディター](../windows/toolbar-editor.md)