---
title: '方法: リソース内のシンボルの検索 |Microsoft ドキュメント'
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
ms.openlocfilehash: b45780223191c8dacec12d5312f4d2ac724b4d4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880219"
---
# <a name="how-to-search-for-symbols-in-resources"></a>方法: リソース内のシンボルを検索する
### <a name="to-find-symbols-in-resources"></a>リソース内のシンボルを検索するには  
  
1.  **編集**] メニューの [選択**シンボルの検索**です。  
  
2.  [シンボルの検索 ダイアログ ボックス](http://msdn.microsoft.com/en-us/63e93d9c-784f-418d-a76a-723da5ff5d96)で、**検索**ボックス、ドロップダウン リストから、以前の検索文字列を選択するか (用、id_accel1 を検索するアクセラレータ キーを入力します。  
  
    > [!TIP]
    >  使用する[正規表現](/visualstudio/ide/using-regular-expressions-in-visual-studio)検索に使用する必要があります、 [Findinfiles コマンド](/visualstudio/ide/reference/find-command)から、**編集**の代わりにメニューを開き、**シンボルの検索**コマンド。 正規表現を有効にする必要があります、**使用: 正規表現** チェック ボックスをオンに、[検索 ダイアログ ボックス](http://msdn.microsoft.com/en-us/dad03582-4931-4893-83ba-84b37f5b1600)です。 右側にある右矢印ボタンをクリックすることができ、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択するときに、検索文字列として設定、**検索**ボックス。  
  
3.  いずれかを選択、**検索**オプション。  
  
4.  をクリックして**次を検索する**です。  
  
    > [!NOTE]
    >  文字列リソース、アクセラレータ リソース、またはバイナリ リソース内のシンボルは検索できません。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)を選択します。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)