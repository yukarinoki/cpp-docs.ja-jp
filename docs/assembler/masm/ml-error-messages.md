---
title: ML エラー メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fbc2ae6388ad11a411850d03de421d2f6820fc03
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057098"
---
# <a name="ml-error-messages"></a>ML エラー メッセージ
MASM のコンポーネントによって生成されたエラー メッセージは、3 つのカテゴリに分類されます。  
  
-   **致命的なエラー。** これらをユーティリティが通常のプロセスを完了するを妨げる重大な問題を示します。  
  
-   **致命的でないエラーです。** ユーティリティは、そのプロセスを完了可能性があります。 場合は、その結果は希望する可能性があります。  
  
-   **警告です。** これらのメッセージは、目的の結果を得られない可能性がありますの状態を示します。  
  
 すべてのエラー メッセージは、次の形式をとります。  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 それぞれの文字について以下に説明します。  
  
 `Utility`  
 エラー メッセージを送信するプログラム。  
  
 *ファイル名*  
 エラーが発生する条件を含むファイルです。  
  
 *Line*  
 エラー条件が存在するおおよその行番号。  
  
 *Error_type*  
 致命的なエラー、エラー、または警告です。  
  
 *コード*  
 一意の 5 または 6 桁のエラー コード。  
  
 `Message_text`  
 短期的および一般的なエラー状態の説明です。  
  
## <a name="see-also"></a>関連項目  
 [Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)