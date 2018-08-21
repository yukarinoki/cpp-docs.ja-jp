---
title: 複数の文字列の Caption プロパティの変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor, changing properties of multiple strings
- strings [C++], changing caption property of multiple
- string editing, string tables
- string tables, changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2372230726530bb0d9bbf8eb4e187cd55c203711
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649098"
---
# <a name="changing-the-caption-property-of-multiple-strings"></a>複数の文字列の Caption プロパティの変更
次の手順では、複数の文字列の caption プロパティを変更する方法を示します。  
  
### <a name="to-change-the-caption-property-of-multiple-strings"></a>複数の文字列の caption プロパティを変更するには  
  
1.  アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  押しながら変更する文字列を選択、 **Ctrl**キーのそれぞれをクリックするとします。  
  
3.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、変更するプロパティの新しい値を入力します。  
  
4.  **Enter** キーを押します。  
  
 マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください[チュートリアル: Windows フォームのローカリゼーション](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5)と[。チュートリアル: ASP.NET でのローカライズ用リソースを使用して](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ストリング エディター](../windows/string-editor.md)   