---
title: ML の致命的でないエラー A2006 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2006
dev_langs:
- C++
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31d2f7df00d1c0658ee8301fbde1efe2522b52fc
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054856"
---
# <a name="ml-nonfatal-error-a2006"></a>ML の致命的でないエラー A2006
**未定義のシンボル: 識別子**  
  
 定義されていないシンボルを使用しようとしています。  
  
 次のいずれかが発生した可能性があります。  
  
-   シンボルが定義されていません。  
  
-   フィールドは、指定された構造体のメンバーをでした。  
  
-   含まれていないインクルード ファイルでシンボルが定義されました。  
  
-   外部シンボルを使用していない、 [EXTERN](../../assembler/masm/extern-masm.md)または[EXTERNDEF](../../assembler/masm/externdef.md)ディレクティブです。  
  
-   シンボル名のスペルが間違っているされました。  
  
-   ローカル コード ラベルは、そのスコープの外部で参照されました。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)