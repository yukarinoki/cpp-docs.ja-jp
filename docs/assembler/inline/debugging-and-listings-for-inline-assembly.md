---
title: デバッグとインライン アセンブリの一覧表示 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 457402626edcdb2be05923aa33bbd26b1cab7137
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050117"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>インライン アセンブリのデバッグと一覧表示
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 コンパイルする場合、ソース レベル デバッガーでインライン アセンブラー コードを含むプログラムをデバッグすることができます、 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)オプション。  
  
 デバッガー内では、C または C++ とアセンブリ言語の両方の行にブレークポイントを設定できます。 混在アセンブリとソース モードを有効にする場合は、ソースとアセンブリ コードの逆アセンブルされたフォームの両方を表示できます。  
  
 複数のアセンブリ命令を配置することに注意してください。 またはソース言語ステートメントを 1 つの行がデバッグを妨害することができます。 ソース モードが同じ直線上の個々 のステートメントではありませんが、1 行にブレークポイントを設定するのに、デバッガーを使用することができます。 同じ原則に適用されます、`__asm`ブロックが 1 つの論理行に展開される C マクロとして定義されています。  
  
 混在したソースとアセンブリのリストを作成するかどうか、 [/FAs](../../build/reference/fa-fa-listing-file.md)コンパイラ オプションには、一覧には、アセンブリ言語の各行のソースとアセンブリの両方のフォームが含まれています。 一覧で、マクロは展開されませんが、コンパイル時に、展開されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)