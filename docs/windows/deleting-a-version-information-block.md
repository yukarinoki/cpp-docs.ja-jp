---
title: バージョン情報ブロックの削除 |Microsoft Docs
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
- blocks, deleting
- version information, deleting blocks
- resources [Visual Studio], deleting version information
ms.assetid: 4e1641eb-d5b2-4183-b273-bc5b51af1537
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f083364f839f963867234a4d3548ac1c00258cc8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649960"
---
# <a name="deleting-a-version-information-block"></a>バージョン情報ブロックの削除
### <a name="to-delete-a-version-information-block"></a>バージョン情報ブロックを削除するには  
  
1.  [[リソース ビュー]](../windows/resource-view-window.md)でバージョン情報リソースのアイコンをダブルクリックして開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  削除するブロック ヘッダーを右クリックして、ショートカット メニューから **[バージョン情報ブロックの削除]** を選びます。  
  
     選んだヘッダーはこのコマンドによって削除されますが、残りのバージョン情報はそのまま残ります。 操作を元に戻すことはできませんのでご注意ください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件
 Win32  
  
## <a name="see-also"></a>関連項目  
 [バージョン情報エディター](../windows/version-information-editor.md)   
 [バージョン情報 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)