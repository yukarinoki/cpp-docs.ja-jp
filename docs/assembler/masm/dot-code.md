---
title: .コード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59e376fc9c10ab8891b02e4da334341ae0534b73
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051237"
---
# <a name="code"></a>.CODE
使用すると[です。モデル](../../assembler/masm/dot-model.md)、コード セグメントの開始を示します。  
  
## <a name="syntax"></a>構文  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`name`|コード セグメントの名前を指定する省略可能なパラメーターです。 既定の名前は非常に小さく、small、コンパクト、およびフラット _TEXT[モデル](../../assembler/masm/dot-model.md)です。 既定の名前は*modulename*_TEXT その他のモデル。|  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)