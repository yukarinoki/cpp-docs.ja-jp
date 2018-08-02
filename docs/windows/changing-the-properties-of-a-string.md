---
title: 文字列のプロパティの変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource identifiers, string properties
- string tables, changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc8f0ec7c904355e3b5b4989a89fd13a7d9ad767
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464572"
---
# <a name="changing-the-properties-of-a-string"></a>文字列のプロパティの変更
### <a name="to-change-a-string-or-its-identifier"></a>文字列または識別子を変更するには  
  
1.  アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  編集するをダブルクリックする文字列を選択、 **ID**、**値**、または**キャプション**列。 これで次のようなことができます。  
  
    -   選択、 **ID**から、 **ID ドロップダウン**一覧、または ID を直接入力します。  
  
    -   別の番号を入力、**値**列。  
  
    -   入力時に編集、**キャプション**列。  
  
        > [!NOTE]
        >  文字列のプロパティを編集することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
 マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド。* マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください[チュートリアル: Windows フォームのローカリゼーション](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5)と[。チュートリアル: ASP.NET でのローカライズ用リソースを使用して](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)します。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ストリング エディター](../windows/string-editor.md)   