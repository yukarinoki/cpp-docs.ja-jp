---
title: インライン アセンブリの最適化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c494594e3b7c541487f34fd33359b0e31f73dd61
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050559"
---
# <a name="optimizing-inline-assembly"></a>インライン アセンブリの最適化
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 存在、`__asm`関数内のブロックに影響を与えるいくつかの方法で最適化します。 コンパイラはまず、最適化するために、`__asm`自体をブロックします。 アセンブリ言語で記述するはまったく取得です。 2 番目の存在、`__asm`ブロックへの影響は、変数の記憶域を登録します。 コンパイラ間でのレジスタ格納変数の回避、`__asm`でレジスタの内容が変更する場合はブロック、`__asm`ブロックします。 最後に、いくつか他の関数全体の最適化を受ける関数内のアセンブリ言語を含めることによってです。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)