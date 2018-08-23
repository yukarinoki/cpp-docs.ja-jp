---
title: '方法: リソース スクリプト ファイルの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files, creating
- .rc files, creating
- resource script files, creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b07efbd4f1434992c76de2b7e959f4578d60096
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608738"
---
# <a name="how-to-create-a-resource-script-file"></a>方法: リソース スクリプト ファイルを作成する

> [!NOTE]
> **リソース エディター** Express エディションでは使用できません。
>
> これは Windows デスクトップ アプリケーションだけに適用できます。 .NET 言語のプロジェクトでは、リソース スクリプト ファイルを使用しません。 詳細については、「 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)」を参照してください。

### <a name="to-create-a-new-resource-script-rc-file"></a>リソース スクリプト (.rc) ファイルを新規作成するには

1. 既存のプロジェクト フォルダーにフォーカスを移す**ソリューション エクスプ ローラー**、たとえば、`MyProject`します。

   > [!NOTE]
   > ソリューション フォルダーを含むプロジェクトのフォルダーと混同しないでください**ソリューション エクスプ ローラー**します。 重点を置く場合、**ソリューション**フォルダーでの選択、**新しい項目の追加**ダイアログ ボックス (手順 3) では別になります。

2. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。

3. **[新しい項目の追加]** ダイアログ ボックスで、 **[Visual C++]** フォルダーをクリックし、右側のペインの **[リソース ファイル (.rc)]** を選択します。

4. **[プロジェクト名]** ボックスにリソース スクリプト ファイルの名前を入力し、 **[開く]** をクリックします。

これで、新しいリソースを [作成](../windows/how-to-create-a-resource.md) して .rc ファイルに追加できます。

> [!NOTE]
> リソース スクリプト (.rc ファイル) を追加できるのは、Visual Studio IDE に読み込まれる既存のプロジェクトだけです。 プロジェクトの外側にあるスタンドアロンの .rc ファイルは作成できません。 [リソース テンプレート](../windows/how-to-use-resource-templates.md) (.rct ファイル) はいつでも作成できます。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)