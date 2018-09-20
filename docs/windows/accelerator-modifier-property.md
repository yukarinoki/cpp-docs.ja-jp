---
title: アクセラレータの修飾子 プロパティ (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c053af58842c75910b0214ae828c652daa33a81
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389292"
---
# <a name="accelerator-modifier-property-c"></a>アクセラレータの修飾子 プロパティ (C++)

アクセラレータ テーブルで、[修飾子] プロパティに有効なエントリを次に示します。

|[値]|説明|
|-----------|-----------------|
|**None**|ユーザーが押したのみ、**キー**値。 これが最も効果的に値で使用される、ASCII]/[ANSI 001 026、を通じてとして解釈される ^ A ~ ^ Z (ctrl キーを押し、A ~ Z CTRL)。|
|**Alt**|ユーザーが押す必要があります、 **Alt**する前にキー、**キー**値。|
|**Ctrl**|ユーザーが押す必要があります、 **Ctrl**する前にキー、**キー**値。 ASCII 型では無効です。|
|**Shift**|ユーザーが押す必要があります、 **Shift**する前にキー、**キー**値。|
|**Ctrl + Alt**|ユーザーが押す必要があります、 **Ctrl**キーと**Alt**する前にキー、**キー**値。 ASCII 型では無効です。|
|**Ctrl + Shift**|ユーザーが押す必要があります、 **Ctrl**キーと**Shift**する前にキー、**キー**値。 ASCII 型では無効です。|
|**Alt + Shift**|ユーザーが押す必要があります、 **Alt**キーと**Shift**する前にキー、**キー**値。 ASCII 型では無効です。|
|**Ctrl + Alt + Shift**|ユーザーが押す必要があります**Ctrl**、 **Alt**と**Shift**する前に、**キー**値。 ASCII 型では無効です。|

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)