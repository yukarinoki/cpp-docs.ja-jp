---
title: 文字列の検索 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3763baf0f085dc72040ab22c9efd38e8aa8068f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875735"
---
# <a name="finding-a-string"></a>文字列の検索
文字列テーブルに 1 つまたは複数の文字列を検索して使用することができます[正規表現](/visualstudio/ide/using-regular-expressions-in-visual-studio)で、**ファイル内の検索**コマンド (**編集**メニュー) の文字列のすべてのインスタンスを検索するにはパターンに一致します。  
  
### <a name="to-find-a-string-in-the-string-table"></a>文字列テーブルに文字列を検索するには  
  
1.  アイコンをダブルクリックして、文字列テーブルを開きます[リソース ビュー](../windows/resource-view-window.md)です。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **編集** メニューのをクリックして**検索し、置換**、順に選択**検索**です。  
  
3.  **検索**ボックス、ドロップダウン リストから、以前の検索文字列を選択するかを検索する文字列のキャプションのテキストまたはリソースの識別子を入力します。  
  
4.  いずれかを選択、**検索**オプション。  
  
5.  をクリックして**次を検索する**です。  
  
    > [!TIP]
    >  ファイルを検索するときに、正規表現を使用して、使用して、**ファイル内の検索**コマンド。 パターンに一致またはの右側にあるボタンをクリックする正規表現を入力、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択するときに、検索文字列として設定、**検索**ボックス。 正規表現を使用する場合は必ず、**使用: 正規表現** チェック ボックスをオンします。  
  
 マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 」および「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ストリング エディター](../windows/string-editor.md)   

