---
title: アクセラレータの修飾子 プロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: d99d4656f2835f9adb60f310e429c4ccb97ac7b6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854055"
---
# <a name="accelerator-modifier-property"></a>アクセラレータの [修飾子] プロパティ
アクセラレータ テーブルの [修飾子] プロパティに有効なエントリを次に示します。  
  
|[値]|説明|  
|-----------|-----------------|  
|**None**|ユーザーは、キー値のみを押します。 これが最も効果的の値と共に使用 ASCII/ANSI 001 026、を通じてとして解釈される ^ A ~ ^ Z (ctrl キーを押し、A ~ Z ctrl キーを押し)。|  
|**alt キー**|ユーザーは、キー値の前に ALT キーを押す必要があります。|  
|**ctrl キー**|ユーザーは、キー値の前に、CTRL キーを押す必要があります。 ASCII 型では無効です。|  
|**Shift キー**|ユーザーは、キー値の前に、SHIFT キーを押す必要があります。|  
|**Ctrl + Alt**|ユーザーには、CTRL キーとキー値の前に ALT キーを押す必要があります。 ASCII 型では無効です。|  
|**Ctrl + Shift**|ユーザーには、CTRL キーとキー値の前に、SHIFT キーを押す必要があります。 ASCII 型では無効です。|  
|**Alt + Shift**|ユーザーには、ALT キーとキー値の前に、SHIFT キーを押す必要があります。 ASCII 型では無効です。|  
|**Ctrl + Alt + Shift**|ユーザーは、キー値の前に ctrl キーを押し、alt キーと shift キーを押す必要があります。 ASCII 型では無効です。|  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)