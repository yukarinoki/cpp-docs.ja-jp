---
title: ML の致命的でないエラー A2050 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 159ed131c13166435114234b3b16a82cd4d41d1f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32056195"
---
# <a name="ml-nonfatal-error-a2050"></a>ML の致命的でないエラー A2050
**real または BCD 番号は使用できません。**  
  
 浮動小数点 (実際) の数または binary coded decimal (BCD) 定数が以外に使用したデータの初期化子として。  
  
 次のいずれかが発生しました。  
  
-   実数または BCD は、式で使用されました。  
  
-   以外のディレクティブを初期化するために使用された実数[DWORD](../../assembler/masm/dword.md)、 [QWORD](../../assembler/masm/qword.md)、または[TBYTE](../../assembler/masm/tbyte.md)です。  
  
-   以外のディレクティブを初期化するために使用された BCD`TBYTE`です。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)