---
title: '方法: リソース内のシンボルの検索 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols, finding
- resources [Visual Studio], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f105f41c465d2750d372a8794a9ab66fa13db466
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215983"
---
# <a name="how-to-search-for-symbols-in-resources"></a>方法: リソース内のシンボルを検索する

### <a name="to-find-symbols-in-resources"></a>リソース内のシンボルを検索するには

1. **編集**] メニューの [選択**シンボルの検索**します。

2. [シンボルの検索 ダイアログ ボックス](https://msdn.microsoft.com/63e93d9c-784f-418d-a76a-723da5ff5d96)の**検索**ボックスで、ドロップダウン リストから、以前の検索文字列を選択するか、(用、id_accel1 を検索するアクセラレータ キーを入力します。

   > [!TIP]
   > 使用する[正規](/visualstudio/ide/using-regular-expressions-in-visual-studio)検索に使用する必要があります、 [Findinfiles コマンド](/visualstudio/ide/reference/find-command)から、**編集**メニューの代わりに、 **シンボルの検索**コマンド。 正規表現を有効にするが必要、**使用: 正規表現**チェック ボックスをオン、[検索 ダイアログ ボックス](https://msdn.microsoft.com/dad03582-4931-4893-83ba-84b37f5b1600)します。 右側に、右矢印ボタンをクリックすることができ、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択すると、検索文字列として設定されます、**検索**ボックス。

3. いずれかの選択、**検索**オプション。

4. クリックして**次を検索**します。

   > [!NOTE]
   > 文字列リソース、アクセラレータ リソース、またはバイナリ リソース内のシンボルは検索できません。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 リソースにアクセスする、マネージ プロジェクトにリソース ファイルを手動で追加するのには静的なリソースを表示して、リソースの割り当ては、プロパティに文字列です。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)  
[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)