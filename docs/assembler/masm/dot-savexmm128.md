---
title: .SAVEXMM128 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d50d4bbc7f9c89e9ef36a1dd8cf3dfeb56de79b5
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057940"
---
# <a name="savexmm128"></a>.SAVEXMM128
生成するか、`UWOP_SAVE_XMM128`または`UWOP_SAVE_XMM128_FAR`アンワインド コードのエントリの指定の XMM レジスタと現在のプロローグのオフセットを使用してオフセットします。 MASM は、最も効率的なエンコーディングを選択します。  
  
## <a name="syntax"></a>構文  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>コメント  
 .SAVEXMM128 できる ml64.exe フレーム関数をアンワインドするとはから拡張すると、プロローグ内でのみ使用する方法を指定、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[です。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブです。 これらのディレクティブは、コードを生成しません。のみを生成する`.xdata`と`.pdata`です。 .SAVEXMM128 は、実際にはアンワインドにアクションを実装する命令によって先行されなければなりません。 アンワインド ディレクティブとして、本来はマクロでのアンワインドに同意を得るようにコードの両方をラップすることをお勧めします。  
  
 `offset` 16 の倍数である必要があります。  
  
 詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)