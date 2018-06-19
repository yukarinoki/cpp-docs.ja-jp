---
title: 呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27c18c83b623ce1a22ffcb5e1a9f1ce98ee6eb20
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055171"
---
# <a name="invoke"></a>INVOKE
によって指定されたアドレスでプロシージャが呼び出される*式*、スタックまたは言語の種類の標準的な呼び出し規約に従ってレジスタで引数を渡すことです。  
  
## <a name="syntax"></a>構文  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## <a name="remarks"></a>コメント  
 プロシージャに渡された各引数式、レジスタのペア、またはアドレス式が適用される場合があります (式に続く`ADDR`)。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)