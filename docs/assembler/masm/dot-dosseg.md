---
title: .DOSSEG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3817cfe98758faf86ea87d74e02657598c3e806b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054887"
---
# <a name="dosseg"></a>.DOSSEG
MS-DOS セグメントの規則に従ってセグメントを並べ替えます。 コードは、最初に、タ、ではなく、セグメントと、タにし、セグメント。  
  
## <a name="syntax"></a>構文  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>コメント  
 タ内のセグメントが、この順序に従う: BSS やスタックではなくセグメント BSS セグメントし、最後にスタック セグメント。 MASM のスタンドアロン プログラムで CodeView サポートを確保するため、主に使用します。 同じ[DOSSEG](../../assembler/masm/dosseg.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)