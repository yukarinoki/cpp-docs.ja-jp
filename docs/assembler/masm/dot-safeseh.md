---
title: .SAFESEH |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea34448b4dae0525e7feb2fd7cca310a95a6e3c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052464"
---
# <a name="safeseh"></a>.SAFESEH
構造化例外ハンドラーとして関数を登録します。  
  
## <a name="syntax"></a>構文  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>コメント  
 *識別子*の ID をローカルに定義されている必要があります[PROC](../../assembler/masm/proc.md)または[EXTRN](../../assembler/masm/extrn.md)プロシージャ A[ラベル](../../assembler/masm/label-masm.md)は許可されていません。 します。SAFESEH ディレクティブに必要な[/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe コマンド ライン オプションです。  
  
 構造化例外ハンドラーの詳細については、次を参照してください。 [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)です。  
  
 たとえば、安全な例外ハンドラーを登録するに (次のように) 新しい MASM ファイルを作成、/safeseh でアセンブリおよびリンクされたオブジェクトに追加します。  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)