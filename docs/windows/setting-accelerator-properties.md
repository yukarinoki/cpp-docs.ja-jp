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
ms.openlocfilehash: 5d47dffb782da1094c157a7bbd21c40ab6ba9fef
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606705"
---
# <a name="setting-accelerator-properties"></a>アクセラレータのプロパティの設定

アクセラレータのプロパティで設定できる、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)いつでもです。 使用することも、**アクセラレータ**エディターのアクセラレータ テーブルでアクセラレータのプロパティを変更します。 使用して行われた変更、**プロパティ**ウィンドウまたは**アクセラレータ**エディターが、同じ結果がある: アクセラレータ テーブルでの編集をすぐに反映されます。

各アクセラレータには次の 3 つのプロパティは[ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160):

- [修飾子プロパティ](../windows/accelerator-modifier-property.md)コントロール、アクセラレータ キーの組み合わせを設定します。

   > [!NOTE]
   > **プロパティ**ウィンドウで、このプロパティが表示されます、3 つの独立したブール型プロパティとしてすべてのことができますが個別に制御: **Alt**、 **Ctrl**、および**Shift**します。

- [キー プロパティ](../windows/accelerator-key-property.md)アクセラレータとして使用する実際のキーを設定します。

- [プロパティを入力して](../windows/accelerator-type-property.md)として仮想 (VIRTKEY) と ASCII/ANSI キーが解釈されるかどうか決定します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[定義済みのアクセラレータ キー](../windows/predefined-accelerator-keys.md)  
[リソース エディター](../windows/resource-editors.md)  
[アクセラレータ エディター](../windows/accelerator-editor.md)