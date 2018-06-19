---
title: XMMWORD |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8fd8e6c82a3275161e519eeead490473e8d64ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32056419"
---
# <a name="xmmword"></a>XMMWORD
MMX と SSE (XMM) の命令では、128 ビットのマルチ メディア オペランドに使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>コメント  
 `XMMWORD` 同じ型を表すために、 [_ _m128](../../cpp/m128.md)です。  
  
## <a name="example"></a>例  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```