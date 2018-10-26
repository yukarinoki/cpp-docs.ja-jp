---
title: バイナリ編集 (C++) のリソースを開く |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- resources [C++], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 256ceee14f38885259da11453efef8451d34248c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068009"
---
# <a name="opening-a-resource-for-binary-editing-c"></a>バイナリ編集 (C++) のリソースを開く

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>バイナリ編集用に Windows デスクトップ リソースを開くには

1. [リソース ビュー](../windows/resource-view-window.md)で、編集の対象となる特定のリソース ファイルを選択します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. リソースを右クリックし、ショートカット メニューから **[バイナリー データを開く]** をクリックします。

   > [!NOTE]
   > 使用する場合、[リソース ビュー](../windows/resource-view-window.md)で Visual Studio が認識しないこと (RCDATA やカスタム リソース) など、リソースの形式でリソースを開くウィンドウが自動的に開きます、**バイナリ**エディター。

### <a name="to-open-a-managed-resource-for-binary-editing"></a>バイナリ編集の対象となるマネージド リソースを開くには

1. **ソリューション エクスプ ローラー**、編集する特定のリソース ファイルを選択します。

2. リソースを右クリックして、ショートカット メニューから **[プログラムから開く]** を選択します。

3. **[プログラムから開く]** ダイアログ ボックスで、 **バイナリ エディター**を選択します。

   > [!NOTE]
   > [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

   > [!NOTE]
   > マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

![バイナリ エディター](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
バイナリ エディターに表示されるダイアログ ボックスのバイナリ データ

バイナリ エディターでは、特定の ASCII 値のみが表されます (0x20 ～ 0x7E)。 拡張文字は、バイナリ エディターの ASCII 値セクション (右側のパネル) にピリオドで表示されます。 "印刷可能" な文字は、ASCII 値の 32 ～ 126 です。

> [!NOTE]
> 使用する場合、**バイナリ**別のエディター ウィンドウで既に編集中のリソース エディターが最初に他のエディター ウィンドウを閉じます。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[Binary Editor](binary-editor.md)