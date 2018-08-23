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
ms.openlocfilehash: 7e6750bfc0195eaaa350b829d1d899f648e9fe0e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592637"
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