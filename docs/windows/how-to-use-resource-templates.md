---
title: '方法: リソース テンプレートを使用して |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- language-specific template files
- resource templates
- resources [Visual Studio], creating
- rct files
- templates, resource templates
- resources [Visual Studio], templates
- .rct files
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bd85dd5c5b6468ca8246fdf11f4068eae928107
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602441"
---
# <a name="how-to-use-resource-templates"></a>方法: リソース テンプレートを使用する

リソース テンプレートは、.rct ファイルとして保存したカスタマイズされたリソースです。 リソース テンプレートは、他のリソースを作成するための出発点として使用できます。 リソース テンプレートを使用すると、標準のコントロールやその他の繰り返される要素などの、機能を共有する他のリソースやリソースのグループを開発する時間を節約できます。 たとえば、複数のダイアログ ボックスで、[ヘルプ] ボタンと会社のロゴのアイコンを使用することが必要になる場合があります。 これを簡単に実現するには、新しいダイアログ ボックスのテンプレートを作成して、ロゴと [ヘルプ] ボタンでカスタマイズします。

テンプレート フォルダー (またはインクルード パスで指定された任意の場所) に変更を保存する必要がありますリソース テンプレートをカスタマイズすると、新しいリソース テンプレートはリソースの種類の下に表示されるように、 [リソースの追加ダイアログボックス](../windows/add-resource-dialog-box.md). 必要に応じて、この新しいリソース テンプレートを何回でも使用することができます。

> [!NOTE]
> 言語固有のテンプレート ファイルは、メインのテンプレート ディレクトリのサブディレクトリに配置できます。 英語版のみのテンプレート ファイルを配置するなど、 \\< リソース テンプレート ディレクトリ\>\1033 します。

### <a name="to-create-a-template-for-resources"></a>リソースのテンプレートを作成するには

1. **ソリューション エクスプ ローラー**プロジェクトを右クリックします。

2. ショートカット メニューの**追加**、 をクリックし、**新しい項目の追加**します。

3. **新しい項目の追加** ダイアログ ボックスで、**テンプレート:** ウィンドウで、選択**リソース テンプレート ファイル (.rct)** します。

4. 新しい .rct ファイルの場所と名前を入力し、クリックして**オープン**します。

5. 新しい .rct ファイルがプロジェクトに追加されに表示されます**ソリューション エクスプ ローラー**下、**リソース**フォルダー。

   ドキュメント ウィンドウで開く、.rct ファイルをダブルクリックしにリソースを追加することができますようになりました (ドキュメント ウィンドウにファイルを右クリックし **リソースの追加**ショートカット メニューから)。 これらのリソースをカスタマイズして、.rct ファイルを保存できます。

   > [!NOTE]
   > 新しい RCT ファイルを作成するときに Visual Studio 内を検索 \Program Files\Microsoft Visual Studio 9.0\VC\VCResourceTemplates での \Program Files\Microsoft Visual Studio 9.0\VC\VCResourceTemplates\\*LCID* (場合は 1033 英語)、*または*任意の場所に、[インクルード パス](../windows/how-to-specify-include-directories-for-resources.md)します。 RCT ファイルを別のファイル フォルダー、たとえば \My Documents に格納した場合には、このフォルダーをインクルード パスに追加するだけで、Visual Studio によって RCT ファイルが検索されます。

### <a name="to-convert-an-existing-rc-file-to-an-rct-file"></a>既存の .rc ファイルを .rct ファイルに変換するには

1. [スタンドアロン ファイルとして .rc ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

2. **ファイル** メニューのをクリックして**保存\< *、filename*> として**します。

3. 場所を指定し、をクリックして**OK**します。

### <a name="to-create-a-new-resource-from-a-template"></a>テンプレートから新しいリソースを作成するには

1. [リソース ビュー](../windows/resource-view-window.md) .rc ファイルを右クリックして、ウィンドウ、**リソースの追加**ショートカット メニューから。

2. **リソースの追加** ダイアログ ボックスで、プラス記号をクリックします (**+**) の横にあるリソースをリソース ノードを展開し、そのリソースの使用可能なすべてのテンプレートを参照してください。

3. 使用するテンプレートをダブルクリックします。

4. リソース エディターで、追加したリソースを必要に応じて変更します。

   リソース エディターによって一意のリソース ID が自動的に指定されます。 変更することができます、[リソース プロパティ](../windows/changing-the-properties-of-a-resource.md)に応じて。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)