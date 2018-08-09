---
title: アクセラレータ プロパティの設定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5337378b54c2109d05e28cb9d1bfed82f81913f3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652699"
---
# <a name="setting-accelerator-properties"></a>アクセラレータのプロパティの設定
アクセラレータのプロパティで設定できる、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)いつでもです。 また、アクセラレータ エディターを使用して、アクセラレータ テーブルでアクセラレータのプロパティを変更することもできます。 プロパティ ウィンドウを使用しても、アクセラレータ エディターを使用しても、変更の結果は同じです。編集はすぐにアクセラレータ テーブルに反映されます。  
  
 各アクセラレータには次の 3 つのプロパティは[ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   [修飾子プロパティ](../windows/accelerator-modifier-property.md)コントロール、アクセラレータ キーの組み合わせを設定します。  
  
    > [!NOTE]
    >  [プロパティ] ウィンドウでこのプロパティが表示されます 3 つの個別のブール型プロパティとしてすべてのことができますが個別に制御: **Alt**、 **Ctrl**と**shift キーを押し**。  
  
-   [キー プロパティ](../windows/accelerator-key-property.md)アクセラレータとして使用する実際のキーを設定します。  
  
-   [プロパティを入力して](../windows/accelerator-type-property.md)として仮想 (VIRTKEY) と ASCII/ANSI キーが解釈されるかどうか決定します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [定義済みのアクセラレータ キー](../windows/predefined-accelerator-keys.md)   
 [リソース エディター](../windows/resource-editors.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)