---
title: _emit 疑似命令 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ad75f4abf2e86cb08ba646e50e9390650993d05
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050699"
---
# <a name="emit-pseudoinstruction"></a>_emit 疑似命令
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 **_Emit**疑似命令は、現在のテキスト セグメントに、現在の場所にある 1 バイトを定義します。 **_Emit**疑似命令に似ています、 [DB](../../assembler/masm/db.md) MASM のディレクティブ。  
  
 次のフラグメントは、コードに 0x4A、示します、および 0x4B バイトを配置します。  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  場合`_emit`命令を生成、レジスタを変更する、最適化を使用してアプリケーションをコンパイルして、コンパイラがレジスタが影響を判断できません。 たとえば場合、`_emit`を変更する命令が生成されます、 **rax**レジスタ、コンパイラが認識していないを**rax**が変更されました。 コンパイラでは、不適切な想定の値は、インライン アセンブラー コードが実行した後で登録してください可能性があります。 その結果、アプリケーションでは、実行時に予期しない動作が発生可能性があります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)