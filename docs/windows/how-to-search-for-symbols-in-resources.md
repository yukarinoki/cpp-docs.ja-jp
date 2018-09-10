---
title: '方法: リソース (C++) 内のシンボルの検索 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51b2045a1605a37fa9c0d17fdc0c9456652345bd
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314197"
---
# <a name="how-to-search-for-symbols-in-resources-c"></a>方法: リソース (C++) 内のシンボルの検索

### <a name="to-find-symbols-in-resources"></a>リソース内のシンボルを検索するには

1. **編集**] メニューの [選択**シンボルの検索**します。

2. [シンボルの検索 ダイアログ ボックス](/visualstudio/ide/go-to)の**検索**ボックスで、ドロップダウン リストから、以前の検索文字列を選択するか、(用、id_accel1 を検索するアクセラレータ キーを入力します。

   > [!TIP]
   > 使用する[正規](/visualstudio/ide/using-regular-expressions-in-visual-studio)検索に使用する必要があります、 [Findinfiles コマンド](/visualstudio/ide/reference/find-command)から、**編集**メニューの代わりに、 **シンボルの検索**コマンド。 正規表現を有効にするが必要、**使用: 正規表現**チェック ボックスをオン、[検索 ダイアログ ボックス](/visualstudio/ide/finding-and-replacing-text)します。 右側に、右矢印ボタンをクリックすることができ、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択すると、検索文字列として設定されます、**検索**ボックス。

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