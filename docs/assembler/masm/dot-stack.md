---
title: .スタック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .STACK
dev_langs:
- C++
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab47677da8db2afca73a078b110300a017e7c8d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052301"
---
# <a name="stack"></a>.STACK
使用すると[です。モデル](../../assembler/masm/dot-model.md)、(セグメント名スタック) のスタック セグメントを定義します。 省略可能な`size`スタック (既定値は 1,024) のバイト数を指定します。 `.STACK`ディレクティブは、スタックのステートメントを自動的に閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
  
.STACK [[size]]  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)