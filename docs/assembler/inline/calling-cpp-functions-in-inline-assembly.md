---
title: インライン アセンブリでの C++ 関数の呼び出し |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffbd8038d240bc2ab0240d172d914790b6ca02ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049624"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C++ 関数の呼び出し
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックがないオーバー ロードされるグローバルの C++ 関数のみを呼び出すことができます。 オーバー ロードされたグローバル C++ 関数、または C++ メンバー関数を呼び出した場合、コンパイラ エラーが発生します。  
  
 宣言された任意の関数を呼び出すこともできます**extern"C"** リンケージ。 これにより、`__asm`ブロック内にすべての標準ヘッダー ファイルがライブラリ関数を宣言するために、C のライブラリ関数を呼び出し、C プログラム**extern"C"** リンケージ。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)