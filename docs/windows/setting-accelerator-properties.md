---
title: アクセラレータのプロパティの設定 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
ms.openlocfilehash: 47ebd54fdaff099e3a8ce828581a66b0ec871915
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647019"
---
# <a name="setting-accelerator-properties"></a>アクセラレータのプロパティの設定

アクセラレータのプロパティで設定できる、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)いつでもです。 使用することも、**アクセラレータ**エディターのアクセラレータ テーブルでアクセラレータのプロパティを変更します。 使用して行われた変更、**プロパティ**ウィンドウまたは**アクセラレータ**エディターが、同じ結果がある: アクセラレータ テーブルでの編集をすぐに反映されます。

アクセラレータ ID ごとに 3 つのプロパティがあります。

- [修飾子プロパティ](../windows/accelerator-modifier-property.md)コントロール、アクセラレータ キーの組み合わせを設定します。

   > [!NOTE]
   > **プロパティ**ウィンドウで、このプロパティが表示されます、3 つの独立したブール型プロパティとしてすべてのことができますが個別に制御: **Alt**、 **Ctrl**、および**Shift**します。

- [キー プロパティ](../windows/accelerator-key-property.md)アクセラレータとして使用する実際のキーを設定します。

- [プロパティを入力して](../windows/accelerator-type-property.md)として仮想 (VIRTKEY) と ASCII/ANSI キーが解釈されるかどうか決定します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[定義済みのアクセラレータ キー](../windows/predefined-accelerator-keys.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)