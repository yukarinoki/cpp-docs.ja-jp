---
title: シンボルの新規作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.creating
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box
- symbols, creating
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 76dec37ec908b40ed5cc6f32dd3d0c6bd3c149e4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642625"
---
# <a name="creating-new-symbols"></a>シンボルの新規作成
新しいプロジェクトを開始するときは、必要なシンボル名を、シンボル名を割り当てるリソースを作成する前に決めておくと便利です。  
  
### <a name="to-create-a-new-symbol-using-the-resource-symbols-dialog-box"></a>[リソース シンボル] ダイアログ ボックスを使用して新しいシンボルを作成するには  
  
1.  [リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)、選択**新規**します。  
  
2.  **名前**ボックスに、シンボル名を入力します。  
  
3.  割り当てられたシンボル値を受け入れます。  
  
     - または -  
  
     **値**ボックスに、新しい値を入力します。  
  
4.  クリックして**OK**新しいシンボルをシンボルの一覧に追加します。  
  
 既に存在するシンボルの名前を入力すると、その名前のシンボルが既に定義されていることを示すメッセージ ボックスが表示されます。 複数の同じ名前のシンボルを定義することはできませんが、同じ数値を持つ異なるシンボルを定義することができます。 詳細については、次を参照してください。[シンボル名の制限](../windows/symbol-name-restrictions.md)と[シンボル値の制限](../windows/symbol-value-restrictions.md)します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 」を参照してください。マネージド プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)を選択します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース シンボルの表示](../windows/viewing-resource-symbols.md)   
 [定義済みシンボル ID](../windows/predefined-symbol-ids.md)