---
title: アクセラレータの修飾子 プロパティ |Microsoft Docs
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
ms.openlocfilehash: 0788536e776661b9a84a6cccc648a7db68389ae5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644256"
---
# <a name="accelerator-modifier-property"></a>アクセラレータの [修飾子] プロパティ
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
 [アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)