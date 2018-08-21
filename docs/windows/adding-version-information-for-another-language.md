---
title: 別の言語のバージョン情報の追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- languages, version information
- New Version Info Block
- blocks, adding
- resources [Visual Studio], adding version information
- version information, adding for languages
ms.assetid: 17f6273c-e1cc-441a-a3d8-f564341cbf20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93682f1a12e2fe2d5dfaf715a718563c35ecddde
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650457"
---
# <a name="adding-version-information-for-another-language"></a>他言語のバージョン情報の追加
### <a name="to-add-version-information-for-another-language-new-info-block"></a>別の言語のバージョン情報 (新しい情報ブロック) を追加するには  
  
1.  [[リソース ビュー]](../windows/resource-view-window.md)でバージョン情報リソースをダブルクリックして開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  バージョン情報のテーブル内で右クリックし、ショートカット メニューから **[新しいバージョン情報ブロック]** を選びます。  
  
     このコマンドを使用して、現在のバージョン情報リソースにさらに情報ブロックを追加し、それに対応するプロパティを [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で開きます。  
  
3.  **[プロパティ]** ウィンドウで、新しいブロック用の適切な言語と文字セットを選びます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件 
 Win32  
  
## <a name="see-also"></a>関連項目  
 [バージョン情報エディター](../windows/version-information-editor.md)   
 [バージョン情報 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)