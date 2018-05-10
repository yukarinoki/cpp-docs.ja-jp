---
title: 追加または削除する文字列 |Microsoft ドキュメント
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
- strings [C++], adding to string tables
- string tables, deleting strings
- strings [C++], deleting in string tables
- string tables, adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e15e29c99dba89ef29ba5b909c62f819bedf63f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="adding-or-deleting-a-string"></a>文字列の追加と削除
文字列エディターを使用して、文字列テーブルに新しいエントリを迅速に挿入できます。 新しい文字列は、テーブルの最後に配置され、[次へ] の使用可能な識別子が指定されます。 ID、値、またはキャプション プロパティを編集することができますし、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)に応じて。  
  
 ストリング エディターは、既に使用されている ID を使用しないことを確認します。 ID を既に使用中に選択文字列エディターは通知され、汎用的な一意の ID、IDS_STRING58113 を割り当てます。  
  
### <a name="to-add-a-string-table-entry"></a>ストリング テーブルのエントリを追加するには  
  
1.  アイコンをダブルクリックして、文字列テーブルを開きます[リソース ビュー](../windows/resource-view-window.md)です。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  文字列テーブル内で右クリックし、**新しい文字列**ショートカット メニューからです。  
  
3.  **文字列**エディター、select、 **ID** ID ドロップダウン リストまたは型 ID に直接配置からです。  
  
4.  編集、**値**必要に応じて、します。  
  
5.  エントリを入力、**キャプション**です。  
  
    > [!NOTE]
    >  Null 文字列は、Windows の文字列テーブルでは許可されません。 「を入力してください、文字列のこのテーブルのエントリ」を選択するメッセージが表示されます、null 文字列は、文字列テーブルにエントリを作成する場合  
  
### <a name="to-delete-a-string-table-entry"></a>ストリング テーブルのエントリを削除するには  
  
1.  削除するエントリを選択します  
  
2.  **編集** メニューのをクリックして**削除**です。  
  
 \- または -  
  
-   削除する文字列を右クリックして**削除**ショートカット メニューからです。  
  
 \- または -  
  
-   キーを押して、**削除**キー。  
  
 マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 」および「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ストリング エディター](../windows/string-editor.md)   

